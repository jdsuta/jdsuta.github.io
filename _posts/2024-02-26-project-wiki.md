---
layout: post
title:  "Wikipedia"
author: david
categories: [ Projects ]
image: assets/images/wiki.png
tags: [projects, django ]
comments: true
---

Wikipedia is a project built using the **Django** framework. It serves as a free online encyclopedia with various entries on diverse topics, each accessible through its respective page. For example, visiting `https://en.wikipedia.org/wiki/HTML`  displays the Wikipedia entry for HTML, with the requested page name specified in the route `/wiki/HTML`. Wikipedia stores entries in a human-friendly markup language **Markdown**, specifically Wikitext. However, when a user views an entry, the Markdown is converted into HTML for display, making the writing and editing process more user-friendly.

### Wikipedia in Action

Discover the capabilities of Wikipedia through this video presentation:

<p>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/4muNAK4nkGQ" frameborder="0" allowfullscreen></iframe>
</p>

### Personal Insights

To understand the **Django** framework, it is key to comprehend the relationship between `urls.py`, `views.py`, and `templates`

**`urls.py`**: This file is used to define the URL patterns for your Django project. It specifies how different URLs should be mapped to views.

**`views.py`**: This file contains the core logic of your application. It defines functions (views) that handle requests and return appropriate responses. Views are responsible for processing data, rendering HTML pages, and handling operations such as GET and POST requests.

**`templates`**: These are HTML files that serve as the presentation layer of your application. They define the structure and layout of the pages. Views interact with templates to dynamically generate HTML content based on the data processed in the backend.

In summary, **`urls.py`** handles URL routing, **`views.py`** manages the backend logic, and **`templates`** handle the presentation and layout of the HTML pages.


Additionally, django allows to create **applications** which is basically a module that. Each application can have its own models, views, templates, and static files, making it easier to manage and scale a project.

For this wiki the the requiremments where the followings:


#### Entry Page
Visiting `/wiki/TITLE`, where TITLE is the title of an encyclopedia entry, should render a page that displays the contents of that encyclopedia entry. The view should retrieve the content of the encyclopedia entry by calling the appropriate util function. If an entry is requested that does not exist, the user should be presented with an error page indicating that their requested page was not found. If the entry does exist, the user should be presented with a page that displays the content of the entry. The title of the page should include the name of the entry.

#### Index Page
Update `index.html` such that, instead of merely listing the names of all pages in the encyclopedia, the user can click on any entry name to be taken directly to that entry page.

#### Search
Allow the user to type a query into the search box in the sidebar to search for an encyclopedia entry. If the query matches the name of an encyclopedia entry, the user should be redirected to that entry’s page. If the query does not match the name of an encyclopedia entry, the user should instead be taken to a search results page that displays a list of all encyclopedia entries that have the query as a substring. For example, if the search query were "ytho," then Python should appear in the search results. Clicking on any of the entry names on the search results page should take the user to that entry’s page.

#### New Page
Clicking “Create New Page” in the sidebar should take the user to a page where they can create a new encyclopedia entry. Users should be able to enter a title for the page and, in a textarea, should be able to enter the Markdown content for the page. Users should be able to click a button to save their new page. When the page is saved, if an encyclopedia entry already exists with the provided title, the user should be presented with an error message. Otherwise, the encyclopedia entry should be saved to disk, and the user should be taken to the new entry’s page.

#### Edit Page
On each entry page, the user should be able to click a link to be taken to a page where the user can edit that entry’s Markdown content in a textarea. The textarea should be pre-populated with the existing Markdown content of the page. The user should be able to click a button to save the changes made to the entry. Once the entry is saved, the user should be redirected back to that entry’s page.

#### Random Page
Clicking “Random Page” in the sidebar should take the user to a random encyclopedia entry.

#### Markdown to HTML Conversion
On each entry’s page, any Markdown content in the entry file should be converted to HTML before being displayed to the user. You may use the `python-markdown2` package to perform this conversion, installable via `pip3 install markdown2`.


To check code and implementation please check [github project Wiki][github-wiki]{:target="_blank"} 

[github-wiki]: https://github.com/jdsuta/projects/tree/main/wiki