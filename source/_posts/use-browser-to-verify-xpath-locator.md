---
title: Use browser to verify xpath locator
layout: post
date: 2018-08-03 07:55:09
tags:
- xpath  
---

In today's post, I will demonstrate how to create an web element locator by using Xpath and verify it in DOM. This can be done right in Google Chrome and Safari.  
<!--more-->

---

## The Problem
When it comes to web front testing, in order to create robust automated tests, one of the important step is to be able to locate any web element efficiently and reliably. All subsequent steps in test case completely depends on the fact that correct locator can be identified for any interaction or assertion to take place. 

Let's say I have constructed a locator by using Xpath, but before I proceed with interacting it and applying any assertions, I need to answer this question:

<blockquote class="blockquote-center">**how do I know it is the right locator to use for my Selenium tests?**</blockquote>

You could just run your test and Selenium would give you an error if it is unable to find the element by using provided locator. But this become very tedious and time-consuming as your test grows and user interactions becomes complex.

Modem browsers like Google Chrome or Safari, have built-in functionality allow locating element by Xpath, this greatly helps the process of creating and verifying a valid locator, thus makes writing automated front-end Selenium based bests much more streamlined.

##  A Solution
I have successfully verified this approach on both Google Chrome (including chromium) and Safari. Firefox, unfortunately doesn't support this just yet.

### Google Chrome
1. Open Chrome browser and go to the site under test.
1. Open the Developer Tools window.
1. Make sure you are in the Developer Tools window, navigate to Elements tab.
1. `command + F` or `control + F` on Windows, you will notice a search bar displays, this is where you will enter your Xpath locator.
1. Enter Xpath locator, now if your locator is valid, you will see it highlighted both in DOM and your browser window, given that it is visible and not hidden by some scripts. Notice that if there is more than 1 match found, it will also be displayed as well.
1. To make it even easier when selecting element, you want to activate the Element Selector by `option + command + C` or `alt + control + C` on Windows. Then just click on the element you want, it will be highlighted in DOM. You can then customise your Xpath to your need as you can see its HTML attributes.
1. Now you can be certain that your locator returns correct element. To use this Xpath locator, just copy and past it to your POM and be sure to use Xpath as locator strategy.

{% asset_img s1.png %}

### Safari
Safari use follows pretty much the same pattern as in Google Chrome, they even share the same short-cut keys. However I prefer Google Chrome over Safari, especially when building my automated tests. It is mostly due to the fact that Chrome handles some short-cut key combinations better.

An example would be when you want to pause a javascript running at the background, so that dialogue box doesn't disappear and you can see its DOM. This is easily done in Chrome, just type `command + \` then it would stop javascript from executing. However this is not the case in Safari, unless you click its Developer Tools window first, this can be an annoyance.

## Conclusion
I hope you find this useful, it has helped me a lot in my testing. Because Xpath is very flexible, you can locate pretty much everything that's in the DOM. I quite often have to refer to this [Xpath Cheetsheet](https://devhints.io/xpath), there is just so much trick you can do.


---
