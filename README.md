# scrapy-tutorial-workshop

following steps in <https://docs.scrapy.org/en/latest/intro/tutorial.html>

Previous Steps:

1. Init git repo
1. install virtualenv `virtualenv venv`
1. activate virtualenv `source venv/Scripts/activate` (on linux | can use git bash console on windows)
1. create requirements.txt file and add (only scrapy /ˈskreɪpaɪ/ is mandatory)
    1. scrapy
    1. ipython
    1. ~~pprint~~ => this is not necessary. pprint is part of the Python standard library
1. and install it with `pip install -r requirements.txt`

Steps:

1. Create a Project => `scrapy startproject tutorial`
    1. This will create a tutorial directory and contents.
    1. output:

        ```text
        New Scrapy project 'tutorial', using template directory 'D:\m01.repos\github.1\scrapy-tutorial-workshop\venv\Lib\site-packages\scrapy\templates\project', created in:
        D:\m01.repos\github.1\scrapy-tutorial-workshop\tutorial

        You can start your first spider with:
        cd tutorial
        scrapy genspider example example.com
        ```

1. Our first Spider => add the file `quotes_spider.py`
1. How to run our spider => go to the project’s top level directory and run: `scrapy crawl quotes`
1. A shortcut to the start_requests method => shrink the `quotes_spider.py` (can check it on the git history). Try running again the spider and the result will be the same
1. Extracting data => The best way to learn how to extract data with Scrapy is trying selectors using the Scrapy shell. Run: `scrapy shell 'https://quotes.toscrape.com/page/1/'`
    1. try inside the shell:

        ```python
        # inside the shell
        response.css("title")
        response.css("title::text").getall()
        response.css("title").getall()
        response.css("title::text").get()
        response.css("title::text")[0].get()
        response.css("noelement")[0].get()
        response.css("noelement").get()
        ```

    2. Besides the getall() and get() methods, you can also use the re() method to extract using regular expressions:

        ```python
        # inside the shell
        response.css("title::text").re(r"Quotes.*")
        response.css("title::text").re(r"Q\w+")
        response.css("title::text").re(r"(\w+) to (\w+)")
        ```

    3. In order to find the proper CSS selectors to use, you might find it useful to open the response page from the shell in your web browser using `view(response)`
    4. Besides CSS, Scrapy selectors also support using XPath expressions:

        ```python
        # inside the shell
        response.xpath("//title")
        response.xpath("//title/text()").get()

        ```
