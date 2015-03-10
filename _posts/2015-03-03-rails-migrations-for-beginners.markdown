---
layout: post
status: publish
published: true
title: Rails Migrations for Beginners
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2620
wordpress_url: http://tosbourn.com/?p=2620
date: '2015-03-03 18:42:52 +0000'
date_gmt: '2015-03-03 17:42:52 +0000'
categories:
- Development Help
tags:
- Rails
- Migrations
comments: []
---
<p>I hadn't heard of the idea of migrations until I started using Rails.</p>
<p>They are something that make so much sense once they make sense.</p>
<p>They aren't hard to grasp but if you are new to Rails or only have to deal with Rails on an incredibly irregular basis they can be very daunting.</p>
<p>I want to try and explain what migrations are for beginners.</p>
<h2>What Are Migrations</h2>
<p>Migrations are a set of commands that Rails will run through when it is setting up or changing the database for your project.</p>
<p>These commands will help to shape the database.</p>
<h2>Why Are Migrations Good</h2>
<p>There are a few reasons why migrations are good.</p>
<ul>
<li>The language they use is easier than SQL</li>
<li>The changes can be version controlled</li>
<li>The changes can be rolled back</li>
</ul>
<p>Migrations use a Ruby Domain Specific Language (dsl), which is easier to learn and write than it is writing SQL. The other benefit of this dsl is that it acts as an abstraction so you don't need to care about what your database is when you write your migrations. This means that if someone decides Postgres is better than MySQL for a project, your migrations won't have to change.</p>
<p>Unlike when you just edit a database, these migrations are code that gets saved with the rest of your project, which means they can be easily version controlled and shared with everyone else on your team. If you have ever had to edit a database and then remember to tell everyone to make the same edit then you will know how great this is! If you are not using version control you should take a minute to read why <a href="http://thetomorrowlab.com/2015/02/why-web-developers-should-use-version-control/">I think developers should be using version control</a>.</p>
<p>Migrations can be rolled back, this means that you can undo what you did. This is a great safety mechanism and means you don't have to worry about permanent damage being done.</p>
<h2>How to use Migrations</h2>
<p>The easiest way to write migrations is to get Rails to do it for you.</p>
<p>We can tell rails we want to create a table called bobs with the following line</p>
<pre><code>rails generate migration createBobs name:string
</code></pre>
<p>This will create a table called <code>bobs</code> with one column called <code>name</code> that will hold stuff that is a string.</p>
<p>That seems like magic – it <em>is</em> magic!</p>
<p>Rails knew we wanted to create a new table because we used the word <code>create</code>, it also knew we wanted to call the table bobs because we said <code>Bobs</code></p>
<p>Now lets say we want to then add another column to this bobs table. We could go back and edit the file that was created when we did that first creation, but that would be bad because Rails will think it has already ran that migration and won't run it again for other people.</p>
<p>What we should do is just create a new migration!</p>
<pre><code>rails generate migration addColourToBobs colour:string
</code></pre>
<p>In this migration we are saying we want to add a column called Colour to the table called bobs.</p>
<p>For reference here is the contents of the file we made when we created that first migration;</p>
<pre><code>class CreateBobs &lt; ActiveRecord::Migration
  def change
    create_table :bobs do |t|
      t.string :name
    end
  end
end
</code></pre>
<p>Hopefully this isn't too daunting and shows how simple this dsl is compared to writing SQL.</p>
<p>Here is the next migration we created;</p>
<pre><code>class AddColourToBobs &lt; ActiveRecord::Migration
  def change
    add_column :bobs, :colour, :string
  end
end
</code></pre>
<p>In both of these you will see some similarities.</p>
<ul>
<li>The class name is just what we called our migration.</li>
<li>The class inherits from ActiveRecord::Migration – This isn't important for us but Rails needs it.</li>
<li>The method change means that when we are running the migration it knows to do one thing, and if we are rolling back the migration it knows to the do opposite (so if we are doing add_column the opposite would be to remove_column, Rails handles all this for us)</li>
</ul>
<h2>Any questions</h2>
<p>If you still have questions about the very basics of migrations than I have failed in this article, I would love for you to ask anything in the comments and I will add it to this post.</p>
