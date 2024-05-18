---
layout: post
title: Motion Capture Editing
---

**Objective:**

Explore filtering and displacement techniques for working with motion capture data.

I wanted to create two distinct edits of a motion capture walk cycle:
1. try to change the apparent personality of the character
2. exaggerate a motion

I started with a BVH file and parsed the motion file to group coordinates into different body parts. Then I filtered motion by body part, did some experimenting, and wrote out a new motion file.

These are some of my motion capture edits -- a sad walk, and waving back.
![Sad walk]({{ site.baseurl }}/images/sad.gif) ![Waving goodbye]({{ site.baseurl }}/images/wave.gif)