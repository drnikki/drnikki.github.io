---
layout: post
title: "Use Zotero to generate an annotated bibliography"
date: 2018-01-04 10:14
comments: true
published: true
---
<i>(this was <a href="https://www.hastac.org/blogs/nikkistevens/2018/01/04/generate-annotated-bibliography-zotero">originally posted</a> on the HASTAC website as part of my HASTAC 17-19 Scholars participation.)</i>


<p>I started a PhD program this semester, and I vowed not to repeat some of the mistakes of my master's thesis. I mean, I made <em>many</em> mistakes, but two are relevant here:</p>

<ol>
	<li><em>I did not do a good job of tracking what I read</em>. This meant that I when I would try to find Smart Thing&nbsp;so that I could use it, and I couldn't remember where I'd read it. I spent a lot of time retracing my steps from source A to source B to find things.</li>
	<li><em>I did not do a good job of taking notes on what I read.</em> This meant that when I finally found that Smart Thing that Scholar had said, I couldn't remember how I wanted to use it or what place I'd found for it in my work.&nbsp;</li>
</ol>

<p>So to avoid mistake #1, I'm using&nbsp;Zotero to store items, generate bibliographies, and to insert citations into documents (all the standard stuff ). I followed fairly closely an updated version of the Zotero + Zotfile + Zotpad workflow described <a href="https://www.hastac.org/blogs/craigeley/2013/02/25/ipad-workflow-zotero-zotfile-zotpad">here</a>. I can say that I am doing a good job of keeping track of <em>everything</em>&nbsp;that I've been reading and Zotero makes it simple for me to do a full-text search of my entire library to relocate a specific Smart Thing that I read once.</p>

<p>When I started taking notes on things that I was reading (to avoid mistake #2), I stored those notes along with the item itself in Zotero. Sometimes they were just notes, but most often I would write up a formal, public-facing annotation that I could share with other students or professors. I assumed (incorrectly) that since Zotero is powered by an SQL database, surely there would be an easy way for me to generate an annotated bibliography with my own annotations instead of the items' abstracts.</p>

<p>I couldn't find an easy way; so, <a href="https://github.com/drnikki/zotero-util/blob/master/annotated-biblio.md">I wrote one</a>. <a href="https://github.com/drnikki/zotero-util/blob/master/annotated-biblio.py">This script</a>&nbsp;will go through your entire Zotero account&nbsp;and search for items&nbsp;that match a certain criteria.&nbsp; It will then go and get any annotations for that item (and it knows how to distinguish a formal "annotation" note from just a "i hope no one sees this private jumbling of thoughts" note).&nbsp; It will then print out the citation (in whatever format you wish) and then the annotation.&nbsp; And magic!&nbsp; An annotated bibliography&nbsp;that's perfect for comps or for when someone just casually asks you to send them all your notes on a topic.</p>

<p>What's not magic is that in order to use this script, you'll need to be comfortable editing a Python file&nbsp;and running it in your terminal. I wish I had a more universally accessible offering, but I'm hopeful that by sharing this, folks will contribute to it and that over time it will become something that can be used by the majority of people who, let's face it, <em>do not</em> want to run Python just to generate a bibliography.</p>

<p>Take a look at <a href="https://github.com/drnikki/zotero-util/blob/master/annotated-biblio.py">the script</a> itself and then <a href="https://github.com/drnikki/zotero-util/blob/master/annotated-biblio.md">read these instructions</a> to get started.&nbsp;If you have any suggestions for improvement (there are still a few bugs, too) feel free to comment here or&nbsp;open an issue&nbsp;on&nbsp;GitHub&nbsp;if you feel comfortable doing so.&nbsp;</p>
