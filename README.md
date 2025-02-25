# Check Point Advisories to JSON Format

This repository demonstrates **two** approaches to scraping [Check Point’s advisories site](https://advisories.checkpoint.com/advisories/) and extracting **CVE references** into a JSON file.

## Overview

1. **Script #1 (BeautifulSoup)**  
   - Uses `requests` and `BeautifulSoup` to retrieve and parse the site’s HTML.  
   - May fail because the site implements bot-protection or human-verification measures, which can block automated requests or return incomplete data.

2. **Script #2 (Selenium)**  
   - Launches a real browser (e.g., Chrome) via Selenium.  
   - Allows the user to **manually complete** any human-verification step (CAPTCHA, etc.).  
   - Once verified, Selenium collects data from **all** advisory pages (typically 4, as of January 2025).  
   - Extracts the advisory CVEs and writes them to a JSON file.

## Why Two Approaches?

- **BeautifulSoup** alone is simpler but often **blocked** by advanced bot-protection or CAPTCHAs.  
- **Selenium** simulates an **actual user** by running a browser. After manual verification, it can successfully gather the full advisory data.

## Setup & Usage

1. **Clone the repo**:
   
```bash
git clone https://github.com/alshawwaf/cp_cve_to_json.git
cd cp_cve_to_json
```

3. **Install dependencies (for both scripts)**:

```bash
# For BeautifulSoup script
pip install requests beautifulsoup4

# For Selenium script
pip install selenium webdriver-manager
```

3. **Run Script #1 (BeautifulSoup)**:

```bash
python scrape_bs4.py
If blocked, the script will likely fail to retrieve full data.
```
4. **Run Script #2 (Selenium)**:

```bash
python scrape_selenium.py
```

* A browser window will open.

![alt text](https://github.com/alshawwaf/cp_cve_to_json/blob/main/assets/advisories_scrap.jpg)
 
* Complete any verification prompts (CAPTCHA, “I’m not a robot,” etc.).
* The script will then scrape all advisories and export a JSON file containing the CVEs.


## Contributing
1. Fork this repository.
2. Create a feature branch (git checkout -b feature/something).
3. Commit your changes and push to GitHub.
4. Create a Pull Request describing your work.

License
MIT License

Disclaimer: This project is for educational/demonstration purposes only. Scraping any website should respect the site’s Terms of Service and all applicable legal requirements.
