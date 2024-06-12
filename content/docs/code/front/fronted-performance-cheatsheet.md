---
title: "如何提高前端网站加载速度"
weight: 2
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![如何提高前端网站加载速度](/img/code/front/fronted-performance-cheatsheet.gif "如何提高前端网站加载速度")

How to load your websites at lightning speed?

Check out these 8 tips to boost frontend performance:

* Compression
  Compress files and minimize data size before transmission to reduce network load.

* Selective Rendering/Windowing
  Display only visible elements to optimize rendering performance. For example, in a dynamic list, only render visible items.

* Modular Architecture with Code Splitting
  Split a bigger application bundle into multiple smaller bundles for efficient loading.

* Priority-Based Loading
  Prioritize essential resources and visible (or above-the-fold) content for a better user experience.

* Pre-loading
  Fetch resources in advance before they are requested to improve loading speed.

* Tree Shaking or Dead Code Removal
  Optimize the final JS bundle by removing dead code that will never be used.

* Pre-fetching
  Proactively fetch or cache resources that are likely to be needed soon.

* Dynamic Imports
  Load code modules dynamically based on user actions to optimize the initial loading times.

Over to you: What other frontend performance tips would you add to this cheat sheet?