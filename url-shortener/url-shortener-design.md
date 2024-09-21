## Use Cases
User enters a URL in a UI and gets a short version of URL back. 
System would need to maintain a mapping of every URL to its short URL
Support update of URL
Vanity URLs -  if user enters a custom url, check if it is ready to use and then grant
Retention policy -  at least one click per month? is that fine?
A UI, an API and a database
a domain server + 8 letters (26 + 10 = 36)  -- 2 trillion urls  // 6 letters = 2 billion  // 7 letters = 80 billion // 8 letters = 2 trillion
url redirection -  when any user enters short url, our server should route it to the original url
Scale: 
 - billion urls to start with
 - at any time, we support 1000 users hitting UI at the same time? how will this be handled?

 - 


