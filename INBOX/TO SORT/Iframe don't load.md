https://stackoverflow.com/questions/6663244/cant-show-some-websites-in-iframe-tag

Since some websites have decided to disable embedding them in iframes theres nothing you can do with pure html solutions. 

You have to check for HTTP response header X-Frame-Option of those sites. if its value is "DENY or SAMEORIGIN", then you can not load those website in the iframes.

DENY = No one can load the website in iframe. Even the same domain page wont be able to load. 
SAMEORIGIN = only a page which is in same domain can load this website in iframe.
