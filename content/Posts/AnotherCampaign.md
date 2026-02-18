---
title: "Another AiTM campaign, another day"
date: 2026-02-18T00:30:03+09:00
description: "Once again a campaign..."
# weight: 1
tags: ["Research"]
author: "n0zk"
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

This is mainly a quick and simple post about my finding.  

I did recently stumble across a URL which saw interesting that I wanted to a further look.  

The URL were based upon: **company.takenoverdomain.com**  

The URLs were carefully designed to target major healthcare and pharmacy companies as part of the campaign. New subdomains were rapidly generated with only brief timeline between them. The campaign specifically focused on companies based in Denmark and the Netherlands.

There was only names from bigger and smaller Healthcare & Pharmacy organizations that which are originating from Denmark or the Netherlands. In the initial hunting phase, the list gathered were both typosquad subdomains and exact company names used in the subdomain.   

My initial thoughts indicate that the threat actor may have used GenAI for creating the typosquad list and domain names, and mostlikely also used it for the Webapp.. 

The URL created had several URL redirects as to not get evade by initial detection from security tools but what there were actually under the hood was a Fake Microsoft SharePoint login page to steal the Primary token from the user account.   

- What you will be met by was a simple website with a "form" and the Sharepoint logo, were the victim could fill out their email to start out and afterwards password...

**Key topics from a highlevel analysis** 
- The domain(s) used, were mainly a parked domian(s) - The domains were usually parked for a few weeks before usage.  

- Several redirects through different ASN(s)

- Some part of the webapp had an "required field(s)" before the threat actor receives it such as email and a specific "Visitor token" generated when the victim accessed the site but sadly I wasn't able to analyze all of the scripts that made the checks in the webapp but there was a difference in the webapps created which revealed some of webapps had minor changes in the code. In some part of the webapps it was required to have both scripts but in some other web was it only the email script that ran through before it handled the request further and sometimes wasn't there any checks. 

- "Email_checker.php" Based on the analysis, the email checker script was used to ensure that it had MX records assigned to the domain of the email by making DNS lookups before the "form" were accepted. 

- "Vistior_token-php" The script acts as an "identifier" and creates a 32 character random generated text string acting as a "token" which was required both in the email check phase and when the "form" were sent. 

Another note, the webapp appered to had some changes afterwards for a bit similiar campaign but different initial AiTM campaign were it's Fake Teams meetings... 