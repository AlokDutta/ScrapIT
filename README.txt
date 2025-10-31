##README

# Web Scraping Application

This is a web scraping application built with Flask that allows users to register, log in, and scrape data from web pages by specifying a URL. The scraped data is saved in a MongoDB database and can be filtered based on specific classes and saved to CSV files.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Routes and Functionalities](#routes-and-functionalities)
- [Acknowledgments](#acknowledgments)

## Features

- User registration and login with MongoDB for storing credentials.
- Scrapes HTML content based on classes found in the specified URL.
- Stores user scraping history with timestamp.
- Saves raw and filtered scraped data to CSV files.
- Allows users to search and filter HTML classes and generate filtered CSV files.
- Provides download links for saved data files.
- Session-based authentication and history tracking.

## Prerequisites

Before running this application, ensure you have the following installed:

- Python 3.6+
- MongoDB (running locally on `localhost:27017` by default)
- `pip` for installing dependencies

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/web-scraping-app.git
   cd web-scraping-app
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Start MongoDB**: Make sure MongoDB is running on `localhost:27017`.

4. **Run the Application**:
   ```bash
   python app.py
   ```

5. **Access the Application**: Open a web browser and go to `http://localhost:5000`.

## Usage

### 1. Register an Account
   - Go to the registration page, enter a username and password, and create an account.

### 2. Login
   - Log in with the registered credentials.

### 3. Scrape a Web Page
   - Enter a URL to scrape, and the application will gather all elements with classes in the HTML.
   - Scraped data is saved as a raw CSV file with the format `output_<username>.csv`.

### 4. Search and Filter Data
   - Specify a class to filter and view elements associated with that class.
   - Generate a new CSV file with only the filtered data.

### 5. Download Files
   - Download raw or filtered CSV files from the generated links.

### 6. View History
   - See a list of all previously scraped URLs with timestamps.

### 7. Logout
   - End the session and return to the login screen.

## Project Structure

   plaintext
web-scraping-app/
├── app.py                # Main application file
├── templates/            # HTML templates for Flask
│   ├── login.html        # Login page
│   ├── register.html     # Registration page
│   ├── search_url.html   # URL scraping input page
│   ├── search_string.html# Page to display and search scraped data
│   ├── search_class.html # Page for class-based data filtering
│   ├── history.html      # User scraping history page
├── static/               # Static files (CSS, JavaScript)
├── outputs/              # Folder to save output CSV files
│   ├── raw_data/         # Raw data CSV files
│   ├── filtered_data/    # Filtered data CSV files
├── get_class.py          # Utility functions for class search
├── generate_csv.py       # Utility functions for CSV generation
├── requirements.txt      # List of dependencies
└── README.md             # This README file

## Routes and Functionalities

 Route                  | Method | Description                                                 
 `/`                    | GET    | Renders the login page.                                     
 `/auth`                | POST   | Authenticates users and redirects to URL scraping page.     
 `/registration`        | GET    | Renders the registration page.                              
 `/create_account`      | POST   | Creates a new account and stores it in MongoDB.             
 `/scrap`               | POST   | Scrapes data from the specified URL.                        
 `/search_class`        | POST   | Filters and displays data based on a specified class.       
 `/generate_csv`        | POST   | Generates and saves a filtered CSV file.                    
 `/history`             | GET    | Displays user's scraping history.                           
 `/logout`              | GET    | Logs out the user and ends the session.                     
 `/download/raw_data`   | GET    | Provides download link for raw data CSV.                    
 `/scrap_web`           | GET    | Redirects to the URL scraping input page.                   

## Acknowledgments

- Flask documentation: [https://flask.palletsprojects.com/](https://flask.palletsprojects.com/)
- MongoDB documentation: [https://www.mongodb.com/docs/](https://www.mongodb.com/docs/)
- BeautifulSoup for web scraping: [https://www.crummy.com/software/BeautifulSoup/](https://www.crummy.com/software/BeautifulSoup/)

---
