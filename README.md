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

