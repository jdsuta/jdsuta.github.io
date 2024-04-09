---
layout: post
title:  "Commerce"
author: david
categories: [ Projects ]
image: assets/images/commerce.png
tags: [projects, django, featured ]
comments: true
---

Commerce is an e-commerce auction site developed using the **Django** framework. It enables users to create auction listings, place bids, comment on listings, and manage their watchlist. The site leverages Django's Object-Relational Mapper (ORM), which provides a higher level of abstraction over SQL, allowing developers to interact with databases using Python classes and objects rather than direct SQL queries. Additionally, the Django admin interface was utilized to streamline data management tasks, enhancing the overall user experience.

## Commerce in Action

Discover the capabilities of Commerce through this video presentation:

<p>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/iF7C4d7ti70" frameborder="0" allowfullscreen></iframe>
</p>

### Personal Insights

In general, the project utilized Django's models, admin interface, and Bootstrap for styling, alongside other key features offered by Django.

The typical commands used during development were:

```
python manage.py runserver
python manage.py makemigrations
python manage.py migrate
python manage.py shell (primarily for querying the database and testing)
python manage.py createsuperuser (to create a superuser and access the Django admin interface at http://127.0.0.1:8000/admin/)
```

Models were defined in the `models.py` file, and forms were generated directly from the models using `forms.py`. Interestingly, a global variable was stored in the `context_processors.py` file to be passed to all templates. It was necessary to add `'auctions.context_processors.watchcount_processor'` in the `settings.py` file under TEMPLATES > OPTIONS > context_processors.

The `@login_required` decorator was used on top of views to ensure that only logged-in users could access those views.

For the general styling of the page, Bootstrap 4 was utilized, including components such as the navbar, cards, and buttons. However, CSS was employed for specific scenarios, such as overlaying a layer and text on top of items being auctioned to indicate when a bid was closed or when a user was the winner of a bid if they had the highest auction.

Below is an example of the overlay style:

```
.success-overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(10, 162, 243, 0.1); /* Opacity adjusted to make it appear inactive */
    pointer-events: none; /* Allows interaction with elements under the card */
    z-index: 1; /* Ensures the overlay appears above other content */
}
```
Understanding the [z-index][z-index]{:target="_blank"} property was crucial, along with catching the difference between absolute and relative positioning and how they function. 

During troubleshooting, I utilized VS Code. Additionally, I created a virtual environment and a debugger launch profile (https://code.visualstudio.com/docs/python/tutorial-django) for efficient debugging.


### Specification for this project:

#### Models:

Your application should have at least three models in addition to the User model: one for auction listings, one for bids, and one for comments made on auction listings. It’s up to you to decide what fields each model should have, and what the types of those fields should be. You may have additional models if you would like.

#### Create Listing: 

Users should be able to visit a page to create a new listing. They should be able to specify a title for the listing, a text-based description, and what the starting bid should be. Users should also optionally be able to provide a URL for an image for the listing and/or a category (e.g. Fashion, Toys, Electronics, Home, etc.).

#### Active Listings Page: 

The default route of your web application should let users view all of the currently active auction listings. For each active listing, this page should display (at minimum) the title, description, current price, and photo (if one exists for the listing).

#### Listing Page: 

Clicking on a listing should take users to a page specific to that listing. On that page, users should be able to view all details about the listing, including the current price for the listing.

- If the user is signed in, the user should be able to add the item to their “Watchlist.” If the item is already on the watchlist, the user should be able to remove it.
- If the user is signed in, the user should be able to bid on the item. The bid must be at least as large as the starting bid, and must be greater than any other bids that have been placed (if any). If the bid doesn’t meet those criteria, the user should be presented with an error.
- If the user is signed in and is the one who created the listing, the user should have the ability to “close” the auction from this page, which makes the highest bidder the winner of the auction and makes the listing no longer active.
- If a user is signed in on a closed listing page, and the user has won that auction, the page should say so.
- Users who are signed in should be able to add comments to the listing page. The listing page should display all comments that have been made on the listing.

#### Watchlist: 

Users who are signed in should be able to visit a Watchlist page, which should display all of the listings that a user has added to their watchlist. Clicking on any of those listings should take the user to that listing’s page.

#### Categories: 

Users should be able to visit a page that displays a list of all listing categories. Clicking on the name of any category should take the user to a page that displays all of the active listings in that category.

#### Django Admin Interface:

Via the Django admin interface, a site administrator should be able to view, add, edit, and delete any listings, comments, and bids made on the site.


To check code and implementation please check [github project Commerce][github-commerce]{:target="_blank"} 

[github-commerce]: https://github.com/jdsuta/projects/tree/main/commerce
[z-index]: https://developer.mozilla.org/en-US/docs/Web/CSS/z-index