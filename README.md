1. Identified the Data Source
I used the URL:
https://github.com/trending 
This page lists public repositories for the GitHub user usernameakhil, sorted by last updated by default.

2. Fetched the Page Using requests
I sent an HTTP GET request to the URL using Python’s requests library with a browser-like User-Agent header to avoid blocking.

3. Parsed the HTML with BeautifulSoup
Using BeautifulSoup, I loaded and parsed the HTML content, then searched for:
<li> elements with class "public" – which represent each repo.
Inside those, I extracted:
The <a> tag with itemprop="name codeRepository" to get the repo name
Constructed the full repo link from the relative href
I sliced the list to keep only the top 5 repositories.

4. Saved the Results to CSV
I used Python’s built-in csv module to write the extracted data to top5_repos.csv, with headers:
Repository Name

Link
5. Tested and Verified
I printed a confirmation message and verified that the file was created with the correct contents.


