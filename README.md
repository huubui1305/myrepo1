import os
import requests

def download_images(image_urls, folder):

    if not os.path.exists(folder):
        os.makedirs(folder)

    for i, url in enumerate(image_urls):

        img = requests.get(url)

        filename = os.path.join(folder, f"page_{i+1}.jpg")

        with open(filename, "wb") as f:
            f.write(img.content)

        print("Downloaded:", filename)
