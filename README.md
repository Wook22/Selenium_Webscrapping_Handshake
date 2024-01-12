# Selenium_Webscrapping_Handshake
JerseySTEM Webscrapping project using Selenium

## Data Extraction and Google Sheets Integration

### Overview

This Python script is designed to perform data extraction from a web source, process the data, and then upload it to a Google Sheets document. The process includes authentication, data extraction, and Google Sheets integration.

### Prerequisites

Before running the script, make sure you have the necessary Python libraries installed. You can install them using the following:

```
pip install pandas gspread oauth2client beautifulsoup4 selenium
```

Additionally, ensure that you have the appropriate drivers (e.g., ChromeDriver) installed and configured for Selenium.

### Usage

1. Authentication

The script begins by authenticating and authorizing access to Google Sheets using OAuth2.0. It assumes that you have the necessary credentials and permissions.

2. Data Extraction

The script extracts data from a specified web source using Selenium and BeautifulSoup. It goes through multiple pages, extracts relevant information, and stores it in a Pandas DataFrame.

3. Google Sheets Integration

After extracting the data, the script creates a new worksheet in a specified Google Sheets document. It appends both the column names and the extracted data to the worksheet.

4. Usage Example

```
# Authenticate and authorize access to Google Sheets
auth.authenticate_user()
creds, _ = default()
gc = gspread.authorize(creds)

# ... (other setup code)

# Extract and send data to Google Sheets
final_df = extract_data(driver)
send_to_google_sheets(final_df)
```

### Configuration

* login(search_url, account_email, account_password): The login function authenticates the user and returns the Selenium WebDriver.

* extract_data(driver): The main function for data extraction. It navigates through pages, extracts data, and returns a Pandas DataFrame.

* send_to_google_sheets(final_df): This function sends both column names and data to a new worksheet in a Google Sheets document.

* Adjustments: Modify the script to fit your specific use case, including updating URLs, login credentials, and any other parameters as needed.

### Notes

* Selenium Driver: Ensure that you have the appropriate web driver (e.g., ChromeDriver) installed and configured. Update the driver path accordingly.

* Google Sheets URL: Replace SOURCE_SHEET with the URL of the Google Sheets document where you want to store the extracted data.

### License

This script is released under the MIT License.