---
layout: page
title: "The tech tools I use to make writing easy"
date: 2019-08-02
permalink: /tech-tools-to-make-writing-easy/
---

Writers tend to be interested in the tools that other writers use to stay productive. And, while I could quip about procrastination disguised as information gathering, the truth is that hearing about other writers’ workflows can be insightful.

That’s why I wanted to share my process for writing, and the tools I use to make that process go smoothly. Here’s the list of what I use; for more information either click to link to go straight to each section or keep reading.

- [Drafts 5 to capture ideas when they come to me.](#drafts---ubiquitous-capture)
- [Ulysses to organize my ideas and write without distraction.](#ulysses---distraction-free-writing)
- [Command line tools to edit and publish what I write.](#command-line-tools)
- [An iPad Pro to make the system portable.](#ipad-pro)

## Drafts - ubiquitous capture

Inspiration can strike anywhere. My best ideas seem to come when I’m waiting in line for groceries, taking a walk in the woods, or hanging out with friends. If I want to hold onto those ideas, I need to write them down.

I like to follow a system of ubiquitous capture, which is something I learned from David Allen’s classic productivity book Getting Things Done. Here’s the basic idea:

> “You need to hold all your ideas until you later decide what to do with them.” - David Allen, Getting Things Done

[Drafts 5](https://getdrafts.com/) is an iOS app that does exactly that: it allows you to capture the ideas that you have, without worrying about what to do with them. It’s the digital equivalent of a notebook that you use to jot down everything. And, although it seems incredibly basic, it’s truly my first stop for text and my most used iPhone app.

The best thing about Drafts is its robust export: after writing whatever it is you want to write, you can send it wherever you’d like. This can range from copying it to a new text message, to appending it to the end of a specific Dropbox text file, to exporting to different iOS apps. 

Here are some uses I’ve found for Drafts:

- Writing longer Reddit comments without worrying that Reddit will accidentally eat them
- Adding to an ongoing list of band names that I keep in a text file on Dropbox (my current favorite is Barback Gremlin)
- Capturing story or article ideas and sending them to Ulysses — more on that below

## Ulysses - distraction-free Writing

I am a distractible person. Sure, I’ll sit down at a keyboard to write, but I may end up wondering which lakes are the deepest, look it up on Wikipedia, realize the deepest one is in Russia, wonder about the sea in Russia that’s shrinking, and spend an hour watching a documentary about environmental disasters. Such is life.

The best solution to the distraction problem is taking a long-haul flight with no onboard wifi and asking the flight attendant to keep bringing coffee for the duration. But that gets pricy.

Luckily, I learned early on that simple writing environments offer the least amount of distraction: as a broody teenager, I wrote [over 100,000 words of terrible Harry Potter fan fiction] in Netscape Composer, which was a basic text editor that came with Netscape Communicator. 

See, Microsoft Word reminded me of school, and I’d spend way more time messing with margins and spacing and fonts than I would actually writing. 

Give me some plain text, and I can just write.
	
[Ulysses](https://ulysses.app/) is a plain text editor that gets out of my way when I need it to. It allows me to write in markdown, which is a plain text way of formatting that can easily be converted to HTML, PDF, ePub, docx, or almost any other format.

When it comes to the hard work of actually writing, the critical part of the processes is getting the words out of your head. In Bird by Bird, Anne Lamott’s charmingly pragmatic book on writing, she encourages us to embrace our first drafts:

> “Almost all good writing begins with terrible first efforts. You need to start somewhere. Start by getting something — anything — down on paper. What I’ve learned to do what I sit down to work on a shitty first draft is to quiet the voices in my head.” - Anne Lamott, Bird by Bird

Ulysses allows me to easily create shitty first drafts, and turn them into slightly-less-shitty final drafts. And, since Ulysses uses plain text and markdown, it’s easy to integrate with my favorite command line tools.

## Command Line Tools

If the zombie apocalypse hits Silicon Valley first, then the startup that you’re trusting with your writing may lose access to their servers and your half-finished book might be trapped within a proprietary format, never to be read again.

Open source command line tools, on the other hand, are more dependable. Even if humanity is reduced to the small cadre of hipster travelers who happened to be in Iceland when the zombie outbreak occurred, we’ll probably always have Linux.

When I work at my computer, I generally live on the command line. In my opinion, the command line offers the most elegant tools for organizing, exporting, and publishing text. Plus, opening the terminal makes me feel like an elite hacker, and I like that.

Here’s a selection of my favorite command line tools for writing. Explaining how to use them is beyond the scope of this article, but I’ve included links to get you started. They should work on any Unix-based system (I switch between Linux and Mac OS, with [Manjaro Linux](https://manjaro.org/) being my main system). Windows users can play along using the Windows Subsystem for Linux.

**Vim for powerful text editing.** Before I wax poetic about [Vim](https://www.vim.org/), I have to admit that it comes with a serious learning curve. In fact, not knowing how to quit Vim has turned into something of a meme (for the record, press esc, then type :q! to quit without saving, or :wq to write and quit).

However, Vim allows me to engage with text shockingly fast. It has been around since the early 90s and is installed practically everywhere. If you learn how to use it via Mac OS X, like I did, you’ll also feel right at home editing config files on a Raspberry Pi or making changes on a remote Linux server. I think everyone should learn how to use it. In fact, [I wrote an entire guide to using it for prose writing](/custom-workspaces-for-writing-and-coding-in-vim/).

**Pandoc for easily converting between file formats.** Remember how I said that markdown is easy to convert to whatever publishing format? [Pandoc](https://pandoc.org/) is the way to do that. Let’s say you have a markdown file that you’d like to convert to EPUB and publish as an ebook: Pandoc will handle the formatting for you. Just want to turn it into a PDF and email it to your mom? Pandoc can do that too.

**Jekyll for blogging from the command line.** Much of the web runs on Wordpress, which is an open source platform that allows non-technical folks to blog. There’s nothing necessarily *wrong* with Wordpress (at least, as long as someone’s thinking about security and issues with plugins). I don’t like it much though.

[Jekyll](https://jekyllrb.com/) is an open source platform for the more technically inclined. It allows me to cut hosting costs and loading times by generating a static site. I can write in markdown, and, since I’m hosting everything on GitHub Pages, I’ve got robust version control. 

Plus, even though JavaScript frameworks like React and Angular are sexy right now, I quite enjoy Ruby on Rails.

The best thing about Jekyll is that I can do everything from the command line. All I need to do is toss a markdown file in the posts folder on my computer. If I want to preview, all I need to do is type `bundle exec jekyll serve` and I’ve got a local version of my website up and running. To publish, it’s as simple as `git push origin master`.

**SSH for doing everything remotely.** These all sound like things I need to do from my actual computer, since that’s where the command line is. But my computer is a desktop, and sometimes I’m not at my desk. Sometimes I’m in bed, or at the park, or grabbing a beer during happy hour. Occasionally, I’m in Oregon, or Spain, or Japan, or just on the ferry headed to San Francisco, and I need to do something on my home computer.

Using [SSH](https://en.wikipedia.org/wiki/Secure_Shell), I can securely operate my home computer from any terminal emulator with internet access. All I need is an open port on my home network and a public key. With SSH and the Termius app, my humble iPad turns into a powerful Linux computer that I can use to get some serious shit done.

## iPad Pro
	
This leads me to my final tool for writing: an iPad Pro.

See, I like to be able to write from anywhere. In grad school, I used to lug my MacBook Pro around to the coffee shops of Chicago, but I often found myself relying on questionable wifi and easily accessible power outlets. More worryingly, the computer lulled me into multitasking and distraction.

The iPad Pro solves these problems. Because I have the wireless version, I never have to worry about finding good wifi. The battery lasts for hours, and I’ve amassed an army of portable chargers that I can use to juice up if I need to. The Smart Keyboard isn’t as comfortable as the massive mechanical keyboard I’ve got at home, but it gets the job done well enough. I particularly love the Apple Pencil, which is just a great for note taking as it is for drawing.

But the most important part? I’ve found a workflow that incorporates my favorite tools without encouraging me to be distracted. I’m able to just sit down and write.

## Conclusion — and next actions for writers

As I mentioned in the beginning, there’s no universal approach that will work for all writers. However, here’s what I recommend if you’re interested in building a workflow similar to mine.

 - **Find a trusted system for capturing ideas.** While I enjoy using an app for my ideas, ubiquitous capture can be as low tech as an analog notebook.
- **Create a distraction-free environment.** Writing takes focus, and it’s good to be proactive about eliminating distractions if you want to get some serious writing done.
- **Incorporate open source tools.** With so many open source tools available, there’s no need to cede control of your words to proprietary file formats. If you’re new to using command line tools, you’ll be surprised at how powerful they can be.
- **Take it with you everywhere.** Inspiration is everywhere. Go outside and find it.
