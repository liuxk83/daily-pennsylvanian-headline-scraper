# Git Scraper for the Daily Pennsylvanian Website

This repo contains a tool for scraping the headline of the newest "Student Life" article on the Daily Pennsylvanian website. It is copied from this [Git scraper template](https://github.com/jlumbroso/basic-git-scraper-template). A list of "Student Life" articles can be found [here](https://www.thedp.com/section/student-life). 

From the template, I made the following two changes in `script.py`:
1. First, I changed `req = requests.get("https://www.thedp.com")` (line 23) to `req = requests.get("https://www.thedp.com/section/student-life")`, since the desired headline is on the "Student Life" page, not the homepage.
2. Then, I changed `target_element = soup.find("a", class_="frontpage-link")` (line 29) to `target_element = soup.find("h3", class_="standard-link")`, because (1) the tag associated with the headline is `standard-link`, not `frontpage-link`, and (2) the tag is a part of the heading `h3`, not the actual link `a`. The returned text, however, will still be the text associated with the link (found by experimenting in `sandbox.ipynb`).