# Web Scraping With Python :

![python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)

#### Project Setup

  - Making the project as :
    ```
    mkdir webscraping
	cd webscraping
    ```
  - Web Scraping installation:
     ```
     open command prompt type 
        pip install virtualenv
     create virtualenv
    	>>virtualenv web-scraping
     we need to activate virtualenv for use
    	>>web-scraping\scripts\activate
     
     need libraries for Web Scraping :
     
    pip install requests
	pip install beautifulsoup4 or install bs4
    ```
  - Create WebsiteScrap.py for development
     ```python
    import requests
    from bs4 import BeautifulSoup
    
    url = "https://www.learnpython.org/"
    
    response = requests.get(url)
    htmlContent = response.content
    formatted_html_content = BeautifulSoup(htmlContent, 'html.parser')
    
    # print(formatted_html_content)
    
    # 1} Get the title of the HTML page
    title = formatted_html_content.title
    print(title)
    # if you want only tag content
    print(title.string)
    
    # 2} find All anchor tag on this website and print count
    list_anchors = formatted_html_content.find_all('a')
    # print all anchor tags
    print(list_anchors)
    # print count
    print("Number of anchor tags on this website : ", len(list_anchors))
    
    # 3} Get first element in the HTML page
    print(formatted_html_content.find('head'))
    
    # 4} Get classes of any element in the HTML page
    print(formatted_html_content.find('a')['class'])
    
    # 5} find all the elements by class name
    print(formatted_html_content.find_all("a", class_="navbar-brand"))
    
    # 6} Get the text from the tags/soup
    print(formatted_html_content.find("p").get_text())
    
    # 7} Get all the anchor tags from the page with iteration
    list_anchors = formatted_html_content.find_all('a')
    all_links = set()
    for link in list_anchors:
        print(link)  # get all anchor tag with links
        print(link.get('href'))  # get all links
        all_links.add(link.get('href'))  # want to remove duplicate links
    
    print(all_links)
    print(len(all_links))
    # 8} find duplicate links
    all_web_links_count=len(list_anchors)
    after_remove_duplicate_links_count=len(all_links)
    print('Number of duplicate links in this website are : ',all_web_links_count-after_remove_duplicate_links_count)
     ```
  - In order to run app:
     ```
	   python WebsiteScrap.py
     ```
  - create clone in you system just execute this file
  	```
	1} create virtualenv and just type below command
	2} pip install -r .\requirements.txt
	```
