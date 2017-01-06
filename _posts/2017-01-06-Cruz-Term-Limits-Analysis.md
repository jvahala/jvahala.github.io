---
layout: post
title: "Ted Cruz and Term Limits"
date: 2017-01-06
---
[House-Term-Dists]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/term-distribution-house.png?raw=true "House Members Separated by Current Term Limits"
[Senate-Term-Dists]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/term-distribution-senate.png?raw=true "Senate Members Separated by Current Term Limits"
[House-Ineligible-Counts]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/count-ineligible-house.png?raw=true "House Members Ineligible for Re-Election Caused by Term Limits"
[Senate-Ineligible-Counts]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/count-ineligible-senate.png?raw=true "Senate Members Ineligible for Re-Election Caused by Term Limits"
[House-Ineligible-Percents]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/percent-ineligible-house.png?raw=true "Percentage of House Members Ineligible for Re-Election Caused by Term Limits"
[Senate-Ineligible-Percents]: https://github.com/jvahala/jvahala.github.io/blob/master/_posts/images/20170106/percent-ineligible-senate.png?raw=true "Percentage of Senate Members Ineligible for Re-Election Caused by Term Limits"

## Ted Cruz and Term Limits

Ted Cruz recently [proposed](https://www.cruz.senate.gov/?p=press_release&id=2940) a term limit ammendment to the constitution. He reasoned, "D.C. is broken. The American people resoundingly agreed on Election Day, and President-elect Donald Trump has committed to putting government back to work for the American people. It is well past time to put an end to the cronyism and deceit that has transformed Washington into a graveyard of good intentions." However, due to Mr. Cruz's well-known far-right stances, I questioned if this was sincere and not a means to knock out significantly more Democrats than Republicans in upcoming elections. 

This post looks into how the proposed term limits (three two-Year terms for House of Representatives members and two six-year terms for Senate members) would alter the power dynamic after the current members of congress are next up for re-election. Later, I'll update this post with the optimal term limits for shifting the balance of power in both the Democratic and Republican directions. 

## Current Congressional Distributions

Using data collected with the [congress-legislators](https://github.com/unitedstates/congress-legislators) repo (specifically the `current-legislators.yaml` file), I plot how many House and Senate members are in their `n`-th term, visualized by party affiliation and by who would be ineligible for re-election if the Cruz term limit ammendment were implemented.

![alt text][House-Term-Dists]{:width="400px"}
![alt text][Senate-Term-Dists]{:width="400px"}

Clearly a whole bunch of members would be out of a job. It's also interesting that there are so many first and second term congressmen. Without looking into any merits of the longtimers, it seems like those people must be there for a reason. Maybe term limits would only kick out those people who deserve to represent their consistuents? This is probably not a universal truth, but its worth thinking through.

It's hard to tell who wins most Cruz's choice of term limits, so we will need to make it more clear. 

## Newly Ineligible Members

Incumbents are known to have an [advantage](http://www.thisnation.com/question/016.html) in congressional elections due to name recognition, funding, and on-the-job training. Thus, if we got rid of a large group of perennial incumbents, the resulting free-for-all would be more even than the typical election. Opposing parties would have a greater chance to grab previously impossible seats. In order to show how various term limits affect each party, we look at how a certain term limit for the House or Senate chanes the actual number of members of each party as well as how it looks like in percentage terms. First, we look at the House. 

![alt text][House-Ineligible-Counts]{:width="400px"}
![alt text][House-Ineligible-Percents]{:width="400px"}

Next, we look at the Senate.

![alt text][Senate-Ineligible-Counts]{:width="400px"}
![alt text][Senate-Ineligible-Percents]{:width="400px"}
