---
title: "Another AiTM campaign, another day"
date: 2026-01-26T00:30:03+09:00
description: "Once again a campaign..."
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
I'll keep the post updated with additional details and screenshots!
<!--more-->
Subdomain are starting to be more tailored for AiTM campaigns – It may have been for a longer time to use subdomains as a tailored method specifically targeting specific organizations or sectors.  

At least it's what has been seen lately.  

Subdomains can be abused for making phishing URLs look more legit, the ability to create a subdomain requires certain amount of privilege within a domain, but the threat actors are able to gain that in various methods.  

This is mainly am quick and simple post about my finding.  

Recently did I stumble across a URL which saw interesting that I wanted to a further look.  

The URL were based upon: company.takenoverdomain.com  

The URLs were specifically crafted for a bigger healthcare company as it led to that it could be seen this was a Healthcare & Pharmacy targeted on-going campaign. As the new subdomains constantly were created with small timeframe in between with a subdomain of Danish and Netherlands origin Healthcare & Pharmacy company names. 

There were at least only names from bigger and smaller Healthcare & Pharmacy organizations that mainly had origin of Denmark or Netherlands. From the initial hunting and the list gathered it were both typo squad sub domain names and exact domain names that were used in this campaign.  

My initial thoughts indicate that the threat actor may have used GenAI for creating the typo squad list and domain names, mostlikely also the Webapp.. 

The URL had several URL redirects as to not get evade by initial detection by security tools, what there were under the hood was a Fake Microsoft SharePoint login page to steal the Primary token.  

- What you would be met by were a simple website with a "form" and the Icon of Sharepoint, were the victim could fill out their email to start out and afterwards password...

Key topics from a highlevel analysis 
- The domain(s) used, were mainly a parked domian(s)

- Several redirects through different ASN(s)

- Some of the Webapp's had a "required field(s)" before the victim will submit - Sadly I weren't able to get in touch of all of the scripts that make the checks. But the webapps had a difference as some of them didn't had the same "required field(s)" 

- "Email_checker" Based on the analysis, the Email checker were used to ensure that it were a legtime mail before the "form" were accepted. 

- "Vistior_token" were required both in the Email check phase and when the "form" were sent.

Another note, the webapp appered to had some changes afterwards for a bit similiar campaign but different initial AiTM campaign were it's Fake Teams meetings... 