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

1. Our first Spider => add `quotes_spider.py`
1. How to run our spider => go to the project’s top level directory and run: `scrapy crawl quotes`
1. A shortcut to the start_requests method => shrink the `quotes_spider.py` (can check it on the git history)).
