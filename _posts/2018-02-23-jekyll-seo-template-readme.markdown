---
layout: post
title: jekyll SEO Template Tutorial
head_title: jekyll SEO Template [Tutorial]
date: 2018-02-23T10:00:00+01:00
last_modified_at: 2018-02-01T22:10:10+01:00
preview_image: jekyll-seo-tutorial.jpg
thumb_image: jekyll-seo-tutorial-thumb.jpg
keywords: heroku, cloudflare, github pages, free ssl, save money, startup, landing page, lets encrypt
main_image_description: Multiple HTTP domain names can be cheap
summary: Thanks for your interest in jekyll SEO template. In this post, I will cover things which differ this template from standard jekyll templates and describe SEO techniques which I implemented into it.
---

Thanks for your interest in jekyll SEO template. In this post, I will cover things which differ this template from standard jekyll templates and describe SEO techniques which I implemented into it.

To learn how use jekyll you should check out [the documentation](https://jekyllrb.com/){: target="_blank" }.

## Configure post metadata:

Each post should have the following data set:

{% highlight text %}

layout: post
title:
head_title:
date:
summary:
last_modified_at:
preview_image:
thumb_image
keywords:
{% endhighlight %}

I added the following non-standard data fields to this template:

`head_title` - it will be displayed in a `<title>` tag of a blog page. This is a title that users will see when they find your page in Google search results. It can be different than the `title`, it is a great place to input the keywords you are targeting.

`preview_image` - this image will be displayed as a thumbnail of a post Open Graph and Twitter meta tags. The image is preprocessed using [jekyll-assets gem](https://github.com/envygeeks/jekyll-assets){: target="_blank"}. One caveat is that if you don't use preview image anywhere in the post it's preprocessed version will not be prepared. To avoid this problem you need to display hidden version of an image somewhere on your blog. Check out `pages/render-images.html`.

It will not be an issue if you use a preview image somewhere in your post.

`thumb_image` - smaller version of the main image, it will be dispalyed before original version is loaded


Preview image needs to be exactly `800x500px` because dimensions data has to be provided in both Open Graph tags and Structured Data. You can change it if you like but I find this size optimal for my images.

`keywords` - keywords are said to have SEO minimal impact in the meta tag. I use them also for Structured Data so it won't hurt to add them.

This template contains 2 of my real blog posts, please consult their source files if something is unclear.

## Lower head

I improved the rendering speed by moving fetching blocking resources below the `<body>` tag. You can check out `_includes/lower_head.html`.

## Image preprocessing

Image preprocessing adds a digest tag to each image. It allows you to leverage browser caching and improve page speed ranking. Check out  [jekyll-assets gem](https://github.com/envygeeks/jekyll-assets){: target="_blank"} for documentation on how to use it.

## Permalink

Contrary to default jekyll setting, posts use only their filename title as an URL. There are studies which confirm that Google favors shorter URLs.

## Structured Data

Together with Structured Data allows your website to appear in Google's featured snippets and Chrome's recommended articles.

You can check out `_includes/schema.html` to see how I setup structured data.

To generate a correct `BlogPosting` entry you need to provide a publisher image with size exactly `600x60`. `publisher.jpg` image is in the `_assets/shared` folder. You should change it to represent your brand.

## Styling

You can find my custom CSS in `css/styles.scss` file. You can change `$theme-color` variable to change the main color.

## Summary

You can also consult [my blog post about SEO tips for blogs](https://pawelurbanek.com/2018/02/16/seo-tips-for-technical-bloggers-and-programming-blogs-in-2018/){: target="_blank" } and [removing AMP](https://pawelurbanek.com/amp-seo-rating-performance){: target="_blank" } where I describe some of those techniques.

Once again thanks for your interest in the template. I am open to suggestions on what could be improved in the codes of the template and this tutorial.
