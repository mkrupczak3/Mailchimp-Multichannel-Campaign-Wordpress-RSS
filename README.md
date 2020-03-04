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
* [Digital Ocean](https://www.digitalocean.com/) hosting a Linux [Ubuntu](https://ubuntu.com/) server
* [Easy Engine](https://easyengine.io/) for installing Wordpress
* [Mailchimp for Wordpress plugin](https://wordpress.org/plugins/mailchimp-for-wp/) (M4WP) to add sign-up forms to site on Homepage and at bottom of every post
* (alternate) you could use [Jetpack for Wordpress](https://wordpress.org/plugins/jetpack/)

## RSS campaign with Mailchimp

Make use of RSS newsfeed provided by Wordpress websites
* Every Wordpress website provides an [RSS newsfeed](https://en.wikipedia.org/wiki/RSS) at example.com/feed in a standard format
* This feed contains the Titles, Dates, and contents of the website's posts
* By telling Mailchimp to monitor it, we can set up an automation to send out an email and post to Twitter whenever a new post is created

## Creating a Mailchimp RSS Campaign:
![Campaign](https://raw.githubusercontent.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/master/Screenshot_2020-03-04%20Campaigns%20Mailchimp.png)
Create a new campaign

![RSS Campaign](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaigns%20Mailchimp(1).png)
Search for "RSS" and create an "RSS" or "Blog" campaign

![Feed URL](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20RSS%20Feed%20Mailchimp.png)

Input the feed URL provided by our Wordpress site to Mailchimp

![Recipients](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Recipients%20Mailchimp.png)
Email to the whole list

![Campaign Info](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Setup%20Mailchimp(2).png)
Personalize our campaign info, customized using the [merge tag](https://mailchimp.com/help/all-the-merge-tags-cheat-sheet/) *|RSSFEED:DATE|* to inform and entice the reader

![Twitter](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Setup%20Mailchimp(1).png)
Set up an auto Twitter post, customized using the RSS [merge tag](https://mailchimp.com/help/all-the-merge-tags-cheat-sheet/) *|RSS:RECENTxxx|* where xxx is a number, in our case 10 indicating that the 10 newest posts _since the last email was sent_ as hyperlinks where the text is the title of the posts. 




