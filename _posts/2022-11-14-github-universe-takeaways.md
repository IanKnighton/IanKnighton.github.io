---
layout: post
title:  "GitHub Universe 2022 Takeaways"
date:   2022-11-14 11:00:00 -0700
categories: github conferences
---

It's the Monday after GitHub Universe 2022 and now that I'm back from a weekend of (what was supposed to be) soccer, I figured I'd break in this new thing with an overview of my takeaways from GitHub Universe.

## Copilot Isn’t As Scary as It Looks

The idea of an AI being able to do what I do everyday went from being something that I considered as a "gimmick" at best, is pretty close to being a reality through GitHub Copilot. That said, it's not as "doom and gloom" as it may seem at first blush. 

Copilot does some very cool things. It can help write regex and has access to a whole slew of boilerplate code that we've all come up with different hacks for over the years. The difference is that it's able to be contextually aware of what you're doing when it applies those structures. 

A simple example that was demoed was adding a switch statement. I've been working in .Net/c# for years and still have to go lookup the syntax because I can't get it right the first time. Copilot was able to take a comment explaining the parameters of what needed to be done and *boom* add a switch statement. The best part was, it can be in a language the developer isn't super proficient in. 

I think the "Hey GitHub" thing is maybe a long way from being something that I'm interested in, but it seems like a big win for accessibility. 

Ultimately, I think humans will always be needed for the logical bits of how to put things together, but lowering the barrier to entry on projects makes the open source community more available. The more people you have writing software on their own, the more new paths can be forged. 

## Codespaces Doesn’t Click Until You Need It

Along with Copilot, there was a lot of attention given to Codespaces. 

I've been vaguely aware of the product, primarily because I'm one of those people that really wants to be able to work off of an iPad and not need to lug my MacBook Pro everywhere I go. It seemed promising when it was in beta, but I kind of let it slip my mind. Now that it's out and ready for general release, I threw it on the back-burner again to review "sometime when I got home."

At the same time, I couldn't stop thinking about a conversation I had with [Josh Johanning](https://josh-ops.com/) at the "Ask" booth. Primarily, the question I had was about having an asynchronous workflow report back its status to the pull request, but in the process he showed me his website and I was somewhat enamored. Then I learned about GitHub Pages. And then that became a project. And here we are. 

The problem was that Jekyll runs on Ruby, Ruby is kind of a bear and I didn't have it installed anywhere. So I decided to have a race between Codespaces and installing Ruby on my Mac Mini. 

Codepsaces won by an absolute landslide. 

In the time it took for Ruby to install, I was able to standup the Jekyll backend and push it up to GitHub. No configuration or anything, just launched the branch in a codespace, installed Jekyll, and called it a day. 

I have a strong reckon I'm going to be spending a bit of time looking into how I can further leverage Codespaces for things like dev environments and LUA configurations when dealing with Terraform. 

## GitHub Uses GitHub to GitHub

They eat their own dog food and they're very willing to share how they do it and what comes with it. There were separate talks on how GitHub uses GitHub to build GitHub and how GitHub uses GitHub to secure GitHub. As someone who is a self proclaimed "Everything as Code Evangelist", I absolutely loved seeing an implementation of IAM through code, pull requests, and CI/CD. It really shows the power of what can be done if you drive everything through source control. 

I'm sure you'll also be surprised to know that they use Codespaces and Copilot as well and showed practical examples of how those work as well. 

It's truly fascinating to see a company as big as GitHub discuss what they do and don't do on their own. It's even more impressive when you see how much of what they're selling to you is something they have to live with every day. I think that's an inherent joy of building a "tool" and less an "application." Unless you're building an application that your engineering teams can use every day, it's really hard for them to give an honest test when they're using it. GitHub lives in that lovely space where they are both building and using what they build and thus feel every pain point an end user might. 

---

That's a first pass at it. I'm *patiently* waiting for the videos to be uploaded and available from the conference so I can watch the sessions I missed and have a second look at the sessions I was too overloaded to grock everything. 

I guess I should also figure out how to make this whole webpage thing work as well. 