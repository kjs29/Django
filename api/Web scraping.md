# What is a web scraping?

`GET` the information from websites(html)

And Edit the information however I want (`Parse`)

# Is it legal? Illegal?

Any website owners won't be a big fan of their websits being scrapped since scrapping can make their websites slow,

So when there is `robots.txt` or official API, it is recommended to not scrap from their websites.

# `requests` module

Ultimately what we want to know is their `html` file for their websites.

In order to get their html files we have to request for it, and we use `requests` module.

How to see website's html file 

```py
import requests

url = "https://www.randomexample.com/"
res = requests.get(url)

# res.text

# save html file called examplewebsite.html
with open("examplewebsite.html", "w") as f:
    f.write(res.text)
```