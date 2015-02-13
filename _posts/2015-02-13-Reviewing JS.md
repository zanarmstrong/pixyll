---
layout:     post
title:      Reviewing Javascript
summary:    Skimming "Learning Javascript" to see what I've missed
categories: learning
---

I'm reading Tim Wright's "Learning Javascript" book. While I've been using Javascript on and off over the last 18 months and am feeling quite comfortable, I decided it would be nice to go through this recommended fundamentals book. It's useful to see if there are any major concepts or functions that I've missed while learning by doing. And, I'm finding it nice to also see how much I know now. 

Since I've been learning primarily through creating visualizations and using D3, my focus has been more on SVG/vis than this book's which is a bit more about general web development and gives examples with input forms. For example, one of the concepts I haven't used are "blur" and "focus" events. These seem more useful for forms, etc. But, I could see them being valuable for visualizations to guide the user, especially to highlight certain text in connection with the viz. 

Speaking of events, I need to try using "orientation change" for mobile/tablet/hand-helds!  It looks fun & powerful.  

I've use both anonymous and callback functions regularly. But, it was nice to put them in a more theoretical context rather than just doing what works. 

It was interesting to see how things that I use all the time via D3 likely relate to more fundamental methods like querySelector and querySelectorAll as well as getters and setters for attributes. I've also typically navigated by id or type of element, so it was nice to be reminded that you can access parents, children, and siblines of nodes in the DOM. Additionally, I've used "event.preventDefault" to ensure that touching a visualization on mobile interacts with the vizualization rather than triggering scrolling. But, I hadn't really thought about it as a more general purpose concept. 

I usually use "if else" rather than "switch" statements. But, might be worth trying "switch"?

The book also spoke to accessibility frequently. For example, they distinguished between hiding an element by moving it off the screen vs by using "display: none". The main difference is for accessibility, that you can include text for a screen reader to explain that the view has changed if you're moving it off the screen. 

