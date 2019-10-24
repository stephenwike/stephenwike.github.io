---
layout: post
author: Stephen Wike
---


# Setting Up My First Technical Blog
##### This is my first one!  Hopefully it's a good one.

I have been meaning to start blogging for a long time and I kept putting it off because:
> I want my personal website to look awesome first.
> I want to have something special to blog about.
> I want to make sure everything public is secure.
> I dont want professionals seeing flaws in my code or logic.
> etc. etc. etc.

Really, the reason I haven't starting until now is I didn't see the value of getting feedback early and leaveraging that feedback to inform my processes.  That's all about to change! [^1]

## Why I started blogging
Admittedly, this is not the first time I've tried to blog.  Most of my experience in blogging had been limited to exploration of the blogger service.  I had a _blogger.com_ and a _wordpress.com_ blogging website, but these were created a long time ago and I never used them as a dedicated source for blogging.  _Also, I didn't have much to say or write about at the time._  It was my intention to start blogging again, but I wanted to blog on my finished website; complete with all the bells and whistles.  I soon realized, being under a major research and rewrite, my site was not going to be published for quite a while.  Then, I had a revelation.  Why not take this research and rewrite opportunity to blog about what I'm learning and how I'm applying it to the development of my new site?  I would be priviledged to provide insight to my process for other developers to expand on and more importantly, get feedback on how to improve on what I've created. [^2]

## Finding A Blog Host
The next step is to find a way to host my blog.  I wanted to find a way to hit the ground running.  First I bought my domain through _godaddy.com_ I looked into hosting my starter blog with Wordpress or Wix but both required payment for work I already knew how to do on my own.  I already have a server through _vultr.com_ on which I could host my site and it's relatively inexpensive.

## Setting Up My VPS (Virtual Private Server)
### Installing and Setting Up a New Admin User
I start by installing CentOS 7 on my server.  Next, I create a user account and give that account administrative permissions _(root priveledges)_. [^3]

```
adduser mynewuser
passwd mynewuser
usermod -a -G wheel mynewuser
su mynewuser
```

The first line adds a new user with the name _'mynewuser'_.  The second sets that user's password.  We can do this because we are in the root user for our operating system.  The system will prompt for two identical passwords to confirm user password.  The third line (_'-a'_) appends new user _'mynewuser'_ to the (_'-G'_) group _'wheel'_.   **wheel** is a defined group that have all system priveledges.  The fourth and final line switches to the new user.

### Removing Login Access to the Root User

Next, I want to disable login access to the root account.  I receive lots of failed in login attempts through the root account and since I'm a solo developer running administrative priveledges through my admin account, I don't need the root account to be accessible.  You may skip this part.  The easiest way is to change with root user's shell from _/bin/bash_ to _/sbin/nologin_.  I like to edit files with vim.

```
sudo yum install vim -y
sudo vim /etc/passwd
```

The first line installs vim text editor.  The second opens the passwd file in the etc directory.  Next change the line
`root:x:0:0:root:/root:/bin/bash` to `root:x:0:0:root:/root:/sbin/nologin`

I test that I successfully disabled login by attempting to log in.  I receive _**'This account is currently not available.'**_  Success! 

## Setting Up a Website for Blogging...
##### And HARD STOP!!!

Why am I doing all this to make a simple blogging website?  I'm still just building a website that I'll have to finish before I'm ready to start presenting my blog.  This is the problem I was trying to avoid.  I was looking back into paying for a blog website service when I came across github pages. [^4]

### Setting Up Jekyll to Create a Static Blog Page
Install Jekyl by following the installation instructions for your operating system here: _https://jekyllrb.com/docs/installation/_

After installation.  Follow the instructions here to create and clone a repository into your local workspace.
_https://pages.github.com/#user-site_

You can now use the command `jekyll serve` inside the project folder to build and run the github pages content locally from your browser by navigating to `localhost:4000`

Following the jekyll docs I created a file structure like this: [^5]

**root**  
&nbsp;&nbsp;&nbsp;&nbsp;|-> _layouts  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| default.html  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| post.html  
&nbsp;&nbsp;&nbsp;&nbsp;|-> _posts  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 2019-10-23-first-blog.md  
&nbsp;&nbsp;&nbsp;&nbsp;|index.html  

Now, I just save my blogs in the *'_posts'* directory with the title format `year-month-day-title.md` and github pages takes care of the rest.

**Note:** _I'm skipping a few steps in this post as they are more about html design and not about getting started.  There are many tutorials on the web for creating html pages.  Everything else you need to know about using jekyll to setup github pages can be found the the jekyll docs._

It's clear that it's not perfect, but I'm much closer to my goal than I was before.  First, all I have is a way for visitors to read content from my blog posts.  I have no way of receiving comments and feedback to improve my processes in developing my website.  This will be a top priority for my next blog issue!

## Redirecting My Domain to GitHub Pages
Although it's not my website on my VPS, I would temporarily like to redirect traffic from my new domain to the github pages blog I just created.  For me, I just had to create Domain Forwarding in the godaddy.com DNS Management page.  Now I can navigate to www.stephenwike.com and see my blog!


[^1]: Sonmez, John S. (2015). Soft Skills: The Software Developer's Life Manual. (ISBN: 1617292397):
This book contains a ton of useful strategies and must-know information for software developers.  John makes great statements regarding the importance of blogging for new and inexperienced developers.

[^2]: Gene Kim, Patrick Debois, John Willis, Jez Humble (2016). The DevOps Handbook: How to Create World-class Agility, Reliability, and Security in Technology Organizations.  (ISBN 1942788002):
This book contains useful information about devops best practices and examples of how these practices brought at-risk major software companies to success.  The importance of the feedback loop is drilled upon heavily throughout the chapters of this book.

[^3]: https://www.tecmint.com/disable-root-login-in-linux/
Setting up a new user with root priveledges on CentOS 7 and disabling the root user login.

[^4]: https://pages.github.com/#user-site
Setting up a brand new repository with an index.html file to start a github pages project.

[^5]: https://jekyllrb.com/docs/step-by-step/01-setup/
