### Web Crawler Design
- Primary purpose is to build a search engine
- Crawl the entire web - billions of pages
- We need to store the html at least for every page we crawl
- Ignore storing images and dynamic client side rendered content for now but make sure design can evolve for that


## High Level Design Considerations
- URL Frontier to store all urls to be visited -  can be a simple queue for poc but needs to be a distributed queue like kafka/etc for internet scale. There will be an initial seed urls
- Fetcher - for every URL in the frontier, fetcher makes a call (http) to the url and gets the page
- Parser -  parses every url content and stores the content and also any other hyperlinks in the parser
- data store to store all visited urls, content and key words and hyperlinks associated with each  url
- failed urls -  any failed urls go here
- politeness -  crawlers must respect the robots.txt policies in the web page to not get banned
- hashing url and the content to ensure same urls or duplicate pages are not crawled
- dynamic scheduling  to ensure different pages are re-visited at different rates
