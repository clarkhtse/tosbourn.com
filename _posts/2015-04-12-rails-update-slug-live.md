---
layout: post
status: publish
published: true
title: Updating a Slug on a live Rails System
author:
  display_name: Toby
  email: toby.osbourn@googlemail.com
categories:
- Developer Help
tags:
- Rails
---

Lets say you have a Rails site with blog posts under categories like `site.com/:category_slug/:page_slug`

If you need a well established category from having a slug `ruby-on-rails` to just `ruby-rails` the quickest way to do this would be to run a update on the Category model.

    c = Category.find_by_title(“Ruby on Rails”)
    c.slug = “ruby-rails”
    c.save

The change would take effect immediately and the slug would be updated.

An issue we have just created is that bookmarks or links coming in from other websites will break.

## Fixing the broken links

There are two ways we can go about doing this and each should ideally be done ahead of the swap to avoid any issues.

The method you choose depends mainly on how many slugs you need to update.

## Redirect the old slug to the new slug

Redirecting the old slug to the new slug involves writing new rules in your `config/routes.rb`. If you have to do a lot of them your routes may start to get a bit messy, and nobody wants that!

You can add something like this.

    get “/ruby-on-rails/”,  to: redirect(“/ruby-rails/”)
    get “/ruby-on-rails/:slug”,  to: redirect(“/ruby-rails/%{slug}”)

You can see how this could quickly mount up the lines in your `config/routes.rb` file!

## Create a new Category

You could reate a new category and have a many to many relationship between pages and categories.

In this way both categories will link correctly to your content.

The issue here is you are changing your domain logic to suit what is essentially a cosmetic change, this doesn’t feel right.

You will also want to ensure you are using the canonical tag in your HTML correctly so that only one slug is ever seen by Google.

## Google Webmaster Tools is your friend

After changing a slug on your website you should always check Google Webmaster Tools some time after the change has been made to see if there is an increase in 404s on your site.

