import requests

API_URL = "https://api.jikan.moe/v4/manga"

def search_manga(name):

    params = {"q": name}

    response = requests.get(API_URL, params=params)

    data = response.json()

    results = []

    for item in data["data"][:5]:

        results.append({
            "title": item["title"],
            "url": item["url"],
            "chapters": item.get("chapters")
        })

    return results
