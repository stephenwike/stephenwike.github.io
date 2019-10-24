---
layout: post
author: Stephen Wike
---


# Setting Up My First Technical Blog
##### This is my first one!  Hopefully it's a good one.

I have been meaning to start blogging for a long time and I kept putting it off because:

* I want my personal website to look awesome first.
* I want to have something special to blog about.
* I want to make sure everything public is secure.
* I don't want professionals seeing flaws in my code or logic.
* etc., etc., etc.

Really, the reason I haven't starting until now is I didn't see the value of getting feedback early and leveraging that feedback to inform my processes.  Thanks to a good book and some motivation, that's all about to change! [^1]

## Why I started blogging
Admittedly, this is not the first time I've tried to blog.  Most of my experience in blogging had been limited to exploration of the blogger service.  I had a **_www.blogger.com_** and a **_www.wordpress.com_** blogging website, but these were created a long time ago and I never used them as a dedicated source for blogging.  _Also, I didn't have much to say or write about at the time._  It was my intention to start blogging again, but I wanted to blog on my finished website; complete with all the bells and whistles.  

I soon realized, currently working a major rewrite with informed by months of research, my site was not going to be ready for quite a while.  Then, I had a revelation.  Why not take this research and rewrite opportunity to blog about what I'm learning and how I'm applying it to the development of my new site?  I could provide insight to my process for other developers to expand on and more importantly, get feedback on how to improve on what I've created. [^2]

## Finding A Blog Host
The next step was finding a way to host my new blog.  I wanted to find a way to hit the ground running.  I own my domain **_www.stephenwike.com_**  through **_www.godaddy.com_**.  Now I just need to find where do write and host my blogging content.

I looked into hosting my starter blog with **[Wordpress](www.wordpress.com)** or **[Wix](https://www.wix.com/)**.  I do have a personal server through **_www.vultr.com_** on which I could host my site and it's relatively inexpensive, however; I don't want to build the database, and infrastructure to manage my blog.

## Setting Up My Blog

I started with setting up my WordPress profile.  I had to make some changes to the username and update the summary.  I also had to configure my comments and recycle an old abandoned blog to make this new one.  Setting up the blog was fairly straight forward.

While setting up my new blog website, I had to come up with a catchy name _(or at least one I felt was catchy)_.  I came up with The Contagious Coder as at least a temporary blog name.  It sounded better than "Stephen's Dumb Blog" anyway.  I was actually looking for a good synonym for _'sloppy'_ or _'disorganized'_ when I came across _'contagious'_.  

It sounds to me like it could represent one of two characteristics.  A coder who is _'enthusiastic'_ and _'has infectious amounts of energy'_, which sounds nice, or a coder who _'infects everyone else with the cold flu'_.  I feel like this is appropriate too, given we already use morbid nomenclature such as _"virus"_, _"hack"_, _"bug"_, _"worm"_, _"terminal"_ and _"daemon"_, just to name a few.

With the blog site set up, there was still another issue.  I couldn't write in **[Markdown Language](https://www.markdownguide.org/getting-started)!**  I generally prefer markdown because it works better for code documentation and it's used across many platforms including **[_www.github.com_](https://github.com/stephenwike)**.  I did solve my issue _(as you can probably tell)_.  The trick was going to the user dashboard and entering WP **Admin -> Settings -> Writing** and clicking the checkbox for **'Use Markdown for Post and Pages'** _(I also had to do this for comments)_.

This didn't fix the problem immediately.  I also discovered I needed to use the new **[Gutenberg Blocks Editor](https://wordpress.org/plugins/kioken-blocks/?gclid=Cj0KCQjwl8XtBRDAARIsAKfwtxDUelVnVnPUrhIDeSpAFAGhJEeVCzzYjQgV1HO6aIK39D5YKawZBo0aAjbiEALw_wcB)** before the markdown language content block became available.

Now I'm finally writing this very blog! :D

## Forwarding My Domain

Having the blog up and running is nice, but I'm not a huge fan of the URL you have to type to get to it. **_https://contagiouscoder.wordpress.com/_**.  I'd prefer to use my **_www.stephenwike.com_** domain name.

Fortunately this was very easy.  I signed into **_www.godaddy.com_** and clicked on the DNS hyperlink.  Near the bottom right of the website is a forwarding card that allowed me to specify DNS forwarding from my domain to my WordPress site.  This may be handled differently depending on your domain host.  A simple google search should give you steps to configure your own DNS forwarding.

This will be a good temporary fix while I'm developing the main website. Now I can post blog content and at least get some feedback while I begin the steps toward developing my site.

## Next Steps

Everything is up and running as expected.  The domain is temporarily tied to my WordPress blog until I have a chance to relocate the blog to my main website.  

It's clear that it's not perfect, but I'm much closer to my goal than I was before.  First, I have a way for visitors to read content from my blog posts and they are able to make comments and leave feedback _(assuming they aren't filtered out by the commenting terms of agreement)_.

Up ahead, I am getting into the weeds quickly and starting with **Deployment First**.  I know it sounds backwards, to start with deployment, but I'll be looking at Docker to determine my deployment strategy.  Hopefully that will allow for now surprises (or at least minimal) when it comes time to finally deploy my code.

---

[^1]: [Sonmez, John S.](https://simpleprogrammer.com/about-simple-programmer/) (2015). Soft Skills: The Software Developer's Life Manual. (ISBN: 1617292397):  This book contains a ton of useful strategies and must-know information for software developers.  John makes great statements regarding the importance of blogging for new and inexperienced developers.

[^2]: Gene Kim, Patrick Debois, John Willis, Jez Humble (2016). The DevOps Handbook: How to Create World-class Agility, Reliability, and Security in Technology Organizations.  (ISBN 1942788002):  This book contains useful information about devops best practices and examples of how these practices brought at-risk major software companies to success.  The importance of the feedback loop is drilled upon heavily throughout the chapters of this book.
