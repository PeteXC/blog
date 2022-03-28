---
layout: post
title:  "My First Blog"
date:   2022-03-23 16:46:24 +0000
categories: post
---
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

In my opinion, a good way to start creating a blog is to get your own domain. It's not strictly necessary as I'll get onto... But it's kinda fun to get this sense of ownership and I like to think fun is a good way to start any project.

Firstly, what you'll need to acquire a domain is to hit up a domain registar. As I understand, and at the time of writing, good options for domain registars are:

- [Godaddy][godaddy]
- [Namecheap][namecheap]
- [Domain][domain]
- [Google][domain-google]

I got mine at Godaddy.

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

In my experience, I've heard of:

1. [Wordpress][wordpress]
2. [Sitecore][sitecore]

And not much positive about either...

But hey, what do I know, I've not tried either. And I almost considered a hosted wordpress site, since it's only about [£5 a month][wordpress-hosted]. Maybe I'll try it one day and write a post on it.

### AWS Based

I say AWS, but I mean this could apply to all the cloud providers meaning GCP, Azure, DigitalOcean to name a few.

If you really want to get into it, you should start [here][aws-website].

If you are a bit of cloud nerd (like what I'm aiming to be), this would be a good way to flex your skills :muscle:, and actually good fun along the way. Maybe I'll try this method soon.

There's also many different ways to go about it with a cloud provider, as explained in the link above. But the problem with all of those options is that eventually... you're going to run into some costs.

Running wordpress on Lightsail is about minimum £3.50 a month... EC2 is going to be at least £5... Cloudfront and S3 is **very** cheap... but still not as cheap as free.

However, you do get many pros with the latter method.
   1. You can get an SSl certificate for your custom domain.
   2. It's easily the most scalable option.
   3. You can also enable your website to act as a REST API.
   4. AWS can also register your domain and manage your DNS with route53.

### Github Pages and Netlify

Introducing [Github Pages][gh-pages], which is a feature that Github has supported since 2008. Totally free, although there are some [***soft limits***][gh-pages-limits] per repository.

There is also [netlify] which is a good alternative to Github pages and it features less restrictive limits for the free version. My friend Anton showed me this [link](https://savjee.be/2020/05/benchmarking-static-website-hosting-providers/), which I used a basis to justify not investigating Netlify just yet as it seemed slower than Github pages :joy:


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