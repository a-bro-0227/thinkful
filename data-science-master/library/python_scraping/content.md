---
title: Web scraping
author: Thinkful
team: grading
time: 120 minutes
uuid: fc32d339-9fbd-45a1-bf01-441a31735ab6
timeHours: 2
---

So far in this module, you have learned how to get data from web APIs. In some situations, however, the data that you need for analysis may not be readily available. In this case, you'll need to cobble the data together from wherever you can get it. 

One option is to find the data on the web. Similar to the way that a person may browse the web, follow links, and read the data on web pages, a program may be written that can follow links, find data on pages, and download that data for processing. This process is called *web scraping*.

Programs that have the ability to automatically follow links on web pages and parse the data on a web page are generally called *web crawlers* or *spiders*. Think of your favorite search engine. How does it get information about the web pages that exist on the web for you to search? It uses web crawlers that simply follow every possible link on every web page that they can find, read the pages, try to summarize their meaning, and store this information for you to search.

In Python, you can write a similar program, but not for crawling the entire web. That would take way too long and cost way too much. [Netcraft estimates](https://news.netcraft.com/archives/2019/01/24/january-2019-web-server-survey.html) that there are over 1.5 billion unique domain names and close to 200 million active websites in the world today. The amount of data on the web today is measured in sextillions of bytes, or *zettabytes*.

Instead, focus on very specific web pages with very specific data that may be useful to you. For example, you may scrape articles from a variety of news sites to perform analyses on trending stories, or you may scrape comments from popular review sites to find out how public sentiment leans toward an organization. There are an infinite number of questions that can be asked and answered from the data that is available in public-facing websites, if you only know how to get that data.

In this checkpoint, you will look at using Python to find and download web pages of interest, parse those pages for data, and store that data in a format that makes it easy to process later. This checkpoint, like the previous two, focuses mainly on getting the data, rather than the processing that is done after the data has been retrieved.

## Dos and don'ts

Before you dive into scraping the web, there are a few things to be aware of. Public-facing websites are owned by organizations that provide the data for their own purposes, and they pay money to make these sites available. Your web scraper will have an impact on those websites, and as such, you should be respectful to the owners.

This article from [the Scrapinghub blog](https://blog.scrapinghub.com/2016/08/25/how-to-crawl-the-web-politely-with-scrapy) summarizes some of the rules that you should follow when building any web scraper. For convenience, a few points are listed here:


1. **Comply with rules from `robots.txt`:** Many websites contain a file named `robots.txt` that defines rules for automated access to the website. The website owner may specify that certain parts of the website should not be crawled, or that certain crawlers are not allowed. Whatever the rules are, you should respect them.
2. **Deliberately go slow:** A program can request pages from a website much faster than a human. If your scraper is accessing pages too quickly, your requests may overwhelm the server and prevent legitimate users from using the website. This is known as a *denial of service attack*. You, of course, do not want to be the source of such an attack against a website. Many sites have tools to recognize an attack of this sort, and they may actively take steps like banning your IP address to protect against such attacks. Simply introducing an artificial delay—for example,  waiting five seconds before requesting a second page—can help prevent this.
3. **Identify yourself:** Provide information about yourself, such as a web page that describes the purpose of your web crawler and an email address so that the website owner can contact you.
4. **Ask first:** If you expect to scrape a lot of information from a website, you can contact the website owner and ask first. Explain the purpose of your crawler, how you intend to use the data, and maybe how your work could even benefit the website. Then, be respectful of whatever rules or restrictions the website owner puts in place.
5. **Check for an API:** Many organizations with interesting data to share will create an API for you to consume their data. Before scraping, check if an API exists.
6. **Stick to public pages:** Remember, if you cannot browse to a page in your browser, then chances are that the page is deliberately not available to the public. In this case, you should not access it with your scraper.

By following these guidelines, you can conscientiously scrape websites. Note that if you do not pay close attention to what you are and are not allowed to do on a website, there is a real danger of wandering into illegal territory with web scraping. Be respectful.


## The scraping process

To properly parse websites for data, you will need to perform a few steps:

1. Identify the website where the data is located.
2. Verify that scraping the data does not violate the site's policies.
3. Manually examine the website with Chrome Developer Tools.
    - Learn the HTML structure of the site.
    - Learn how the data is requested by the site. How is the URL of the website structured to get the data?
4. Use the Requests library to fetch the HTML code of the website.
5. Use the Beautiful Soup library to parse the HTML and extract the content.
6. Follow links to get more data.
7. Store the data in a file for future analysis.

In this checkpoint, you will look at two examples. First, you'll see how to scrape a list of jokes from a website. The video below shows an example using [this page](http://pun.me/pages/funny-jokes.php), but it's recommended that you use [this page](https://www.ducksters.com/jokes/knockknock.php) instead in order to avoid recently reported certificate errors. Then, you will scrape a list of jobs from the [Stack Overflow Jobs site](https://stackoverflow.com/jobs).

<jupyter notebook-name="python-scraping" course-code="DSBC"></jupyter>

Check out the video below for a screencast demonstration of the topics covered in this checkpoint.

<iframe id="kaltura_player_1590583365" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590583365&entry_id=1_e2hp0wnb" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


