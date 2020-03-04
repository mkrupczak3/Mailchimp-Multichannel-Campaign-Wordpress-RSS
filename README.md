# Mailchimp Multichannel Campaign Wordpress RSS
![Krupczak Logo](https://raw.githubusercontent.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/master/krupczak-1-4.png "Krupczak Logo")

## Scenario:

On my website [matthew.krupczak.org](https://matthew.krupczak.org) AKA [foobarbat.org](http://foobarbat.org):
* I would like to make it so that readers can sign up to be notified of new posts via email on the Homepage or at the bottom of any post
* An email should be sent out to the reader daily if new posts are created
* The email should contain a list of the posts created since they were last notified, along with the HTML content of the latest post in the body of the email
* The campaign should auto populate to Twitter as well

## Wordpress setup

Use Existing Wordpress setup:
* Digital Ocean hosting a Linux Ubuntu server
* Easy Engine for installing Wordpress
* Mailchimp for Wordpress plugin (M4WP) to add sign-up forms to site on Homepage and at bottom of every post

## RSS campaign with Mailchimp

Make use of RSS newsfeed provided by Wordpress
* Every Wordpress website provides an [RSS newsfeed](https://en.wikipedia.org/wiki/RSS) at example.com/feed in a standard format
* This feed contains the Titles, Dates, and contents of the website's posts
* By telling Mailchimp to monitor it, we can set up an automation to send out an email and post to Twitter whenever a new post is created

## Screencaps, Mailchimp configs, and Merge tags


