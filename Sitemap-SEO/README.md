**sitemap.vm**

* Creates an XML document that helps inform search engines about pages on their site that are available for crawling.
* XML schema for the Sitemap protocol as described by http://www.sitemaps.org/protocol.html
    * Note: To include the XML declaration (`<?xml version="1.0" encoding="UTF-8"?>`) in the published Site Map, edit the Site Map Page's Configuration and check the option to " Include XML Declaration in Published Files".
* Works best with Index Block that indexes all Pages in the Site.
    * Xpath expression checks for Pages that are marked for publishing and have already been published.
* Google now ignores changefreq and priority so they are omitted.
