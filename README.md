# Web Scraping Solutions for CipherLegion

Here are the solutions for web scraping tasks based on the website [CipherLegion](https://cipherlegion.com/):

## 1. Scrape the title of the webpage
### Solution:

```python
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
title = soup.title.string

print('Title of the page:', title)
