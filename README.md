# 🚀  fxxx-work-report 🚀 
Python script - used to generate weekly and monthly reports of commit records of all Git repositories under specified file directories for a specified Git account.
### The script comes with functions that remove duplicate commit records, replace prefixes such as feat: fixed:, and remove duplicate commit records.
Configure the following parameters in the script:
````python
# Local git account
git_username = "nicezz"

# List of git project paths to search
project_paths = [
    "/Users/nicezz/IdeaProjects/",
    "/Users/nicezz/WebstormProjects/"
]

# Path to save the records
output_path = "/Users/nicezz/temp/"
````
### After executing the main method, a report document will be generated in the directory specified by output_path.
<img width="400" alt="image" src="https://user-images.githubusercontent.com/22947965/227078731-ab4f526f-e343-4e0d-b6c7-e15f910fdee5.png">
