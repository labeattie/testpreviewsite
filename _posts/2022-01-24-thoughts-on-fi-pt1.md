---
title: "My Take on Financial Independence - Overview"
mathjax: true
layout: post
categories: finance
---

One of my biggest focuses over the past year or two has been on personal finance. It's pretty much a staple subject of any self-improvement effort, and, as someone perhaps a bit too into spreadsheets, I've always been interested in my and my family's finances. 

I was beginning to dig deeper into the subject and took a lot of inspiration from the FIRE community, which stands for "Financial Independence Retire Early". Even if I could, I personally have no intention of retiring anytime in the next decade or two, but I'm very much into the idea of achieving the Financial Independence (FI) side of that idea. 



In this two-part series, I'd like to discuss several ideas about financial independence and how my thinking on it has developed over the last year. This first article will go over some of the primary tenets of the FIRE framework and my takeaways after experimenting with them.

## Tenet 1: The 4% Rule
How much money do you need to retire? We don't even have to use such a loaded word. How much money do you need to never have to work again? If you look at many online resources and calculators, they base this answer off of the amount of money you earn. 

This is a major pet peeve of mine, as this usually assumes you spend nearly all of the money you make. What if I make 10 million dollars a year? I don't, but if I did, I would hope I could retire a lot sooner than age 65. Instead, the amount of money you need to retire should be based off of how much money you spend. This can also be thought of as "how much your lifestyle costs".

A commonly used rule of thumb in the FIRE community is the "4% rule". This postulates that, if you withdraw 4% or less per year of a stock/bond portfolio's starting value (adjusted for inflation), you are very unlikely to ever run out of money. Another way to state this is, if you save up 25x your annual spending, and have it invested (hopefully in low-fee index funds), then you likely never need to earn another cent.

This is based off of something called "The Trinity Study". Some people think the 4% rule is a bit optimistic, and others a bit conservative, but I think it is an excellent starting point. Note that I'm assuming you will spend approximately the same amount in retirement that you spend right now (adjusted for inflation). If you have good reasons to think otherwise, then the target would be 25x that number. However I tend to think the best predictor of future spending is current spending.

## Tenet 2: Savings Rate
If we make some simplifying assumptions, holding your spending and earnings relatively constant for a long time (adjusted for inflation), and assuming an inflation adjusted return on stocks, then an interesting conclusion can be drawn. The time until you are financially independent is dependent on one single variable: your savings rate.

Your savings rate is simply the percentage of the money you take home that gets saved and invested, rather than spent. This is interesting because it's independent of the total amount of money you make. If you save 50% of your after-tax income, you will become financially independent in approximately 17 years whether you earn $40,000 per year or $400,000.

Here is a chart I calculated, assuming an inflation adjusted average return on investment of 5% (the S&P 500's historical average is about 6.6%). I will include a little bonus section at the end with how to calculate these numbers.

![FI_years](/testpreviewsite/assets/fi table.png)

This might be surprising at first, but spending plays two roles in the financial independence equation. It determines how much of your money gets saved, but also how much total money is needed. 

I often hear a quip that it's better to focus on earnings than savings, as earnings are theoretically infinite, whereas you can only spend so little. I don't buy this idea at all. Because spending is in the denominator of the "time to FI" math, reducing spending increases your money's power asymptotically. By way of illustration, if you spent $0 per year (your lifestyle costs nothing), how much money do you need to make to retire? None, you're already FI!

Mr. Money Mustache is a blogger who wrote most of my favorite articles on financial independence, and he has a much better post than mine explaining these concepts here: [The Shockingly Simple Math Behind Early Retirement][simple_math]. I see his "years till retirement" chart matches mine, which is encouraging. 

## My Savings Efforts
Many of the FIRE practitioners I come across online have been able to take these concepts to impressive lengths, saving 50%-75% (or a few even more) of what they earn. And many have been able to leave traditional employment in their early thirties. 

I didn't become interested in financial independence until my early thirties, and had always saved more like 20%-30% percent of my or my family's income. So we were on a strong foundation, but nowhere close to FI. Additionally, as stated earlier, I don't plan to quit working anytime in the near future even if I could. 

However, I was more than inspired enough to start tracking my expenses thoroughly, trying to eliminate what waste I could (and dragging my wife along for the ride :P). I also tried some random ways to save or make a bit more money that could make good material for future posts. 

This improved our savings rate, but I found it far more difficult than I expected to achieve 50% or more. As a result, we're probably still something like 10-15 years from financial independence.

## Why FI?
You might ask why I'm so enamored with the idea of financial independence if I don't have a desire to quit working as soon as possible. This is a fair question, and I have 3 main points as answers. 

First, I just want to do an impressive job managing our personal finances. I don't want to sacrifice things that are important to me and my family along the way, but if being intentional with our spending can leave us wealthy down the line, I think that sounds well worth it.

Secondly, I'm just obsessed with the idea of having options and freedom. I fully expect I would want to stay at my job and keep working if I achieved FI tomorrow, but I think I would feel very differently about it. I would fully internalize the fact that I was there because I want to be and not because I need to be. Mr. Money Mustache has a great article on this concept: [Retire in Your Mind Even If You Love Your Job][swami].

Lastly, the future is just uncertain. Who's to say I will still love my work in 10 years, or that my wife will? What if we want to do something wild like pack up and move to another country? I don't anticipate any of the above, but I love the idea of being prepared for something similar.

## Conclusions
So while buckling down to a truly impressive savings rate wasn't in the cards right now, I still had some important takeaways from these ideas. First, that the FIRE community are some of the clearest thinkers with regard to personal finance out there. I typically will look to them for deciding where to allocate money in retirement accounts or for other similar issues. And secondly, being intentional with spending is the biggest lever that most of us have available to pull if we want to affect our financial futures. I plan to track spending monthly without fail.

## Bonus: How to Calculate Years to FI
I calculated the numbers in that chart myself in a spreadsheet using the engineering economics formula for "future worth given an annual amount". This formula can be found online and I got it from my NCEES FE Exam booklet I still have on my office bookshelf. My engineering friends can dig theirs up for reference! 

$$\frac{F}{A} = \frac{(1-i)^n-1}{i}$$

Where:
* F = future worth = (1-savings rate)*25
* A = annual amount = savings rate
* i = interest rate
* n = time in years

I then simply rearranged the equation to solve for n, as shown below.

$$(1-i)^n = Fi/A+1$$

$$ln((1-i)^n) = ln(Fi/A+1)$$

$$n*ln(1-i) = ln(Fi/A+1)$$

$$n = \frac{ln(Fi/A+1)}{ln(1-i)}$$

So as an example, a 40% savings rate and a 5% real return would get plugged into that final equation like so:

$$\frac{ln(25(1-40\%)*5\%/40\%+1)}{ln(1-5\%)} = 21.6yrs$$

In the next finance article, which I will post a couple of weeks from now, I will talk about the incremental benefits of saving your money prior to reaching FI, as well as balancing saving for the future with living a gratifying life in the present. Thanks for reading!

[simple_math]: https://www.mrmoneymustache.com/2012/01/13/the-shockingly-simple-math-behind-early-retirement/
[swami]: https://www.mrmoneymustache.com/2011/04/30/weekend-edition-retire-in-your-mind-even-if-you-love-your-job/