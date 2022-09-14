+++
title = "OhSint | TryHackMe"
tags = ["tryhackme", "open source intelligence", "osint"]
date = "2022-09-13"
+++

{{<figure src="/tryhackme/ohsint/title.png">}}

# Intro
It seems like the creator of this box wants us to sharpen our open source intelligence (osint) skills. We are given a photo of what looks like the old windows XP desktop.

&nbsp;
# Download photo and exiftool
{{<figure src="/tryhackme/ohsint/taskfile.png" >}}

Knowing that personaly identifiable information (PII) can sometimes be embeded in the meta data of a photo; a program like -- exiftool -- can help us extract that information. If you don't have exiftool or need to know how to install it, I always recomend going straight to the source isnstead of perusing random blog pages. A quick search of "exiftool github" lead me to their GitHub repo which then lead me to their website https://www.exiftool.org. The website clearly outlined the installation process for whatever operating system you are running on. 

&nbsp;
# Run exiftool
{{<figure src="/tryhackme/ohsint/exiftool1.png">}}

After running exiftool, we have GPS coordinates of where the photo was taken and a copyright name. Let's see what the internet has on that copyright. A quick search yields an oddly named users' twitter page who also happens to love taking photos ^_^, seems like we are on the right track.

&nbsp;

# Question 1
{{<figure src="/tryhackme/ohsint/usertwitter.png" >}}

Looking at the users twitter page gives us an answer to the first question.

    AWNSER: cat

&nbsp;

# Question 2
We can gleam two things from this users twitter page: they get free wifi from their house and their wifi mac address is

    B4:5D:50:AA:86:41

Which we now have permission to "go nuts" with. Does that mean I can also legally hack into this WiFi rotuer with the password I find later? I'm not sure, but I don't think this justification would hold up in a court of law. A website like wigle.net or a program like GEOWiFi will give us WiFi geolocaiton data for that router/BSSID. If you use wigle.net, head to VIEW -> BASIC SEARCH... login... zoom out and notice the purple circles over london. 
{{<figure src="/tryhackme/ohsint/wigle.png" >}}

    ANSWER: london

&nbsp;
# Question 3
This awnswer can also be gleamed from our geolocation enumeration. If you are on wigle, zoom in all the way over the purple circles until you see the name of the SSID belonging to that BSSID.

{{<figure src="/tryhackme/ohsint/ssid.png" >}}

    ANSWER: UnileverWiFi

&nbsp;
# Question 4
If we go back to our search engine there is also a GitHub repo and a Wordpress site that looks like it may belong to our target. Looking at the GitHub repo description in the search engine shows the users gmail address. 

{{<figure src="/tryhackme/ohsint/search.png" >}}

    ANSWER: OWoodflint@gmail.com

&nbsp;
# Question 5
We found this email information on Github.

    ANSWER: GitHub

&nbsp;
# Question 6
Almost done! Taking a look at the users blog shows us that they are currently in New York. 

{{<figure src="/tryhackme/ohsint/location.png" >}}

    AWNSWER: New York

&nbsp;
# Question 7
This last question seems like it will be quite a leap. However, it seems something was wrong with this box when I did it because their password is very obviously shown in the blog post. If the site wasn't broken, we would have probaly had to search through the blogs source code looking for some sort of hint. This seems like a resonable thing to do given how transparent this user was to the outside world with PII. Looking through some other guides it looks like the source code used to look like this. 

https://doretox.com/ohsint-tryhackme-walkthrough/

{{<figure src="/tryhackme/ohsint/source.png">}}

    ANSWER: pennYDr0pper.!

This last question didn't make any sense to me, I can't think of a scenario where someone would randomly embed their password withink the source code of a blog or accidentally expose that information in a blog post... Maybe I over estimate our target. Regardless, a quick and fun refresher for my osint skills and a nice reminder of www.wigle.net!