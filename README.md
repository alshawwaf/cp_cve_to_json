# Check Point Advisories to JSON Format

## THis project includes two example scripts. The goal is to scap the list of IPS advisories from https://advisories.checkpoint.com/advisories/ and export the list of CVEs to a json format.

### THe first script uses the BeautifulSoup pythin library. However the challenge comes from human identificaton protection used by Check Point to prevent unwanted scaping by bots.

### to solve this, the second script uses selenium to scap the advisory pages. We have around 4 pages as of January 2025. The tool will lunch an automated browser with human verification that can be clicked by the user, making the scaping successful.
