# Google-Images-Scraper
This Python script automates the process of scraping images from Google Images for products listed in a CSV file. 

Description

This Python script automates the process of scraping images from Google Images for products listed in a CSV file. It uses Selenium WebDriver to navigate Google Images, search for product images based on brand and name, and download up to a specified number of images per product. The images are saved in organized folders named by product ID, brand, and name. The script is designed to handle cookie consent dialogs, avoid duplicate images, and manage errors gracefully.

Features





Reads product data (ID, brand, name) from a CSV file.



Searches Google Images using Selenium WebDriver with Chrome.



Downloads up to a configurable number of images per product (default: 5).



Organizes images into folders named by product ID, brand, and name.



Sanitizes filenames to ensure compatibility with file systems.



Handles Google’s cookie consent dialog automatically.



Implements scrolling to load more images dynamically.



Filters out invalid or low-quality image URLs (e.g., base64 or thumbnails).

Requirements





Python 3.8+



Libraries: Install the required Python packages using:

pip install selenium requests



ChromeDriver: Download the ChromeDriver executable compatible with your Chrome browser version from here and specify its path in the script.



Google Chrome: Ensure the Chrome browser is installed.



CSV File: A products.csv file with columns id, brand, and name.

Setup





Clone the Repository:

git clone https://github.com/your-username/google-images-scraper.git
cd google-images-scraper



Install Dependencies:

pip install -r requirements.txt



Prepare the CSV File:





Create a products.csv file in the project directory with at least the following columns: id, brand, name.



Example products.csv:

id,brand,name
1,Nike,Air Max 270
2,Adidas,Ultraboost 21



Download ChromeDriver:





Download ChromeDriver from here.



Place it in a known location and update the CHROMEDRIVER_PATH variable in Scrapper.py with the full path to the executable.



Configure Paths:





Update CSV_FILE in Scrapper.py to point to your products.csv file.



Update SAVE_DIR to specify where downloaded images should be saved.



Example:

CSV_FILE = r'path/to/your/products.csv'
SAVE_DIR = r'path/to/save/images'
CHROMEDRIVER_PATH = r'path/to/chromedriver.exe'

Usage





Run the script:

python Scrapper.py



The script will:





Read the products.csv file.



For each product, search Google Images using the brand and name.



Download up to MAX_IMAGES (default: 5) images per product.



Save images in subfolders under SAVE_DIR, named as {id}_{brand}_{name}.

Project Structure

google-images-scraper/
├── Scrapper.py           # Main script for scraping and downloading images
├── products.csv          # Input CSV file with product data
├── requirements.txt      # List of Python dependencies
└── README.md             # This file

Example Output

For a product with id=1, brand=Nike, name=Air Max 270, images are saved in:

selenium_images/1_Nike_Air_Max_270/
├── img_1.jpg
├── img_2.jpg
...

Notes





Headless Mode: To run the browser without a GUI, uncomment the --headless option in the setup_driver() function.



Rate Limiting: The script includes delays (time.sleep) to avoid overwhelming Google’s servers. Adjust these if needed.



Error Handling: The script logs errors for failed downloads or missing data and continues processing other products.



Google Images Changes: Google’s page structure may change, requiring updates to CSS selectors in the google_images_search() function.

License

This project is licensed under the MIT License. See the LICENSE file for details.

Contributing

Contributions are welcome! Please submit a pull request or open an issue for suggestions or bug reports.

Author

Salman Nawaz Malik
