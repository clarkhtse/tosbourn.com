---
layout: post
title: Uploading files with Capybara in Rspec tests
categories:
- Rails
tags:
- Ruby
- Capybara
- Rspec
description: You can easily upload files with Capybara when testing with rspec
---

Capybara is a great tool for testing your Rails app. Recently I had cause to test uploading files through a particular UI. Here is how you go about in Capybara.

    attach_file("Upload Your File", Rails.root + "spec/fixtures/file.pdf")

What this tells Capybara is look for a file upload input with the label "Upload Your File" and then inserts the file specified.

I found I needed the Rails.root for the file to upload correctly.

In order to tidy up your tests I would recommend making a helper method called something like `pdf_upload_file` which would return `Rails.root + "spec/fixtures/file.pdf"`