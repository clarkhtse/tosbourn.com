---
layout: post
title: The difference between Render and Redirect in Rails
categories:
- Ruby
tags:
- Ruby
---

To a brand new Rails developer the controller methods `render` and `redirect_to` might seem very similar. They both appear at the bottom of your controller method and they both (when done correctly) end up showing a page in your web browser.

They both do very different things however, and it is good to know the difference.

## Render

Calling render will create a full response that is sent back to the browser. 

If you don't include a call to render in your controller action then it is assumed you are trying to render the view of the same name as your controller action inside a folder of the same name as your controller. This means that the following code will look for `app/views/foos/my_action.html.erb`;

    class FoosController < ApplicationController
        def my_action
        end
    end

If you want to render a different view within the same controller you can call `render :action_name` and it will know where to look.

You can specify views that belong to another controller by using `render "widgets/show"`

You can even just render an arbitary file, a leading slash will let Rails know what do to. This is useful if you want to share views between Rails applications on the same server. `render "/users/another/apps/different_app/app/views/products/show"`

You can render things other than views as well, they are covered in more detail in [this great guide](http://guides.rubyonrails.org/layouts_and_rendering.html), examples of things you can render are;

* JSON
* Text
* Status Codes

### Debugging Render

Sometimes you want to see what is going to be rendered without inspecting inside of the browser. There is a rails method called `render_to_string` which can really help you out. This takes all the same options as render but returns a string instead of sending a response back to the browser.

## Redirect

Redirect is concerned about telling the browser it needs to make a new request to a different location.

This could be a location within your application by calling something like;

    redirect_to widgets_url

Or it can be to a completely different website;

     redirect_to "http://tosbourn.com"

By default Rails uses the 302 redirect, which is a temporary redirect. If you know any that traffic going to a certain place should always end up at a different place you should consider setting the status code to 301, which is a perminant redirect.

     redirect_to widgets_url, status: 301

There is a great guide on the different status codes you should be worried about in this guide about [HTTP status codes to be worried about for SEO](http://developerseoguide.com/http-status-codes-for-seo)

## Know when to use each one

You should not make the browser need to make a fresh call unless you really have to, so always question when you are using `redirect_to` and if it is the right thing, or perhaps a `render` would be better.

A `render` doesn't change the URL of the page you are visiting, which can lead to a confusing user experience if they visit /foo but because of some render magic start seeing a layout associated with /bar