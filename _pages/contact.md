---
title: "Contact"
permalink: "/contact.html"
---

<!-- https://fontawesome.com/v5/icons/linkedin?f=brands&s=solid
Icons to use in the web -->

<div class="container">
    {% for author in site.authors %}
        <div class="p-4 border rounded mb-4">
            <div class="row">
                <div class="col-md-3 mb-4 mb-md-0 text-center">
                <!-- Author avatar -->
                    <img alt="{{ author[1].name }}" src="{{site.baseurl}}/{{ author[1].avatar }}" class="rounded-circle" height="80" width="80">
                </div>
                <!-- Author name and bio -->
                <div class="col-md-9">
                    <a href="{{site.baseurl}}/author-{{ author[1].name | slugify }}">
                        <h4 class="text-dark mb-0"> {{ author[1].name }} </h4>
                        <small class="d-inline-block mt-1 mb-3 font-weight-normal">(View Posts)</small>
                        <div class="excerpt">{{ author[1].bio }} </div>
                        <div class="excerpt">Feel free to contact me: </div>
                    </a>
                    <!-- Social media icons -->
                    <div class="icon-block mt-3 d-flex justify-content-between">  
                        <div>
                        <a class="text-dark ml-1" target="_blank" href="{{ author[1].linkedin }}"><i class="fab fa-linkedin-in" aria-hidden="true"></i></a> &nbsp;
                        <a class="text-dark ml-1" target="_blank" href="{{ author[1].github }}"><i class="fab fa-github" aria-hidden="true"></i></a> &nbsp;
                        <a class="text-dark ml-1" target="_blank" href="{{ author[1].instagram }}"><i class="fab fa-instagram" aria-hidden="true"></i></a>  &nbsp;
                        </div>
                    </div>
                </div>
            </div>
        </div>
    {% endfor %}
</div>

<!-- https://formspree.io/forms/xdorgqoj/submissions -->

<form action="https://formspree.io/xdorgqoj" method="POST">    
<!-- <p class="mb-4">Please send your message to {{site.name}}. I will reply as soon as possible!</p> -->
<p class="mb-4">Please send your message. I will reply as soon as possible!</p>
<div class="form-group row">
<div class="col-md-6">
<input class="form-control" type="text" name="name" placeholder="Name*" required>
</div>
<div class="col-md-6">
<input class="form-control" type="email" name="_replyto" placeholder="E-mail Address*" required>
</div>
</div>
<textarea rows="8" class="form-control mb-3" name="message" placeholder="Message*" required></textarea>    
<input class="btn btn-success" type="submit" value="Send">
</form>