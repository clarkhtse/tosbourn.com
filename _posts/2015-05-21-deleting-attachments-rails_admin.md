---
layout: post
status: publish
published: true
title: Deleteing Attachments with rails_admin
categories:
- Ruby
tags:
- Ruby
---

If you want to be able to delete an attachment or a file upload associated with rails_admin you can by making some pretty tiny changes to your model.

The first thing you want to do is let your model know there is a parameter it wants to look for, this parameter should be named `:delete_#{name_of_attachment}`, for example;

```
attr_accessor :delete_attachment
```

Next up we need to set up something to catch this being set by rails_admin and handle it appropriately. You can do this with one line;

```
before_validation { attachment.clear if delete_attachment == '1' }
```

Thats it! Unfortunately I couldn't find this documented anywhere so it took me longer than I would care to admit.
