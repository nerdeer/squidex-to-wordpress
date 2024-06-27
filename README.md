# squidex-to-wordpress #

push ( and pull ) content from squidex into a WordPress instance.

# WHY? #

WordPress is very popular and runs many of the world's websites, however managing and supporting a WordPress site has 
become tedious and tiresome to the point of developer abandonment. 

.. but why?

A large part of the problem is that to do anything with WordPress today required the website to sign up for a number of 3rd party services that often have paid licenses. This sort of arrangement works against the developer, and hurts the industry as a whole.

But what if I told you that these plugins aren't needed at all? 

The problem isn't WordPress itself, or even these plugins. The problem is that all of these websites are running their businesses' directly out of WordPress.

MADNESS, I SAY!

* No, you probably do not need ( or even want ) a live dynamic website with real time updates.
* No, a shopping cart should not be part of your blog.
* No, you don't need a fancy wysiwyg content builder.
* No, you don't need to pay a license for that one extra feature.
* No, your data doesn't need to be locked behind a service or paid license.
* No, do not run SMTP on your server.
* Yes, you should be able to localize your content and media.
* Yes, you should be able to deploy to multiple environments without licensing issues.
* Yes, you should be able to use CI and Docker deployments.
* Yes, deploying to a multisite configuration should be supported.
* Yes, your website should be using Git.
* Yes, your website should have versioned states.
* Yes, you should hire "that" developer.


# Ok, but what is Squidex? #

Squidex is just another CMS, but this one is generic in the sense that you can build any data models that you like with it.
It also follows modern coding standards, plus has amazing localization support for text and media.
Because Squidex is API based, it is referred to as a `headless CMS`.

Squidex is, honestly, a bit of a `hidden gem` :gem:, but yes it does require a little know-how to use it properly.

It uses OpenAPI with Angular for the UI. Documentation is auto compiled, and you have the choice of GraphQL or a classic API that supports OData for accessing the data.

Also, since it is open it can easily be hooked up into integration services. I anticipate that services like Zapier will include support soon.

It's a developer's playground that can solve many problems by giving us control of the data.


# Deploy an Environment #

The goal is to use WordPress as a deployment target instead of as a Content Management System.

This is done 100% via APIs by :

1) Start with a clean WordPress installation 
2) Collect the data & media from Squidex 
3) Push the data into WordPress
4) Leave WordPress in read-only mode so that no additional changes can be made.

This can be automated in CI.

## Advanced ##

For localization, this can be done by using WordPress in a multi-site configuration where all the content is generated for each supported language; one per site.

With the content managed by Squidex, localization in WordPress is solved.

# Push changes from WordPress into Squidex #

Normally, there is no reason to push changes from WordPress back into Squidex, however every situation can be unique.

## one-time push from an existing WordPress instance into Squidex ##

This is a common place to start when there is already a WordPress site with content.

## Using WordPress to edit content regularly ##

In this scenario, we would need basic CI automation. 
The choice I have here is to use github actions, but there are many options.

on a trigger ( manual or tagged version ), update Squidex from the running WordPress instance.

# Plugins #

Squidex support for each plugin needs to be added individually. 

# Requirements #

## WordPress ##

* A running WordPress instance with the [REST API](https://developer.wordpress.org/plugins/rest-api-overview/) accessible.

## Squidex ##

* A running Squidex instance, either [cloud](https://squidex.io) or self hosted.
* an application configured to use the `Blog Starter`
* A client added with the `editor` permissions

# Changes #

Pull Requests are welcome!

# :heart: Support :heart: #

please contact [Nerdeer.com](https://www.nerdeer.com) if you require development services.
