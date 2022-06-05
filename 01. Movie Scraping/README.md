# Movie Details Scraping Project

This project is done with reference to a [blog post](https://pub.towardsai.net/web-scraping-top-movies-with-python-and-selenium-8c2f0c6a1d69) (written by [Dennis Niggl](https://medium.com/@dniggl?source=post_page-----8c2f0c6a1d69--------------------------------)) that is published in TowardsAI.

Below are some key notes from the blog post on this project.

---

## What is Web Scraping?

It is a technique used by programmers to automate the process of data extraction from websites within a short period of time. We can use web scraping tools to collect unstructured data and store it in a structured format that can be used for further analysis.

## How can Web Scraping be Used?

Web scraping can be used for a wide variety of reasons including:

### Price Comparison:

Used to collect data from online shopping websites and compare products and pricing.

### Research and Development:

Used to collect a large set of data (Statistics, General Information, Weather, etc.) from websites, which are then analyzed and used to carry out surveys.

### Social Media: 

Used to collect data from Social Media websites to understand people’s behavior, and sentiments and discover what topics are trending.

### Contact Information: 

Used to collect contact information including names and email addresses to send bulk emails to potential customers.

### Job listings: 

Used to collect details about job openings and interviews from different websites and then show information in one place that is easily accessible for the user.

### Movie Reviews: 

Used to collect information about movies to help decide which movies are popular and highly rated.

## Is Web Scraping Legal?

> In 2019, the US Court of Appeals denied LinkedIn’s request to prevent HiQ, an analytics company, from scraping its data. The decision was important in the data privacy and data regulation areas. It showed that any data that is publicly available and not copyrighted is available to web crawlers.

Some websites allow web scraping but some prohibit access to their websites. To find out whether a website allows web scraping, look at the website's "`robots.txt`" file. You can find this file by appending "`/robots.txt`" to the main URL that you want to scrape.

The file for this project can be accessed through `https://www.boxofficemojo.com/robots.txt`.

```txt
# robots.txt for BoxOfficeMojo
User-agent: *
Allow: /
```

More information about `robots.txt` rules at [here](https://developers.google.com/search/docs/advanced/robots/create-robots-txt).

---

# Overview of Selenium

We need to review some basic information on Selenium. The `HTML` content of the webpages will be parsed and scraped using Selenium. 

Selenium is a **python library** that can scrape data on websites dynamically. It can also be used for web automation & testing. Scraping data from the web is only a small portion of the Selenium library. 

Some of the features of Selenium include:

* Multi-Browser Compatibility
* Multiple Language Support
* Handling of Dynamic Web Elements
* Easy to Identify Web Elements
* Speed and Performance
* Open Source and Portable

Learn more about Selenium at [here](https://selenium-python.readthedocs.io/).

Selenium web driver offers a variety of locater functions to locate elements on the web page. For this project, we will be locating data elements using the `XPath` function. `XPath` is a language used for locating data values within `HTML` tags and attributes like `class`, `id`, and `name`.

The syntax for the `XPath` function is shown below.

```txt
Xpath = //tagname[@Attribute='Value']

//        ➡ Select Current Node
tagname   ➡ Tagname like div, td, tr
@         ➡ Selects attribute
Attribute ➡ Attribute name (class, id, name, etc)
value     ➡ value of the attribute
```

Assume that the data we want to extract is as below in `HTML` view:

```html
<div class='movie'>
    <a class='drama' href='IMDB.com'> IMDB</a>
</div>
```

Our code will be like this in `py`:

```py
# This will return the HTML with tag div and class movie in a list.
Xpath = //div[@class='movie']

# This will return all the links with class drama inside the div tag that has a class of movie.
Xpath = //div[@class='movie']/a[@class='drama']
```