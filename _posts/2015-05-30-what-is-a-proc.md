---
layout: post
title: What is a Proc?
categories:
- Ruby
tags:
- Ruby
---

In Ruby we have a notion of a `Proc`, in this article I want to cover what exactly they are and what use they have within Ruby and within frameworks like Ruby on Rails.

A Proc object is a block of code that has been bound to a set of local variables.

Once a Proc object has been bound it can be called in different contexts and still be able to access those variables.

That is a bit of a mouthful but let me explain with an example.

	def make_power(factor)
		return Proc.new {|n| n**factor}
	end

	power_of_five  = make_power(5)
	power_of_three = make_power(3)

	power_of_five.call(10) # returns 100000
	power_of_three.call(10) # returns 1000

So what we are passing into `.call` is what the Proc takes in as `n`.

## Is a Proc a Lambda?

Nope, however a Lambda _is_ a type of Proc, look at the return type when you try this in irb;

	test = ->(x) { x + 2 }
	 => #<Proc:0x007fc82c335378@(irb):6 (lambda)>

I am going to cover Lambdas in a later post.

## Proc Class Method

There is only one public Proc class method, which is `new`. As you seen in the previous example you generally would call Proc.new with a block

## Proc Instance Methods

I am not going to go through each public instance method for Proc, you can do that yourself by looking through [the docs](http://ruby-doc.org/core-1.9.3/Proc.html). I do want to call attention to some of the more interesting methods.

### ===

This method has been defined so that you can use a Proc within the confines of a case statement or an if statement.

When used in this way whatever the Proc is being compared to will be passed in as the argument for the Proc and a boolean result is recorded.

	is_odd = Proc.new {|n| n.odd?}
	is_odd === 3 # Will be true

	case 5
	when is_odd # Will run
	when is_even
	else
	end

### prc[params]

A common reason why would you prefer a Lambda over a Proc is that Lambda’s care about how many parameters they receive, which is really handy because normally we care about that as well.

The standard procedure for a Proc is to ignore any parameters that it doesn’t require. This means we can collect an arbitrary amount of parameters and do something with them if our Proc was set up like;

	my_proc = Proc.new { |a, *b| b.collect {|i| i * a}}

What the `*b` does is gather any parameters after the first one into an array, we can do with that array what we like, in this case we can multiply and return each element of that array with whatever we pass in as `a`.

	my_proc[5, 1, 2, 3] # Returns [5, 10, 15]

### Parameters

When you call parameters on a Proc you get to see information about the parameters that make up the Proc.

	my_proc = Proc.new {|a, b=5, *c| # Something awesome }
	my_proc.parameters
	# Returns [[:opt, :a], [:opt, :b], [:rest, :c]]

The reason this says :a is :opt(ional) is because we are dealing with a Proc and Proc’s don’t care about the params, if we made a Lambda with the same params we would see something different;

	my_lambda = -> (a, b=5, *c) { # Something awesome }
	my_lambda.parameters
	# Returns [[:req, :a], [:opt, :b], [:rest, :c]]

Now :a is :req(uired).

## Procs in Rails

Where I use Procs most frequently is when I am writing models in Rails and setting scopes.

Something fairly common would be;

	scope :last_month, ->() { where(“publish_date > ?”, 1.month.ago) }

In this case we have used a Lambda, but since we have already established that Lambda’s are a type of Proc that is fine :-)