# Best practices for web scraping

The below informations are with reference to relevant blog posts on [zyte.com](https://www.zyte.com/learn/web-scraping-best-practices/) and [itgovernance.eu](https://www.itgovernance.eu/blog/en/the-gdpr-legitimate-interest-what-is-it-and-when-does-it-apply).

A lot of people says that scraping is a legal grey area, but the truth is scraping itself isn't illegal. It's the manner in which you scrape and what you scrape that falls into the grey area.

# Practice 1: Don't Be a Burden

> Web *Scraping* Rule: Do **NOT** harm the website.<br>
> Web *Crawling* Rule: Do **NOT** harm the website.

This means that the volume and frequency of queries you make should not burden the website's servers or interfere with the website's normal operations.

You can accomplish this in a number of ways:

1. Limit the number of concurrent requests to the same website from a single IP.
2. Respect the delay that crawlers should wait between requests by following the crawl-delay directive outlined in the `robots.txt` file.
3. If possible it is more respectful if you can schedule your crawls to take place at the website's off-peak hours.

A crucial aspect of this rule is providing the web administrators of the websites you scrape with an easy way to contact you. If you ever receive an abuse report from a website you are scraping you should either stop scraping the site or limit the scraping in order to rectify the abuse reported.

# Practice 2: Don't Violate Copyright

When scraping a website you should always consider whether the web data you are planning to extract is copyrighted.

> Copyright is defined as the exclusive legal right over a physical piece of work — like an article, picture, movie, etc. It basically means, if you create it, you own it. 

In order to be copyrightable, the work needs to be original.

The common types of material on the web that might be copyrighted are:

* Articles
* Videos
* Pictures
* Stories
* Music
* Databases

As a result, copyright is very relevant to scraping because much of the data on the internet (like articles and videos) are copyrighted works.

However, there are some situations when exceptions can apply to all or part of the data enabling it to be legally scraped without infringing on the owner's copyright.

## 1. Fair Use:

Fair use is an exception that permits limited use of copyrighted material. Typically, fair use includes categories such as criticism/parody, comment, news reporting, teaching, scholarship, and research. 

One example of fair use is the publishing of short snippets of articles with links, which is generally okay under the fair use exception due to the transformative and ***limited nature of the use***.

The factors commonly used to determine if the fair use exception applies are:

1. The purpose and character of your use (ie: is it transformative in some way).
2. The nature of the work (ie: fact vs fiction / published vs unpublished) .
3. The amount taken, the less you copy the better.
4. The effect upon the potential market, meaning the extent to which your use may deprive the owner of income or a potential market opportunity.

## 2. Transformative Use:

One factor in determining fair use is whether the usage is transformative. 

Instead of distributing and storing exact duplicates or lengthy portions of the crawled website, ***transform the content*** and the use of it in some way so that you are not violating copyright.

## 3. Facts:

The facts within copyrighted material are often not covered by copyright laws, so if you limit what is being scraped to just the ***factual matters*** (ie: names of products, price, etc), then it is acceptable to scrape.

Note that different countries have different exceptions to copyright law, and you should always ensure that an exception applies within the jurisdiction within which you're operating.

# Practice 3: Don't breach GDPR

The introduction of GDPR completely changes how you can scrape the personal data of EU citizens (and sometimes non-EU citizens as well). For a deeper explanation of how GDPR affects web scrapers, check out [Web Scrapers Guide to GDPR](https://www.zyte.com/blog/web-scraping-gdpr-compliance-guide/). This section will just outline the best practices when it comes to scraping personal data. 

Personal data is any data that can identify an individual person:

* Name
* Email
* Phone number
* Address
* User name
* IP address
* Bank or credit card info
* Medical data
* Biometric data

Unless you have a "lawful reason" to scrape and store this data, you will be in breach of GDPR if any of the scraped data belongs to EU residents. In the case of web scraping, the most common legal reasons are legitimate interest and consent.

## Legitimate Interest

Theoretically, it applies whenever an organisation uses personal data in a way that the data subject would expect.

For most companies, it will be very difficult for you to demonstrate that you have a legitimate interest in scraping someone's personal data.

In most cases, only governments, law enforcement agencies, etc. will have what would be deemed to be a legitimate interest in scraping the personal data of its citizens as they will typically be scraping people's personal data ***for the public good***.

## Consent

For consent to be your lawful reason to scrape a person's data, you need to have that person's explicit consent to scrape, store and use their data in the way you intended. This means that you or a 3rd party must have been in direct contact with the person and ***they agreed to terms*** that allow you to scrape their data.

An example of this would be companies like [mint.com](https://mint.intuit.com/), where users give Mint consent to log into their online banking accounts and retrieve their banking transactions so that they can be tracked and displayed in a more user-friendly format on Mint.com.

# Practice 4: Beware of Login and Website T&C (Terms and Conditions)

When you log in and/or explicitly agree to a website's terms and conditions you are entering into a contract with the website owner, thereby agreeing to their rules regarding web scraping. 

The rules can explicitly state that you aren’t allowed to scrape any data on the website. This means that you need to carefully ***review the terms and conditions*** you are agreeing to if your spiders have to log in to scrape data, as they could stipulate that you're not allowed to scrape their data. 

You should always honor the terms of any contract you enter into, including website terms & conditions and privacy policies.