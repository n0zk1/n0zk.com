---
title: "Another campaign another day"
date: 2026-01-26T00:30:03+09:00
description: "Desc"
# weight: 1
tags: ["Research"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
disableHLJS: true # to disable highlightjs
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---
Yet antoher day, yet another campaign.
<!--more-->
Once again a campaign...  

Subdomain are starting to be more tailored for token stealing phishing campaigns – It may have been for a longer time to use subdomains as a tailored method specifically targeting specific organizations or sectors.  

At least it's what has been seen lately.  

Subdomains can be abused for making phishing URLs look more legit, the ability to create a subdomain requires certain amount of privilege within a domain, but the threat actors are able to gain that in various methods.  

This is mainly am quick and simple post about my finding.  

Recently did I stumble across a URL which saw interesting that I wanted to a further look.  

The URL were based upon: company.takenoverdomain.com  

The URL were specifically crafted for a bigger healthcare company as it led to that it could be seen this was a Healthcare & Pharmacy targeted on-going campaign. As the new subdomains constantly were created with small timeframe in between with a subdomain of Danish and Netherlands origin Healthcare & Pharmacy company names. 

There were at least only names from bigger and smaller Healthcare & Pharmacy organizations that mainly had origin of Denmark or Netherlands. From the initial hunting and the list gathered it were both typo squad sub domain names and exact domain names that were used in this campaign.  

My initial thoughts indicate that the threat actor may have used GenAI for creating the typo squad list and domain names.  

The URL had several URL redirects as to not get evade by initial detection by security tools, but what there was under the hood were Fake Microsoft SharePoint login page for Token theft.  


Key topics from a highlevel analysis 

-