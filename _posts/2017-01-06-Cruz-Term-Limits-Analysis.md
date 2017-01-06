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

This post looks into how the proposed term limits (three two-year terms for House of Representatives members and two six-year terms for Senate members) would alter the power dynamic after the current members of congress are next up for re-election. Later, I'll update this post with the optimal term limits for shifting the balance of power in both the Democratic and Republican directions. 

## Current Congressional Distributions

Using data collected with the [congress-legislators](https://github.com/unitedstates/congress-legislators) repo (specifically the `current-legislators.yaml` file), I plot how many House and Senate members are in their `n`-th term, visualized by party affiliation and by who would be ineligible for re-election if the Cruz term limit ammendment were implemented.

![alt text][House-Term-Dists]{:width="400px"}
![alt text][Senate-Term-Dists]{:width="400px"}

Clearly a whole bunch of members would be out of a job. It's also interesting that there are so many first and second term congressmen. Without looking into any merits of the longtimers, it seems like those people must be there for a reason. Maybe term limits would only kick out those people who deserve to represent their consistuents? This is probably not a universal truth, but its worth thinking through.

Also, the House Republicans have far more second term members than Democrats, and the House Democrats have far more third term members than Republicans. If Cruz's three-term limit were imposed, then it seems like Republicans would have the heavy advantage in the new contests. We will see if this guess holds up to further investigation.

## Newly Ineligible Members

Incumbents are known to have an [advantage](http://www.thisnation.com/question/016.html) in congressional elections due to name recognition, funding, and on-the-job training. Thus, if we got rid of a large group of perennial incumbents, the resulting free-for-all would be more even than the typical election. Opposing parties would have a greater chance to grab previously impossible seats. In order to show how various term limits affect each party, we look at how a certain term limit for the House or Senate chanes the actual number of members of each party as well as how it looks like in percentage terms. 

### House of Representatives
First, we look at the House. 

![alt text][House-Ineligible-Counts]{:width="400px"}
![alt text][House-Ineligible-Percents]{:width="400px"}

As a sanity check, we see that if a one-term limit were imposed, then 100% of Congress members would be ineligible for re-election. Woot. For the House, we see that at a three-term limit, Democrats lose ~80% of their members while Republicans lose ~70%. These numbers translate to 78 Republicans to 38 Democrats left standing from the first culling. Approximately a 2:1 ratio. It's an open question how much this ratio would matter, but I'd guess the 38 being so small (9% of the 435 members) would make the new members coming much more important. There wouldn't be a buffer for Democrats to take extra losses in the oncoming elections. The key for the Republicans is that the strong majority of their members in the House are in their early terms; the Democrats are better spread through the terms. 

It seems like the Cruz house limit is almost a compromise with the Democrats. If Cruz's staff we're doing this kind of analysis, they'd know a better choice for Republicans would be something deeper in the terms for Congressmen. The differences between each percentage (`dem_percent - rep_percent`) are

```
[0, 0, 11, 5, 19, 20, 15, 16, 17, 16, 15, 12, 11, 6, 3, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

So the best choice for Cruz in terms of party politics would have been a five- or six-term limit for the House of Representatives. The next election cycle for Republicans would lose 19-20% fewer members than Democrats. Democrats would term limits more along 14-16 terms region to minimize their losses relative to Republicans at less than 6%. 

### Senate
Next, we look at the Senate.

![alt text][Senate-Ineligible-Counts]{:width="400px"}
![alt text][Senate-Ineligible-Percents]{:width="400px"}

We see from the percentage plot that Cruz's proposed two-term limit would do nothing to the immediate ratio between Republicans and Democrats. Thus, there's no hit to Republicans or Democrats. But, if we look at the percent difference values (again, `dem_percent - rep_percent`), we have 

```
[0, 0, -8, -11, -4, -9, -3, 2, 0, 0, 0]
```

So Democrats would actually be better served by longer (once again) term limits than those proposed. Their ideal term limit seems to be four terms, which results in an 11% swing in their favor. Republicans would much prefer the proposed term limit. The two independents in the Senate (Bernie Sanders and Angus King) are pretty much screwed by term limits simply because they are so rare to begin with. 

## Future Work

Later I plan to look into each district that would be lost with Cruz's term limits and see the margin of victory of the incumbent in each. From this, I'll infer how the district leans party-wise and whether its drawn well enough to fend off the opposing party. I'll then make a prediction of how the shift of power would change under various term limit programs. 

I also would like to add more research and links about how term limits have worked or failed in the past, so I (and others) can make educated decisions about supporting such an ammendment to the constitution (with our votes for congress members). 
