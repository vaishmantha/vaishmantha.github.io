---
layout: post
title: Motion Capture Editing
---

Objective: Explore filtering and displacement techniques for working with motion capture data.

I wanted to create two distinct edits of a motion capture walk cycle and try to change the apparent personality of the character, or an exaggerated motion. I started with a BVH file and parsed the coordinates into different body parts. Then I operated on the motion files by parsing them, filtering the motion by body part, and writing out a new motion file which the viewer can read.

These are some motion capture edits I made programatically.
![Sad walk]({{ site.baseurl }}/images/sad.gif) ![Waving goodbye]({{ site.baseurl }}/images/wave.gif)