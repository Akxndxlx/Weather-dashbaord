Tech Stack

1. Python
The core programming language used for implementing the logic of the application. Python's simplicity and a vast library ecosystem make it an ideal choice for such projects.
2. Amazon Web Services (AWS)
Amazon S3 (Simple Storage Service):
Used for storing the fetched weather data as JSON files. The application can create an S3 bucket dynamically and store files organized by city and timestamp.
Boto3:
AWS SDK for Python that facilitates interaction with S3. It is used to check for the existence of the bucket, create it if necessary, and upload the weather data.
3. OpenWeatherMap API
Provides weather data for cities across the globe.
The API is accessed using HTTP requests, and responses are parsed to extract details such as temperature, humidity, and weather conditions.
4. dotenv
python-dotenv:
This library loads environment variables from a .env file into the application. Sensitive credentials, such as the OpenWeatherMap API key and AWS credentials, are securely managed using this method.
5. Requests
A Python library for making HTTP requests to external APIs (OpenWeatherMap). It handles parameter encoding, response validation, and error handling seamlessly.
6. JSON
Used for structuring and storing the weather data. The weather responses are parsed into Python dictionaries, manipulated, and saved as JSON files in the S3 bucket.



Features

1. Weather Data Fetching
The application fetches real-time weather data from the OpenWeatherMap API for a predefined list of cities (e.g., London, Dublin, Berlin). It retrieves:

Current temperature
Feels-like temperature
Humidity
Weather conditions (e.g., clear sky, rain)

2. Cloud Storage with Amazon S3
Weather data is saved to an S3 bucket with a clear directory structure: Each city's data is saved with a timestamp-based filename, e.g., weather-data/London-20250111-163500.json.

3. Secure Environment Variable Management
Sensitive credentials such as the OpenWeatherMap API key and AWS access keys are securely loaded using dotenv, ensuring these details aren't hard-coded in the application.

How It Works

Environment Setup:
The .env file stores sensitive information:

OPENWEATHER_API_KEY=your_openweathermap_api_key
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_BUCKET_NAME=your_bucket_name

Initialize Application:
The WeatherDashboard class is instantiated. AWS S3 client is initialized using the Boto3 library.

Create S3 Bucket:
If the bucket doesn’t already exist, the application creates it.

Fetch Weather Data:
Weather data for predefined cities is fetched from the OpenWeatherMap API.

Save to S3:
The weather data is saved in JSON format to the S3 bucket under a timestamped filename.

Display Results:
Weather data, including temperature, humidity, and conditions, is printed to the console.

How to Run
Clone the repository:
git clone https://github.com/your_username/weather-dashboard.git
cd weather-dashboard

Set up the environment:
Create a .env file in the root directory and populate it with your credentials:
OPENWEATHER_API_KEY=your_openweathermap_api_key
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_BUCKET_NAME=your_bucket_name

Install dependencies:
pip install -r requirements.txt
Run the application:
python weather_dashboard.py
