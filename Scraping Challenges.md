# Scraping Challenges

Web scraping has become a hot topic among people with rising demands for big data. More and more people hunger for data from multiple websites to help with their business development. However, many challenges, such as blocking mechanisms, will rise when web scraping processes scale, which can hinder people from getting data. Let’s look at these challenges in detail.

---

## 01. Bot Access

The first thing to check is that if your target website allows for scraping before you start it. If you find it disallows for scraping via its `robots.txt`, you can ask the web owner for scraping permission, explaining your scraping needs and purposes. If the owner still disagrees, it’s better to find an alternative site that has similar information.

## 02. Complicated and Changeable Web Page Structures

Most web pages are based on `HTML` (Hypertext Markup Language). Web page designers can have their own standards to design the pages, so web page structures are widely divergent. When you need to scrape multiple websites, you need to build one scraper for each website.

Moreover, websites periodically update their content to improve the user experience or add new features, which often leads to structural changes on the web page. Since web scrapers are set up according to a certain design of the page, they would not work for the updated page. Sometimes even a minor change in the target website requires you to adjust the scraper.

## 03. IP Blocking

IP blocking is a common method to stop web scrapers from accessing data of a website. It typically happens when a website detects a high number of requests from the same IP address. The website would either totally ban the IP or restrict its access to break down the scraping process.

There are many IP proxy services like [Luminati](https://brightdata.com/), that can be integrated with automated scrapers, saving people from such blocking.

## 04. CAPTCHA

[CAPTCHA](https://en.wikipedia.org/wiki/CAPTCHA) (Completely Automated Public Turing test to tell Computers and Humans Apart) is often used to separate humans from scraping tools by displaying images or logical problems that humans find easy to solve but scrapers don’t.

Many CAPTCHA solvers can be implemented into bots to ensure non-stopping scrapes. Although the technologies to overcome CAPTCHA can help acquire continuous data feeds, they could still slow down the scraping process a bit.

## 05. Honeypot Traps

[Honeypot](https://en.wikipedia.org/wiki/Honeypot_(computing)) is a trap the website owner puts on the page to catch scrapers. The traps can be links that are invisible to humans but visible to scrapers. Once a scraper falls into the trap, the website can use the information it receives (e.g. its IP address) to block that scraper.

## 06. Slow / Unstable Load Speed

Websites may respond slowly or even fail to load when receiving too many access requests. That is not a problem when humans browse the site as they just need to reload the web page and wait for the website to recover. But scraping may be broke up as the scraper does not know how to deal with such an emergency.

## 07. Dynamic Content

Many websites apply [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) to update dynamic web content. Examples are lazy loading images, infinite scrolling and show more info by clicking a button via AJAX calls. It is convenient for users to view more data on such kind of websites but not for scrapers.

## 08. Login Requirement

Some protected information may require you to log in first. After you submit your login credentials, your browser automatically appends the cookie value to multiple requests you make the way most sites, so the website knows you’re the same person who just logged in earlier. So when scraping websites requiring a login, be sure that cookies have been sent with the requests.

## 09. Real-Time Data Scraping

Real-time data scraping is essential when it comes to price comparison, inventory tracking, etc. The data can change at the blink of an eye and may lead to huge capital gains for a business. The scraper needs to monitor the websites all the time and scrape data. Even so, it still has some delay as the requesting and data delivery take time. Furthermore, acquiring a large amount of data in real-time is a big challenge, too.

---

# Sources

1. [Octoparse Blog](https://www.octoparse.com/blog/9-web-scraping-challenges#)
