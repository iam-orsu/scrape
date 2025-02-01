
Here are the solutions for the web scraping questions based on https://cipherlegion.com/:

1. Scrape the title of the webpage.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
title = soup.title.string

print('Title of the page:', title)
2. Extract all the links from the homepage.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
links = soup.find_all('a')

for link in links:
    print(link.get('href'))
3. Scrape the first heading (e.g., <h1> or <h2>) from the homepage.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
first_heading = soup.find(['h1', 'h2'])

print('First heading:', first_heading.text.strip())
4. Extract all the text inside the paragraphs.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
paragraphs = soup.find_all('p')

for paragraph in paragraphs:
    print(paragraph.text.strip())
5. Scrape the social media links from the website.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
social_links = soup.find_all('a', href=True)

# Filter out social media links (e.g., Facebook, Twitter)
social_media_keywords = ['facebook', 'twitter', 'instagram', 'linkedin']
for link in social_links:
    href = link['href']
    if any(keyword in href for keyword in social_media_keywords):
        print(href)
6. Scrape the first image on the homepage.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')
first_image = soup.find('img')

if first_image and 'src' in first_image.attrs:
    print('First image URL:', first_image['src'])
else:
    print('No image found.')
7. Extract and print the content of the "About Us" section.
Solution:

python
Copy
Edit
import requests
from bs4 import BeautifulSoup

url = 'https://cipherlegion.com/'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')

# Try to find the "About Us" section or similar, based on the page structure.
about_section = soup.find('section', {'id': 'about'})

if about_section:
    print(about_section.text.strip())
else:
    print("About Us section not found.")
