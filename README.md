# Chargetracker

A scraper built to scrape information about EV charger usage between two locations in Sweden.

## Description

Chargetracker is a scraper that scrapes information from the webpage [Chargefinder](https://chargefinder.com/se) and track usage data from EV charger stations between two locations. The shortest route between two points are calculated using Chargefinders algorithms and then Chargefinder lists all EV chargers available on the road between these two points. This data is then scraped and information about the usage is outputted into an excel based on 3 statuses:

* LEDIG
* UPPTAGEN
* OTILLGÄNGLIG

The excel wb is being updated with sheets that is named based upon the inputs

## Installation

```shell
# Download the scraper
git clone https://github.com/Liimpo/Chargetracker

# (Optional) Create a virtual environment
python3 -m venv /path/to/Chargetracker
source /path/to/Chargetracker/bin/activate

# Install packages with pip
pip3 install -r requirements.txt
```

## Usage

### Running the script

To be able to run the script properly the user must pass two locations into the script. If a specific street is used then the location should be seperated with a __-__

```shell
# Running the scraper using two city locations
python3 chargetracker.py Göteborg Stockholm

# Running the scraper using one city (starting from a specific street) location and one city location
python3 chargetracker.py Linnégatan-Göteborg Stockholm
```

### Output examples

This section is dedicated to display what data is being scraped and how it is outputted inside the excel document.

<img src="https://i.imgur.com/zazfNXB.png" width="700">

This image display the original use of [Chargefinder](https://chargefinder.com/se). The two locations used in this image is Göteborg and Stockholm, the dots on the map are all available EV charging stations between these locations

<img src="https://i.imgur.com/sncC17R.png" width="700">

This image is an example output of the same two locations when the script has been executed during different times. If the same locations are used over multiple run, the data is being stored inside of the same sheet. If two other location combinations are used, a new sheet will be created in the same Workbook that contains the data that belongs to the specific combination
