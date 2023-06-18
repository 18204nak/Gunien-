# Gunien
import requests

def get_user_repositories(username):
    url = f"https://api.github.com/users/{username}/repos"
    response = requests.get(url)
    
    if response.status_code == 200:
        repositories = response.json()
        for repo in repositories:
            print(repo['name'])
    else:
        print(f"Error: {response.status_code}")

# Replace 'YOUR_USERNAME' with your GitHub username
get_user_repositories('YOUR_USERNAME')

