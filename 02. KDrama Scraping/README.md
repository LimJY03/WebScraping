# Korean Drama Details Scraping Project

In this project, we will be scraping a [KDrama Website](https://butchixanh.com) to obtain the:

1. KDrama Name
2. KDrama Post Date
3. KDrama Site for Download Link

We will be using `Python` to write the codes, therefore we will use `Jupyter Notebook` to run the codes.

The two package and libraries used for this project are:

1. [Selenium](https://selenium-python.readthedocs.io/) - To scrape web data.
2. [Pandas](https://pandas.pydata.org/) - To convert scraped data into a Pandas Data Frame.

---

## Disclaimer

Is web scraping legal?

> *In 2019, the US Court of Appeals denied LinkedIn’s request to prevent HiQ, an analytics company, from scraping its data. The decision was important in the data privacy and data regulation areas. It showed that any data that is publicly available and not copyrighted is available to web crawlers.*
>
> src: [blog post](https://pub.towardsai.net/web-scraping-top-movies-with-python-and-selenium-8c2f0c6a1d69) (written by [Dennis Niggl](https://medium.com/@dniggl?source=post_page-----8c2f0c6a1d69--------------------------------)) that is published in TowardsAI.

Some websites allow web scraping but some prohibit access to their websites. To find out whether a website allows web scraping, look at the website's "`robots.txt`" file. You can find this file by appending "`/robots.txt`" to the main URL that you want to scrape.

The file for this project can be accessed through `https://butchixanh.com/robots.txt`.

```txt
# robots.txt for butchinxanh

Sitemap: https://butchixanh.com/sitemap.xml
Sitemap: https://butchixanh.com/news-sitemap.xml
User-agent: *
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php
```

---

# The HTML Structure

After inspecting the elements in the website, this is the general structure of the website's `HTML`:

```html
<!DOCTYPE HTML>
<head></head>
<body>
    ...
    <div id="page" class="site tg-site">
        ...
        <main id="main" class="site-main">
            <div id="content" class="site-content">
                <div class="tg-container tg-container--flex tg-container--flex-space-between">
                    <div class="tg-container tg-container--flex tg-container--flex-space-between">
                        <div id="primary" class="content-area">
                            <article id="post-2658" class="post-2658 page type-page status-publish hentry zakra-article-page">
                                ...
                                <div class="entry-content">
                                    ...
                                    <div class="ptam-block-post-grid aligncenter">
                                        <div class="ptam-post-grid-items is-grid columns-4">
                                            <article class="has-thumb" style="border: 0px solid #000000;  background: inherit; padding: 0px; border-radius: 0px;">
                                                <div class="ptam-block-post-grid-image" style="text-align: left">

                                                    <!-- Site URL is here! -->
                                                    <a href="https://butchixanh.com/money-heist-korea-joint-economic-area/" rel="bookmark" class="local-link"></a>
                                                </div>
                                                <div class="ptam-block-post-grid-text">
                                                    <h6 class="ptam-block-post-grid-title" style="text-align: left">

                                                        <!-- KDrama Name is here! -->
                                                        <a href="https://butchixanh.com/money-heist-korea-joint-economic-area/" rel="bookmark" style="color: inherit; font-family: inherit; box-shadow: unset;" class="local-link">Money Heist: Korea – Joint Economic Area</a>
                                                    </h6>
                                                    <div class="ptam-block-post-grid-byline " style="text-align: left; color: inherit; font-family: inherit">

                                                        <!-- KDrama Post Date is here! -->
                                                        <time datetime="2022-06-24T19:11:32+07:00" class="ptam-block-post-grid-date">June 24, 2022</time>
                                                    </div>
                                                    ...
                                                </div>
                                            </article>
                                        </div>
                                    </div>
                                </div>
                            </article>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>
</body>
```

The common pattern found here to obtain the 3 information that we want to scrape are:

* KDrama Name

    ```html
    <div class="ptam-block-post-grid-text">
        <h6 class="ptam-block-post-grid-title" style="text-align: left">
            <a href="https://butchixanh.com/money-heist-korea-joint-economic-area/" rel="bookmark" style="color: inherit; font-family: inherit; box-shadow: unset;" class="local-link">Money Heist: Korea – Joint Economic Area</a>
        </h6>
    </div>
    ```

    Since the class `"local-link"` is used at other places as well, we will be using `By.XPATH` to obtain the correct data we want.

* KDrama Post Date

    ```html
    <div class="ptam-block-post-grid-byline " style="text-align: left; color: inherit; font-family: inherit">
        <time datetime="2022-06-24T19:11:32+07:00" class="ptam-block-post-grid-date">June 24, 2022</time>
    </div>
    ```

    Since the class `ptam-block-post-grid-date` is only used on post dates, we will be using `By.CLASS_NAME` to obtain the date elements.

* KDrama Site URL

    ```html
    <div class="ptam-block-post-grid-image" style="text-align: left">
        <a href="https://butchixanh.com/money-heist-korea-joint-economic-area/" rel="bookmark" class="local-link"></a>
    </div>
    ```

    Similar to the name, we will be using `By.XPATH` but in this case, we will also specify `.get_attribute("href")` to obtain the URL to the site.