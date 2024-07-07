# Predicate Logic Code for Python

This repo contains the code for the predicate logic project.



## To use the code the logic.py file:
```python
import requests
import os

# Function to download a file from a URL
def download_file(url, save_path):
    # Send a GET request to the URL
    response = requests.get(url, stream=True)

    # Check if the request was successful
    if response.status_code == 200:
        # Open the file in write-binary mode
        with open(save_path, 'wb') as file:
            # Write the content of the response to the file
            for chunk in response.iter_content(chunk_size=8192):
                file.write(chunk)
        print(f"File downloaded and saved as {save_path}")
    else:
        print(f"Failed to download file. HTTP status code: {response.status_code}")

# Example usage
file_url = 'https://raw.githubusercontent.com/ronishg27/predicate-logic-python/main/logic.py'
save_location = '/content/logic.py'

download_file(file_url, save_location)
```