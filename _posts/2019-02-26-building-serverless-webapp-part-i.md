---
layout: post
title: "Building a serverless pet project: Part I"
date: 2019-02-26 20:32:44
image: '/assets/img/'
description: 'Running a dedicated web app at next to no cost'
tags:
- aws
- lambda
- backend
categories:
- Backend development
twitter_text: 'Serverless pet projects and AWS Lambda Part I'
---

I've had a couple opportunities to become involved with "pet projects" either through personal interests or hackathons.
They've been awesome ways to get my hands dirty with newer technologies like Angular and Firebase that aren't typically
learned in CS degree programs, but managing the deployment of these apps is a hassle. As a student, I didn't want to have
to worry about the configuration management that comes with running a dedicated cloud server like an AWS EC2 instance, and
a dedicated instance is using a lot of compute time that my small project would really not need due to the lack of consistent
traffic. That being said, it's nice to deploy pet projects in order to showcase a polished version of a web app to friends
or prospective employers without worrying if your instance is running or if you've stopped it.

Enter serverless web apps! Instead of managing a running instance, and paying for unused compute time, you write "functions"
in the backend language of your choice (*ehhhh* with a catch), and your cloud provider will manage an environment for
that function to run on, taking care of all the configuration details. The caveat is that some overhead goes into spinning
up an environment to run your function when it is called by some type of trigger (an API for example), particularly if it
hasn't been run in some time. This results in some additional latency when compared with a dedicated cloud server, but for
the use case described here this isn't really noticeable enough to be an issue (at least it wasn't for me).

In this guide, I'll be walking through some of the steps needed to deploy a serverless API to AWS

* [AWS Lambda](https://aws.amazon.com/lambda) seems to lead the pack because AWS is still the most popular cloud provider right
now. They support a ton of languages and seem to have a lot of libraries pre-installed in their runtime environment.
* [IBM Cloud](https://www.ibm.com/cloud/functions) supports serverless functions as well.
* fdlkfjldj
*
*

## Basic Setup

1. [Install Jekyll](http://jekyllrb.com)
2. Fork the [Will Jekyll Template](https://github.com/willianjusten/will-jekyll-template/fork)
3. Clone the repo you just forked.
4. Edit `_config.yml` to personalize your site.
5. Check out the sample posts in `_posts` to see examples for assigning categories and tags, and other YAML data.
6. Read the documentation below for further customization pointers and documentation.

## Site and User Settings

You have to fill some informations on `_config.yml` to customize your site.

{% highlight ruby %}
# Site settings
description: A blog about lorem ipsum dolor sit amet
baseurl: "" # the subpath of your site, e.g. /blog/
url: "http://localhost:3000" # the base hostname & protocol for your site 

# User settings
username: Lorem Ipsum
user_description: Anon Developer at Lorem Ipsum Dolor
user_title: Anon Developer
email: anon@anon.com
twitter_username: lorem_ipsum
github_username:  lorem_ipsum
gplus_username:  lorem_ipsum
disqus_username: lorem_ipsum
{% endhighlight %}

## Color customization

All color variables are in `src/styl/variable`. To change the main color, just set the new value at `main` assignment. Another colors are for texts and the code background color.

## Creating posts

You can use the `initpost.sh` to create your new posts. Just follow the command:

{% highlight bash %}
./initpost.sh -c Post Title
{% endhighlight %}

The new file will be created at `_posts` with this format `date-title.md`.

## Front-matter 

When you create a new post, you need to fill the post information in the front-matter, follow this example:

{% highlight ruby %}
---
layout: post
title: "How to use"
date: 2015-08-03 03:32:44
image: '/assets/img/post-image.png'
description: 'First steps to use this template'
tags:
- jekyll 
- template 
categories:
- I love Jekyll
twitter_text: 'How to install and use this template'
---
{% endhighlight %}


## Running the blog in local

In order to compile the assets and run Jekyll on local you need to follow those steps:

- Install [NodeJS](https://nodejs.org/)
- Run `npm install` 
- Run `gulp`

## Questions

Having a problem getting something to work or want to know why I setup something in a certain way? Ping me on Twitter [@willian_justen](https://twitter.com/willian_justen) or file a [GitHub Issue](https://github.com/willianjusten/will-jekyll-template/issues/new).

## License

This theme is free and open source software, distributed under the The MIT License. So feel free to use this Jekyll theme on your site without linking back to me or using a disclaimer.

If you’d like to give me credit somewhere on your blog or tweet a shout out to [@willian_justen](https://twitter.com/willian_justen), that would be pretty sweet.






