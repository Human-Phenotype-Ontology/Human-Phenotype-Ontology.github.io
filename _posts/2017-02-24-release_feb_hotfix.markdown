---
layout: post
title:  "February release (hotfix)"
date:   2017-02-24 09:00:00
categories: 
---

## February 2017 release (hotfix)

We have introduced a new feature in one of our last releases, where we allowed a primary label to marked as being for laypersons. 
Although this was transferred into valid OBO syntax, several consumers of hp.obo weren't prepared for this change.

Thus we have fixed that by copying the primary (and lay) label into a new synonym, which is then marked as lay.

This hopefully helps.

Best,
Sebastian