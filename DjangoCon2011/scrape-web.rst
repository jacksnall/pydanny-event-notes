==================
Scraping the Web
==================

by Katharine Jarmul

 * Co-Founder and VP of PyLadies
 * twitter.com/kjam
 
Content is what you need
===========================

 * You need to get content
 * good content exists all over the web
 * Scrape it!
 
lxml
=====

 * lxml.etree good for good formatted xml
 * fast for SOAP or other xml-formatted content
 
.. sourcecode:: python

    def parse_feed_titles(rss_feed):
       data = [] 
       dochtml = html.document_fromstring(rss_feed)
       for x in dochtml.cssselect('title'):
            data.append(x)