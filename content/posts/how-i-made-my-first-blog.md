+++
title = "How I made my first blog"
date = "2022-03-23"
author = "Peter C"
cover = "/img/website.jpg"
description = "So, welcome to my first blog post. It took me the better part of a day at work to find the best (and cheapest!) way to setup a blog under my own domain."
+++

So, welcome to my first blog post. It took me the better part of a day at work to find the best (and cheapest!) way to setup a blog under my own domain.

I've recently started a new job at Infinity Works (IW) as a consultant, and with all this new job energy I thought I'd like to look into doing some things that I've been meaning to for a long time but didn't have time.etc... Fortunately at IW we have something called the Green Room, where I am able to do some self-development projects and such, and so starting this blog on work time is somewhat justified :smile:

The initial idea here is to start documenting findings and keeping a record of my achievements and interesting things that I've learned over the course of my career.

I mean... half of all the programming I've ever learnt is from someone's blog or a medium article, so why not give back with my own take on things?

In this post I'll be walking through my decision making and how I started this very blog you're reading right now. Because... where better to start a first blog post?

There are three basic things that I will talk about today:

1. Domains
2. Hosting
3. Content

## How do I even start a website? (Domain)

In my opinion, a good way to start creating a blog is to get your own domain. It's not strictly necessary as I'll get onto... But it's kinda fun to get this sense of ownership, and I like to think fun is a good way to start any project.

Firstly, what you'll need to do is to acquire a domain is to hit up a domain registar. As I understand, and at the time of writing, good options for domain registars are:

- [Godaddy][godaddy]
- [Namecheap][namecheap]
- [Domain][domain]
- [Google][domain-google]

I got mine at Godaddy.

