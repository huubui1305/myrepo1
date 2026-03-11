from search import search_manga
from downloader import download_images

name = input("Enter manga name: ")

results = search_manga(name)

print("\nSearch results:\n")

for i, r in enumerate(results):
    print(i+1, r["title"])

choice = int(input("\nSelect manga: ")) - 1

print("Selected:", results[choice]["title"])

# Example image URLs (replace with legal sources)
images = [
    "https://example.com/page1.jpg",
    "https://example.com/page2.jpg"
]

download_images(images, results[choice]["title"])
