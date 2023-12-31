# Article Scraper API

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)

Oxylabs’ [Article Scraper](https://oxylabs.io/products/scraper-api/web/article-scraper?utm_source=github&utm_medium=repositories&utm_campaign=product) is a data gathering solution allowing you to extract real-time information from any website effortlessly. This brief guide explains how an Article Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can get article results in HTML form by providing your list of URLs to our service.

#### Python code example

The example below illustrates how you can obtain the HTML of an article from [oxylabs.io](https://oxylabs.io/blog/what-is-http-proxy).

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal',
    'url': 'https://oxylabs.io/blog/what-is-http-proxy'
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```
Find code examples for other programming languages [**here**](https://github.com/oxylabs/article-scraper/tree/main/code%20examples)

#### Output Example
```json
{
  "results": [
    {
      "content": "<!DOCTYPE html><html lang=\"en\"><head><meta charSet=\"utf-8\" /><meta name=\"viewport\" content=\"width=de ... </html>",
      "created_at": "2023-12-18 11:37:50",
      "updated_at": "2023-12-18 11:38:00",
      "page": 1,
      "url": "https://oxylabs.io/blog/what-is-http-proxy",
      "job_id": "7142478062620273665",
      "status_code": 200
    }
  ]
}
```
With our Article Scraper, you can seamlessly extract public data from any news or blog post. Gather critical information such as key facts, author attribution, or publication dates to expand your research and stay ahead of your competitors. If you have any queries or need assistance, don't hesitate to reach out to our support team through live chat or email us at hello@oxylabs.io.
