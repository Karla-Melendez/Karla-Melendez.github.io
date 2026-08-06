---
layout: post
title: "Getting My Own Site Found: What SEO Taught Me About Discoverability"
date: 2026-08-06
categories: technical-writing
---

A few weeks ago, I did what most people do after publishing something new: I searched my own name. LinkedIn came up first, as it always does. Then I searched "Karla Melendez GitHub", and my repository showed up, but not my GitHub Pages site, the one with my actual writing on it. I tried a few more variations. Nothing. The site I'd been building out, post by post, might as well not have existed as far as Google was concerned.

As a technical writer, this stung a little more than it might for most people. I'd just written, on this very blog, about how content today has to be discoverable by both humans and bots—self-contained, structured, parsable. And here I was, having apparently not applied a single one of those principles to my own site's visibility.

So I did what I'd tell any end-user to do when something isn't working the way they expect: I investigated. I ran searches, compared what I found against Google's own documentation, and talked it through with an LLM to sanity-check each step before acting on it.

## Confirming the Problem

The first useful trick was a simple one, searching `site:karla-melendez.github.io` directly in the search bar. If Google has indexed a site, this returns every page it knows about. If it returns nothing, the site hasn't been crawled at all yet.

I ran it. Nothing came back. Not "ranking poorly." Not "buried on page five." Nothing. My site wasn't in Google's index at all, despite having live backlinks pointing to it from my LinkedIn Featured section, my resume, my cover letters, and my Indeed and Glassdoor profiles.

The fact that nothing came back at all made a difference. A ranking problem and a discovery problem call for completely different fixes, and I'd been about to solve the wrong one.

## Telling Google the Site Exists

Backlinks help Google *eventually* find a site, but they're not a guarantee, and they're definitely not fast. What actually moves things along is telling Google directly, through Google Search Console.

I verified ownership of the site (using the URL prefix method with an HTML file, since a GitHub Pages subdomain doesn't give DNS access for the domain-level option), checked that my sitemap.xml already existed—it did, generated automatically through the jekyll-sitemap plugin—and submitted it. Within Search Console, I also used the URL Inspection tool to directly request indexing on my homepage.

The homepage got indexed in a matter of minutes, to my great relief. Watching "Page is indexed" appear where there had been nothing before brought me such joy!

## The Part That Looked Like a Problem But Wasn't

Not everything went smoothly right away. My sitemap showed a status of "Couldn't fetch," even after I resubmitted it. My first instinct was to assume something in my file was broken—malformed XML, a bad path, something in robots.txt quietly blocking the crawler.

I checked all of it. The sitemap loaded cleanly in a browser. My robots.txt had no disallow rules at all, just a pointer to the sitemap itself. Everything that could go wrong on my end, didn't.

It turned out this is a known, mostly cosmetic quirk in Search Console. Sitemap status can lag behind the actual crawl, sometimes showing a stale error for a day or two before quietly resolving itself. Nothing to fix. Just something to wait out.

That was its own small lesson: not every red flag is a real one, and knowing how to tell the difference—checking the actual artifact instead of assuming the worst from a status label—is its own kind of technical literacy.

## Why This Belongs in a Tech Writing Blog

It would be easy to file this whole experience under "web development" and move on. But discoverability is a documentation problem as much as it is a technical one. The best knowledge base article in the world does nothing for the person searching for it if it never surfaces. The same is true of a portfolio, a resume, or a blog.

I've spent twenty years thinking about how to structure content so the right person finds the right answer at the right moment. It turns out that work doesn't stop at the sentence level. It has to extend to whether the content is even reachable in the first place, and that's a lesson I now understand a little more viscerally than I did a month ago.
