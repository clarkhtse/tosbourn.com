---
layout: post
status: publish
published: true
title: How the technical direction of a project can be influenced
author:
  display_name: Toby
  email: toby.osbourn@googlemail.com
categories:
- Developer Help
tags:
- Technical
---

I was asked my thoughts on how the technical direction of a software project can be influenced. I thought it was an interesting question and wanted to write down my thoughts.

## The Problem

The problem to be solved will rule out certain technologies, languages have applications that they excel in and some that they drag their feet with.

An extreme example would be if there was a need for realtime computing you wouldn’t use something like COBOL.

## Current Knowledge Base of the Team

The team that has been assembled to solve the problem will have their own strengths, weaknesses, and preferences.

If 90% of the team know Ember.js inside out and there is a requirement for a front end framework for a website then it would make little sense to use Angular.

## Third Party Integrations

Some problems require that communication needs to happen via a third party integration. If this is an API call the third party integration will have little effect on the technical direction of the project.

Some integrations aren’t hidden behind an API and drivers or specific packages will need to be used. This will dictate the technical direction.

Once I got an LCD display screen for my Raspberry Pi. The only libraries written for it were in Python. This meant there was no point in me starting a project that needed the LCD screen in Ruby.

## Hosting Environments

Luckily most problems I encounter these days don’t have pre-existing hosting requirements which means I can let the solution dictate the hosting required.

This isn’t always the case – I used to have to deal with projects were the client already had hosting and the solution needed to sit on one of their servers. Virtualisation is an answer but not something that every IT department is keen to adopt, which means if they are running a Windows Server you need to write something that can be executed in a Windows environment.

## The Problem as it Evolves

Very few projects end as they were intended to during the first few meetings. User feedback, changing business objectives, clients not fully knowing what they wanted ahead of time, and a host of other reasons means that things change.

If the client suddenly needs offline access to something that was always assumed would be online you will need to adjust accordingly.

The pragmatic thing to do is to cleanly add on this new layer to the stack, but sometimes the change can be so severe that changing the technical direction of a project completely is the best way to proceed.

## Team Members Leaving and Joining

As a project continues the team members involved in it will change. 

Just like the team picked at the start of the project, these new people will have their own thoughts, opinions and experiences that could dictate the future of a project.

I have seen a team building something in one language, then everyone in that team leaves and the new team don’t know the language. The choice is to either get everyone up to speed to support one project or spend the time re-writing the project.

## Changing Technical Landscape

During the course of a project things change in the outside world, gems get made or fall out of favour, new build tools come along or get major overhauls.

I don’t believe you should immediately change things in a project based on these influences, but it is wise to have an understanding of the landscape in which your project sits.

## What do you think?

What do you think dictates how the technical direction of a software project can be influenced?