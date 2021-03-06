# Pinterest Image Scraper

Now you can take the URL to any Pinterest board (or a CSV of a bunch of boards) and return a Python list of the URLs to the hi-rez versions of all of the images on the board.

## Requirements:

- Python 3
- Selenium (pip install selenium)
- [Chrome driver](https://sites.google.com/a/chromium.org/chromedriver/) ( Download and place in the directory) or Firefox: `brew install chromedriver`
- aria2c (a command line download utility)
	- Mac: `brew install aria2`
	- Ubuntu: `sudo apt-get install aria2`
	- Centos/Fedora: `sudo yum install aria2`

- A [Pinterest](http://www.pinterest.com) Account

## How to Run:

- `mv ./config_sample.py ./config.py`

- Add your username / password to config.py

- Then use:
	- `python scraper.py <search term | board url> <how many scroll down [default=1]> <destination folder[optional]>`
- For example: 
	- `python scraper.py "Persian cats" 5 ./persian_cats`
	- `python scraper.py https://pinterest.com/kuxbini/cute-pets/ 5 ./persian_cats`
	
## Use in a script

```
import scraper as s
ph = s.PinterestHelper(PINTEREST_USERNAME, PINTEREST_PASSWORD)

# Returns an array of image urls
images = ph.runme("Persian Cats")

# Use a image board url instead
images = ph.runme("https://pinterest.com/kuxbini/cute-pets/")
```