![Godaddy](https://sm.pcmag.com/t/pcmag_me/review/g/godaddy-we/godaddy-web-hosting_x4tv.1200.jpg)

It's worth noting that students should visit the [Github Student Developer Pack](https://education.github.com/pack), as there are some services that offer free domain names for at least a year or two!

<br>

---
<br>

## Alright Pete you made me buy a domain. What now? (Hosting)

Great! You got your own domain! Logically the next step start putting content in your shiny new domain. **HOWEVER**, before you can do that, you're going to need someone to host your content.

Now this can be a bit of a sticking point... especially if you don't have much patience...

Basically, there are a lot of options and it really depends on what you want for a blog. In my case, I didn't want to spend much money, and I wanted the convenience of publishing as fast as possible.

Turns out you need to compromise a little...(surpise!)

Let me simplify the options for you!

1. [Wordpress][wordpress]
  - Cheap!
  - Convenient!
  - Not fun!
2. [AWS based][aws-website]
  - Cheaper!
  - Least convenient!
  - Maybe more fun?!
3. [Github Pages][gh-pages] (my option)
  - Cheapest! (FREE)
  - Also convenient!
  - Not as fun!

### Wordpress

I've heard of wordpress for a while now, it's a household name and it's quite consistently rated as one of the [best][techradar-cms] CMS around!
As I understand, most websites currently are powered by these [CMS][CMS]'s as they're the easiest and fastest way to deliver a website.

<br>

<p align="center">
  <img width="600" height="400" src="https://s.w.org/about/images/logos/wordpress-logo-stacked-rgb.png">
</p>

<br>

In my experience, I've heard of:

1. [Wordpress][wordpress]
2. [Sitecore][sitecore]

And not much positive about either...

But hey, what do I know, I've not tried either. And I almost considered a hosted wordpress site, since it's only about [£5 a month][wordpress-hosted]. Maybe I'll try it one day and write a post on it.

### AWS Based

I say AWS, but I mean this could apply to all the cloud providers meaning GCP, Azure, DigitalOcean to name a few.

With the power of the cloud, you can make a website in so many different ways. You could:

1. Use something like to distribute static websites hosted on S3 buckets
2. Run an apache server off of an EC2 instance or some kind of VPS
3. Use an EC2 instance or VPS to run wordpress

If you really want to get into it, you should start [here][aws-website].

If you are a bit of cloud nerd (like what I'm aiming to be), this would be a good way to flex your skills :muscle:, and actually good fun along the way. Maybe I'll try this method soon.

There are also many different ways to go about it with a cloud provider, as explained in the link above. But the problem with all of those options is that eventually... you're going to run into some costs.

Running wordpress on Lightsail is about minimum £3.50 a month... EC2 is going to be at least £5... Cloudfront and S3 is **very** cheap... but still not as cheap as free.

However, you do get many pros with the latter method.
   1. You can get an SSL certificate for your custom domain.
   2. It's easily the most scalable option.
   3. You can also enable your website to act as a REST API.
   4. AWS can also register your domain and manage your DNS with route53.

### Github Pages and Netlify

Introducing [Github Pages][gh-pages], which is a feature that Github has supported since 2008. Totally free, although there are some [***soft limits***][gh-pages-limits] per repository.

There is also [Netlify][netlify] which is a good alternative to Github pages and it features less restrictive limits for the free version. My friend Anton showed me this [link](https://savjee.be/2020/05/benchmarking-static-website-hosting-providers/), which I used a basis to justify not using Netlify just yet as it seemed to have marginally slower response times than Github pages :joy:. Again, if I need it one day, I'll look into it... But be warned that netlify currently doesn't support [subdomains](https://docs.netlify.com/domains-https/netlify-dns/)


The great thing about Github pages is that it's so easy to setup. All it takes is to create a Github repository, and then going into the settings to pick a theme, and you will have a .github.io website in literally no time.

And **boom**! You have a website! No domain name required.

Although if you wanted to connect your personal domain to github pages, it's also possible [to do that](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages). And I do highly recommend doing that as it makes your blog unique.

Github pages comes preloaded with [Jekyll](https://jekyllrb.com/) as the [Static Site Generator](https://www.cloudflare.com/en-gb/learning/performance/static-site-generator/), which is powered by Ruby. And this will lead me nicely onto...

<br>

---

<br>

## Halp, I don't know HTML, how do I make some (**CONTENT**)?

The [Jamstack](https://jamstack.org/), as I've seen it called, is a modern and simple method to build and deploy a static website with the least faff as possible. It's how I created this website, and it's most of what I've been talking about in this blog post.

Using what is known as a [Static Site Generator](https://www.cloudflare.com/en-gb/learning/performance/static-site-generator/) (SSGs), you can quite easily generate the necessary HTML and CSS for a good looking website without much fuss. That's basically what SSGs do; it simplifies the process of writing content as you can do it in something like markdown, and easily have that compile into a beautiful webpage.

There is a plethora of options here (as usual!), and honestly I don't know enough here to give any recommendations. But I would avoid Next.js and Gatsby for simple websites like a blog since I believe they're used more for deploying static react apps, and I wouldn't bother with something as complex as react for a blog.

[Eleventy](https://www.11ty.dev/) (written in JS) and [Hugo](https://gohugo.io/) (written in Go) look very interesting and up and coming in terms of userbase and functionality.

[Jekyll](https://jekyllrb.com/) has been around for longer and is already quite established, but ecosystem of Ruby with Bundler and Gemfiles feel a bit heavy for building a static website. Look at the [setup](https://jekyllrb.com/docs/installation/macos/) for Jekyll (despite the fact that they try to hide this with a nice simple [quickstart](https://jekyllrb.com/docs/)).

Compare this to Eleventy's super quick (non-existent) [setup](https://www.11ty.dev/#quick-start), or even Hugo's no bullshit setup [here](https://gohugo.io/getting-started/quick-start/#step-2-create-a-new-site).

I might consider moving to Hugo and get rid of ruby off my system entirely.

<br>

---

<br>

## Summary

To summarise, below is a diagram that describes the process of making this website.

![MyWebsiteDiagram](/img/website.jpg)

<br>

Although this could easily be done alternatively as:

<br>

![MyDesiredDiagram](/img/desiredwebsite.jpg)

If you'd like to find out more about how other people set up their websites I highly recommend using blogging platforms like [Hashnode](https://hashnode.com) or [Dev.to](https://dev.to) and going to other people's blogs and see what they've done, such as [this guy](https://blog.cavelab.dev/2021/08/deploying-hugo-blog-to-s3/).

Thanks for reading my first blog post and I hope you will find my future posts interesting!

*(P.S.) I used [Miro](https://miro.com) for the images produced above and it's an incredibly useful tool*

[godaddy]: https://godaddy.com
[namecheap]: https://www.namecheap.com/
[domain]: https://www.domain.com/
[domain-google]: https://domains.google
[gh-pages]: https://pages.github.com/
[wordpress]: https://wordpress.com/
[aws-website]: https://aws.amazon.com/websites/
[CMS]: https://en.wikipedia.org/wiki/Content_management_system
[sitecore]: https://www.sitecore.com/
[wordpress-hosted]: https://www.godaddy.com/en-uk/hosting/wordpress-hosting
[gh-pages-limits]: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#usage-limits
[techradar-cms]: https://www.techradar.com/uk/best/cms
[netlify]: https://www.netlify.com