# Using Mailchimp with Wordpress's RSS feed to email subscribers with new posts
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


# Creating a Mailchimp RSS Campaign:


## Create a new campaign
![Campaign](https://raw.githubusercontent.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/master/Screenshot_2020-03-04%20Campaigns%20Mailchimp.png)




## Search for "RSS" and create an "RSS" or "Blog" campaign
![RSS Campaign](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaigns%20Mailchimp(1).png)




## Input the feed URL provided by our Wordpress site to Mailchimp
![Feed URL](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20RSS%20Feed%20Mailchimp.png)




## Email to the whole list
![Recipients](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Recipients%20Mailchimp.png)




## Personalize our campaign info, customized using the [merge tag](https://mailchimp.com/help/all-the-merge-tags-cheat-sheet/) \*|RSSFEED:DATE|\* to inform and entice the reader
![Campaign Info](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Setup%20Mailchimp(2).png)




### Set up an auto Twitter post, customized using the RSS [merge tag](https://mailchimp.com/help/all-the-merge-tags-cheat-sheet/) \*|RSS:RECENTxxx|\*. xxx is a number, in our case 10 indicating that the 10 newest posts _since the last email was sent_. They will show up as hyperlinks where the text is the title of the posts. 
![Twitter](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Setup%20Mailchimp(1).png)




## Select the full width campaign template for more space
![Template](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20HTML%20Mailchimp.png)




## Now we customize our email template
![Email template](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Template%20Designer%20Mailchimp(1).png)




#### Greeting for the user in text:
```Hello, *|IF:EMAIL ! <<Email Address>>|**|EMAIL|**|ELSE:|*friend*|END:IF|*, You may be interested in new article(s) I've written on my website, matthew.krupczak.org:```


##### In my signup form, I only ask for an email address (and not first name / last name) in order to reduce user friction. 


##### If a user is reading the campaign in email, it would be nice to mention their email address specifically so they know it's not mass spam.


##### If a user is viewing the campaign page from Twitter, no email address will be available. We can greet them as 'friend' instead


##### This can be accomplished using [conditional block tags:](https://mailchimp.com/help/all-the-merge-tags-cheat-sheet/#Conditional_block_tags)
```*|IF:EMAIL ! <<Email Address>>|**|EMAIL|**|ELSE:|*friend*|END:IF|*```

If the user's email address is not a placeholder from Mailchimp's software, print the user's email. Else, print "friend".


## Let's look at our template again:
![Email template](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Template%20Designer%20Mailchimp(1).png)




### \*|RSS:RECENTxxx|\*. xxx is a number, in our case 10 indicating that the 10 newest posts _since the last email was sent_. They will show up as hyperlinks where the text is the title of the posts. 
[RSS Merge Tags](https://mailchimp.com/help/rss-merge-tags/) merge tags are included which will show the title, date of publication, and full HTML content of the latest post on my website




## Dynamic Social Cards:
![Social Card](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Pre-delivery%20Checklist%20Mailchimp.png)
### To inform and entice the reader, I use a [RSS Merge Tag](https://mailchimp.com/help/rss-merge-tags/) to include the date and title of my most recent post


## Social Card Preview:
![Social Card Preview](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/raw/master/Screenshot_2020-03-04%20Campaign%20Builder%20-%20Pre-delivery%20Checklist%20Mailchimp(1).png)

# .
# . 
# .
# Putting it all together:
## The Final Product:
![Matt's Tech Bytes new posts for 03 04 2020](https://github.com/mkrupczak3/Mailchimp-Multichannel-Campaign-Wordpress-RSS/blob/master/Screenshot_2020-03-04%20Matt's%20Tech%20Bytes%20new%20posts%20for%2003%2004%202020.png)
