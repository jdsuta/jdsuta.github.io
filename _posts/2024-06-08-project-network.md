---
layout: post
title:  "Network"
author: david
categories: [ Projects ]
image: assets/images/mail.png
tags: [projects, react, featured ]
comments: true
---

Network is a Twitter-like social network website for making posts and following users. Developed using the Django framework and React, it allows users to create posts, follow/unfollow users, like/unlike posts, edit their own posts, and view profiles.

## Network in Action

<p>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/Cxp1w1u0n-8" frameborder="0" allowfullscreen></iframe>
</p>

### Personal Insights

The project utilizes Django's models, admin interface, and other robust features alongside React, HTML, CSS, and Bootstrap for styling. It also incorporates pagination to enhance the user experience.

Here is an interesting piece of code to handle pagination:

```python

# Paginator to handle 10 posts per page. The page number is passed.

paginator = Paginator(posts, 10)
page_obj = paginator.get_page(page_number)

has_next = page_obj.has_next()
has_previous = page_obj.has_previous()

if has_next:
    next_page_number = page_obj.next_page_number()
else:
    next_page_number = -1

if has_previous:
    previous_page_number = page_obj.previous_page_number()
else:
    previous_page_number = -1 

data = {
    'posts': page_obj.object_list,
    'followers': number_followers,
    'following': number_following,
    'followed': followed,
    'page_number': page_obj.number,
    'num_pages': page_obj.paginator.num_pages,
    'has_next': has_next,
    'has_previous': has_previous,
    'next_page_number': next_page_number,
    'previous_page_number': previous_page_number
}
```

In react it was handled like this:

```jsx
{/* Paginator using Bootstrap */}
<br />
<nav aria-label="Page navigation example">
    <ul className="pagination justify-content-center">
        {has_previous ? (
            <>
                <li className="page-item">
                    {/* Profile(post.poster__id, post.poster__username, userid, page_number) */}
                    <a className="page-link" href="#" onClick={() => Profile(posterid, username, userid, 1)} aria-label="Previous">
                        <span aria-hidden="true">&laquo;</span>
                    </a>
                </li>
                <li className="page-item">
                    <a className="page-link" href="#" onClick={() => Profile(posterid, username, userid, previous_page_number)}>
                        {previous_page_number}
                    </a>
                </li>
            </>
        ) : null}

        <li className="page-item active">
            <a className="page-link" href="#" onClick={() => Profile(posterid, username, userid, page_number)}>
                {page_number} <span className="sr-only">(current)</span>
            </a>
        </li>

        {has_next ? (
            <>
                <li className="page-item">
                    <a className="page-link" href="#" onClick={() => Profile(posterid, username, userid, next_page_number)}>
                        {next_page_number}
                    </a>
                </li>
                <li className="page-item">
                    <a className="page-link" href="#" onClick={() => Profile(posterid, username, userid, num_pages)} aria-label="Next">
                        <span aria-hidden="true">&raquo;</span>
                    </a>
                </li>
            </>
        ) : null}
    </ul>
</nav>
```

### Specification for this project:

Using Python, JavaScript, HTML, and CSS, complete the implementation of a social network that allows users to make posts, follow other users, and “like” posts. You must fulfill the following requirements:

**New Post:** Users who are signed in should be able to write a new text-based post by filling in text into a text area and then clicking a button to submit the post.

**All Posts:** The “All Posts” link in the navigation bar should take the user to a page where they can see all posts from all users, with the most recent posts first.
  - Each post should include the username of the poster, the post content itself, the date and time at which the post was made, and the number of “likes” the post has (this will be 0 for all posts until you implement the ability to “like” a post later).

**Profile Page**: Clicking on a username should load that user’s profile page. This page should:

- Display the number of followers the user has, as well as the number of people that the user follows.
- Display all of the posts for that user, in reverse chronological order.
- For any other user who is signed in, this page should also display a “Follow” or “Unfollow” button that will let the current user toggle whether or not they are following this user’s posts. Note that this only applies to any “other” user: a user should not be able to follow themselves.

**Following**: The “Following” link in the navigation bar should take the user to a page where they see all posts made by users that the current user follows.
- This page should behave just as the “All Posts” page does, just with a more limited set of posts.
- This page should only be available to users who are signed in.
  
**Pagination:** On any page that displays posts, posts should only be displayed 10 on a page. If there are more than ten posts, a “Next” button should appear to take the user to the next page of posts (which should be older than the current page of posts). If not on the first page, a “Previous” button should appear to take the user to the previous page of posts as well.

**Edit Post:** Users should be able to click an “Edit” button or link on any of their own posts to edit that post.
- When a user clicks “Edit” for one of their own posts, the content of their post should be replaced with a textarea where the user can edit the content of their post.
- The user should then be able to “Save” the edited post. Using JavaScript, you should be able to achieve this without requiring a reload of the entire page.
- For security, ensure that your application is designed such that it is not possible for a user, via any route, to edit another user’s posts.

**“Like” and “Unlike”:** Users should be able to click a button or link on any post to toggle whether or not they “like” that post.
Using JavaScript, you should asynchronously let the server know to update the like count (as via a call to fetch) and then update the post’s like count displayed on the page, without requiring a reload of the entire page.

To check code and implementation please check [github project Network][github-network]{:target="_blank"} 
Specification and project done by:  [CS50 WEB - Network][cs50web-network]{:target="_blank"} 

ChatGPT was used to improve grammar and coherence of this article

[github-network]: https://github.com/jdsuta/projects/tree/main/network
[cs50web-network]: https://cs50.harvard.edu/web/2020/projects/4/network/