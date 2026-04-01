# AI Jam - Session 2: Git and GitHub
**Date:** March 31, 2026
**Duration:** 59 minutes
**Instructor:** Ryan Herubin (Git/GitHub concepts), Maroun Najjar (host)

---

## Transcript

@0:00 - Akshay Verma
Almond's coming in. I'm excited to dig in. Yeah, please stress test it all for me, because I've been looking at this for weeks, so it's helpful to get a fresh pair of eyes on it.

@0:11 - Lizzie Belgum (Change.org)
Absolutely.

ACTION ITEM: Make Maroun Fathom admin; Maroun download recording - WATCH

@0:23 - Maroun Najjar
Hello. Welcome, y'all. Workshop number two, Git and GitHub. Okay, I pressed the Fathom button for the first time, and I don't see my Fathom person.

But I see yours, Lizzie, so maybe you can make me admin or whatever on the meeting after, and I can download it all.

@0:49 - Lizzie Belgum (Change.org)
Yep, happy to.

@0:51 - Maroun Najjar
Great. Alrighty, y so I will see if we have some other folks joining really quick. See who else. else.

At RSVP. Cool. All righty. Why don't I intro what we're going to do today? And then if folks want to join, they can.

We've got special guest Professor Ryan joining us, which is super exciting to teach us the foundational concepts of Git and how we work with Git and GitHub.

Before we jump into this, that part of the class, what I was thinking we could do is we all sort of had some homework after the first class.

I'd love if folks who have like spent a little bit more time would want to demo what they've put together.

And so as a reminder, the homework was to essentially keep polishing something, keep polishing the project you had put together in the first class, try different ways of polish.

Right. And I walked through like some of the different techniques that, that I go through. But. But, yeah, I'm thinking maybe we start with, like, three-minute demos to talk through, yeah, the homework piece and the polish that's been done.

Welcome, Steve. Also, welcome, Akshay. This class will build on the last one, so I don't know if y'all had a chance to go through that content.

If not, the interactive workshop piece will be a little bit harder to do, but Ryan's presentation will still be useful in terms of, like, getting the core concepts across.

Okay, let's do, why don't we do our demos? Lizzie, Katie, Janice, Rafa, yeah, do y'all have something you want to show or talk through?

@2:43 - Lizzie Belgum (Change.org)
The site that I was polishing was the Persona site, which I got to show at the All Hands this morning, so I can cede my time to someone else, because you all have seen that.

@2:56 - Maroun Najjar
Cool. I still, yeah, let's see if anyone else wants to go. But it would still be useful if you'd want to talk through, like, did you use agitation?

Like, what were your loops to do the polishing, right, and what kind of methods you used? But yeah, does anyone else have something they'd like to demo just around the homework from last time?

@3:16 - Samara Tager
I can share.

@3:19 - Maroun Najjar
Awesome. Go for it.

@3:21 - Samara Tager
I can share. So we're just, like, giving a quick overview and how we built it.

@3:26 - Maroun Najjar
Yeah, so, yeah, and so I'll set a three-minute timer, but the prompt is our homework was to keep polishing the thing we made last time, or to keep polishing something.

So if you can talk us through, how did you polish? How did you iterate? What did you do? Yeah.

SCREEN SHARING: Samara started screen sharing - WATCH

@3:44 - Samara Tager
Okay, cool. One second. Can you guys see my screen?

@3:52 - Lizzie Belgum (Change.org)
Yes.

@3:53 - Maroun Najjar
Yes.

@3:54 - Samara Tager
Yep. Okay, so this is, as you guys know from my Slack messages, the global rollout tracker. correct. hope I'm managing the rollout of our starter dashboard in 17 markets, I think there's one extra market there, 16 or 17 markets, and there's just so many inputs that we have going on, we had like QA, which had all these Google Sheets, we have JIRA tickets, we have data in Amplitude, stuff happening in Slack, and I wanted a place to just like bring it all together and be able to sleep.

See like at a high level, everything that's going on, and I wanted it to happen automatically, so I didn't want to have to keep like prompting and inputting the spreadsheets every time I wanted Claude to remember the inputs that I had given it and been able to make updates to the site on a regular basis.

So right now I have this connected to several Google Sheets, a Slack channel. Amplitude, and JIRA so that they could see all the tickets and the statuses of everything that's going on there.

You can see there's QA bugs. This is coming from the spreadsheet. You can also see if there's linked bug tickets here.

You're able to dive deeper. So for instance, this is Australia and I had Claude basically build me like a detail page.

So essentially, the V1 was just this kind of dashboard view where you can see all the different phases and countries.

You can see what stage that they're in of development. And I wanted a little bit of a deeper dive so that we can have things like these linked bug tickets if we have JIRA tickets that are attached to a specific country.

And I also had it bring in Amplitude and summarize it for me. So it's able to go to Amplitude, look at all the charts, and then give me...

Me this high-level summary so I can see at a glance what's going on without having to dig into the data myself, which is also really helpful, like how are we doing in these different countries?

I think Canada is doing pretty well, so I'll show you guys that one. Everything is pretty much green or flat here.

But yeah, this is all something that I had to kind of prompt it. So there was a lot of visual bugs.

I used agentation for that to clean up things. There's like, you know, implementation, for instance, here is split to two lines.

I could probably still continue to clean up little things like that. But when it came to actually building additional pages, there was just a lot of prompting that was like, hey, I'm looking for a different view.

I'd like an entry point on each of the cards. And then here's kind of how I want that view to be laid out.

@6:52 - Maroun Najjar
Amazing. Awesome. Thank you so much for showing. This is so, this is so cool. Such a use case I didn't consider.

Thanks, Great. So it's, yeah, it's awesome that you made this.

@7:03 - Samara Tager
Thanks, guys.

@7:06 - Maroun Najjar
Ooh, do you want, would you want to talk through Brian's question? It's a great, it's great question.

@7:14 - Ryan Herubin
Here, Samara, I'll just, you know, have to read it. So I get how you, the Amplitude section, like your, the Amplitude is the data backing for that information.

So like, how did you connect JIRA and all those things for like ticketing? So like, if a bug ticket happened around Canada or Germany or France or whatever, like how did you organize, how did you prompt to organize that data around?

@7:37 - Samara Tager
Yeah, that's a good question. I had, there was like a key, an API key that I had to generate.

And then I had Claude basically look at the Epic. So our Epic is everything that's related to the global rollout.

And then I had it specifically look at the QA tickets. So I have like a ticket that's like parentheses QA, and then it's every market.

we're CPC. CSO. So I had to just look at those QA tickets, look at any comments or conversation that was happening there, and then basically any linked bug tickets, which is how our QA lead has been kind of tracking necessary changes.

So yeah, I basically just had Claude walk me through how to set everything up. And at first I thought it was all dynamic and it turns out it wasn't.

And when you start a new session, it doesn't remember anything from the last session. I'm like, can't you find these links?

@8:32 - Ryan Herubin
I already gave them all to you. So yeah. point. That's a very good engineering pain point that you just really lived right there.

@8:39 - Samara Tager
Yes. I was like, wait, are you kidding me? How is this not saved anywhere? But yeah, I basically redid it again and said like, no, I actually need this to be live.

I need you to update it, check once an hour and then update the live site immediately. So yeah, apparently that's all running in.

in the background and actually doesn't need terminal open, but there are some processes that do need terminal open to be able to complete, even if you're not prompting it.

@9:10 - Ryan Herubin
Yeah. Okay, cool. So like, so it's, instead of being off of like a metadata on a Jira ticket, it's all around like how the title of the ticket was formed or created and is entered in Jira.

That's how it kind of can pull that those, like the QA ones, parentheses QA, that's how you're told the prompting how to pull that out.

@9:29 - Samara Tager
Okay. Yeah. It said like, are there any naming conventions? Like how do I know which tickets? And I just said, I had already named them that way.

So anyone that is able to have that.

@9:40 - Maroun Najjar
Awesome. Thank you so much. I do want to move us to another demo just so we can then transition to class content.

@9:46 - Katelyn Burgin
Katie, did you have, were you going to show something different or do you have a question? Yeah, I have a question so we can do that.

@9:52 - Maroun Najjar
Would you mind putting it in the zoom chat and then we'll, we'll look at, at something else. Awesome. From everybody else.

Yeah. Look at that. Thank Corinne, Rafa, Janice, Lizzie, anyone else who's, like, made something and iterated on something?

@10:05 - raphaelsocrates
Yeah. I have a quick thing.

@10:09 - Maroun Najjar
Go for it.

SCREEN SHARING: Raphaelsocrates started screen sharing - WATCH

@10:13 - raphaelsocrates
Cool. That's actually was my first test using, like, FigumenCB at all. Like, it was, like, a two, one week ago or something.

It was really kind of, like, trying to, you know, we have an issue today that's, like, people always ask to access our assets.

And it's hard to find. And it was just, like, oh, maybe instead of, like, a presentation or something, we can just, like, put something in one page.

And the way they were created was, like, using the visual explainer. A lot of iterating with, you know, using also the agentation here.

I think, like, mostly my struggles were, like, at first, getting variables from Figma. Don't You're That's on camera. All those things, but it was really kind of like, and also like another struggle was like using the using figment to illustrate things and then, oh, actually using the cloud to illustrate things or like getting a little iterated, a lot of those things and I know we talk about like the quiver AI, there's the new one that I kind of, you know, can create vector with this.

It's something that we can test afterwards. Even for icons, I start testing for icons as well. That might be interesting.

Um, yeah, just like putting, kind of like importing everything pixel perfect from figment and kind of like already like applying and, and doing all those things and even like call it something that people really struggle like for out from the design team is like what colors we use and all those things.

Like you can just like, you copy the color. You paste somewhere and all those things. a little, you know, fixing things is still a little, the behavior is not exactly what I want, but like usually what I really do is just like use the agitation here.

It's very easy. And yeah, that's it. It's just a quick demo with, it might be something that we might use in the future.

@12:30 - Ryan Herubin
I guess the use case of this would just be like showcase what's in Figma, but not needing Figma.

@12:37 - raphaelsocrates
This specific one is just like a, we have a lot of people around the company that is really kind of like working mark-ons and all those things.

And like they, they are looking for the late latest like guidelines for things that we are using either the logo, the colors and everything.

Uh, even like design, design team that we are closer to this. guess. But, like, you know, just making it a way that is easy for everyone to access to it.

And also, like, to be synced to the last, like, color palette and all those things. We don't have to keep, like, to be keeping updating those things.

@13:15 - Maroun Najjar
Awesome. Amazing. Thank you so much, Rafa. I'm going to move us to our core class for today, just to make sure we've got plenty of time.

Before we jump into it, I just want to preview for you what we're doing today and the next class.

Because they sort of go together, and I just want you to see, like, how we're going to build on what Ryan's going to teach us.

So, what Ryan's going to go through today is what Git and GitHub is. And so, the way you can think about it is that's, Git is how we collaborate on work.

And it is how we iterate on a product surface. And it's, like, the foundation for doing that. And so, today, we're going to go through the core concepts.

What I'm hoping we'll do, this is going to be a little, like, live workshop-y, but what I'm hoping... The we'll do is I have an old, slightly bastardized version of our petition page.

What I want to do is for everybody to pull that repo down onto their computers and then we'll go around the room and assign different parts of it for different people to fix and iterate on.

And then we will all push it back to the same place. I don't know if we'll get there today, but that's our goal.

That's what this first class is about. I just want to preview the next one because you'll sort of see why this is important.

This is important because one, when you work with engineers, this is the process we will be going through, right?

But then the second thing that we'll do in the next class is we're going to look at something called a work tree.

And a work tree is essentially a way for you, Ryan will explain this in more detail in the future, but I just want to preview this bit.

It's a way for you to spin up multiple agents and allow each to iterate on the same thing in just like a different parallel universe, and then to come back and pick the result that you like.

That's one of the use cases. And so that's sort of what we're heading towards. And next It is a world where you don't just have your one terminal window, but you're able to, like, have multiple of these things sort of working together.

Anyways, that'll be for next class. I just want you to see, like, where the road that we are walking down over these next two classes.

Okay, I'm to pass it to you, Ryan, to kick us off.

SCREEN SHARING: Ryan started screen sharing - WATCH

@15:19 - Ryan Herubin
Awesome. All right. So one thing that Maroun and I also talked about was that this is new for us.

So you guys are the first class around this. So there might be some bumps and rockiness along the way, but that's okay.

We're going to get to it together and we'll constantly make this content good for general use. So you guys are the first one.

So just let's celebrate that. And this isn't going to be perfect, but that's going to be okay. So GitHub and Git.

So the first thing is that we need to talk about commits, branches, what pushes and pulls. And what pull requests are.

So those are the big four sections we're going to unlock today to hopefully get clarity around. And, spoiler alert, there's this website that I created because I am not a deck creator, as Lizzie and Jen can tell you, so I've used AI to generate this.

So, just be kind for my graphic choice, Lizzie. Because I didn't do it, Claude did it.

@16:33 - Lizzie Belgum (Change.org)
It looks great, Ryan.

@16:35 - Ryan Herubin
So, everybody, the first thing you need to get up and install, get on your Macs. So, who, Maroon, should everybody have this installed or do we need to go through this?

@16:48 - Maroun Najjar
I think we should have everyone go through it now and like pause on the slide, yeah.

@16:52 - Ryan Herubin
All right. So, everybody, open up the terminal. A way to do that is open up Spotlight with the command space keyboard shortcuts.

@16:59 - Steve Dziedzic
Or cuts. And just type terminal and hit enter. And is this what I tried to do an hour ago and was unsuccessful because it requires site platform?

@17:09 - Ryan Herubin
It also requires a GitHub account. So if Chris hasn't set up a GitHub account for you, this is going to be less beneficial for you, but you can still listen.

You can do it yourself, right?

@17:20 - Steve Dziedzic
Well, so I got a Git account and then I went to terminal and then I tried to like import the Corgi Git files and it said like, okay, now log in to Git.

@17:31 - Ryan Herubin
If it asks you to log in, you have in Git installed.

@17:34 - Steve Dziedzic
And then I tried and I didn't pass the Chris Campbell test and so now site platform has to give me the credentials.

So if anybody else runs into a similar issue, know that site platform has to get involved.

@17:49 - Maroun Najjar
Yeah, I still, so for today's class, the repo we're going to work out of, I know this is recorded, but is in my personal GitHub.

So, and I'm just going to. Add you all to it, and we will delete all this stuff after this class, so it's not insecure.

But so I still think it's worth doing, even if we haven't all been added to the official change.org organization quite yet.

@18:14 - Ryan Herubin
So the first thing, so does everybody try to run this Xcode selects with the spaces and the hyphens in your terminal command, and if anybody has problems, please raise your hand or just shout it out, and we can live fix anything you guys might be seeing.

@18:39 - Samara Tager
We open terminal, we just put the command in. We don't have to do, like, CD, Corgi, or Claude.

@18:46 - Ryan Herubin
Correct.

@18:55 - Lizzie Belgum (Change.org)
And this is a one-time thing, right?

@18:58 - Ryan Herubin
You and Jen have already done.

@18:59 - Lizzie Belgum (Change.org)
You're good.

@19:00 - Ryan Herubin
It should say done. It should give you some message saying it's already done.

@19:07 - Jennifer Garfield
I should still brew install git, right? No?

@19:11 - Ryan Herubin
You should already have that, but yeah, go try it, Jen.

@19:14 - Steve Dziedzic
Well, Jen, if you do the git-version and it has a version for you, then you should be.

@19:21 - Ryan Herubin
Jen, look at the bottom and that'll be your sign that you're good to go.

@19:26 - Maroun Najjar
And for someone who's doing it, we can have multiple people screen sharing at once. Would you mind screen sharing?

This was helpful last time because as one person hit roadblocks, we could all talk through it. So yeah, someone who hasn't done this before.

@19:41 - Akshay Verma
For a quick question, will none of this apply to me if I don't have the git account and everything from last session?

@19:50 - Maroun Najjar
and the key key don't know yet. But you can go through, like, the first-class content. I've got just, like, a checklist of how to go through it and then come back to this, yeah.

@20:07 - Akshay Verma
Great.

@20:11 - Maroun Najjar
Awesome. How are we doing?

@20:15 - Ryan Herubin
Katie, Rohan, Janice, yeah. Corinne's got the version.

@20:25 - Maroun Najjar
And then what I will ask you to do, just if you've done this, in our Slack channel, our AI Builders curriculum, I posted a command.

Here, I will give you the message. Click on this. I would love for you to run that, and what that's going to give you is your GitHub username.

And if you could, if you could just, like, thread response to this message in Slack and tell me what your username is, this way I can invite you to my private repo.

@20:54 - Ryan Herubin
Yeah. And Steve, this might prompt you to create your account.

@20:58 - Maroun Najjar
Mm-hmm.

@21:08 - Katelyn Burgin
Okay, so I put what you put in Slack into my terminal and it says command not found.

@21:17 - Maroun Najjar
Which one? Screen sharing?

@21:20 - Katelyn Burgin
Yes.

@21:21 - Samara Tager
We do need a space between select and install.

@21:31 - Katelyn Burgin
No, this is the exclamation GH API user.

@21:35 - Samara Tager
That one.

@21:36 - Lizzie Belgum (Change.org)
Okay. For me, Katie, command not found.

@21:40 - Katelyn Burgin
Okay, let's share this.

@21:43 - Steve Dziedzic
Command not found.

SCREEN SHARING: Katelyn started screen sharing - WATCH

@21:45 - Katelyn Burgin
This is what I got.

@21:52 - Ryan Herubin
I don't know how to look at other person's screen when I'm sharing also.

SCREEN SHARING: Lizzie started screen sharing - WATCH

@21:57 - Maroun Najjar
In the top, there are different tabs.

@21:59 - Ryan Herubin
are tabs can Abbasayee a a is it, it's No, but what I'm sharing, I can't see that.

@22:03 - Maroun Najjar
Oh, gotcha. For, I guess, Katie and Lizzie, let's try this. Could we all summon ClaudeCode and then say, ask it what your GitHub username is?

Or if it knows, and we can see what it does.

@22:20 - Samara Tager
In general, should we need Claude summoned for this? Or we just open terminal and put in that string?

@22:27 - Maroun Najjar
Not, not yet. You, the string worked for me, but maybe it's, there's like a personalized command or something.

@22:35 - Katelyn Burgin
That should be in ClaudeCode, ClaudeTerminal that we ask it, what our GitHub name is, right?

@22:41 - Maroun Najjar
Yeah. Yeah. So where you are, you would just type in Claude to start ClaudeCode. All right, I'm following Lizzie's screen.

It seems like it's giving you the same command.

@23:27 - Lizzie Belgum (Change.org)
Yeah. So it would want me to run that command in normal terminal, not clad.

@23:35 - Maroun Najjar
Yeah.

@23:37 - Samara Tager
What's supposed to happen when you type it in?

@23:39 - Ryan Herubin
Is it just like... You don't need that first exclamation point. You just need gh. That's the problem. that's gonna be I finally was able to give it my screen.

@23:48 - Maroun Najjar
Thank you, Ryan.

@23:50 - Ryan Herubin
So there you go. Sorry to nuke in there, but that's the problem. But what does a success date look like?

SCREEN SHARING: Maroun started screen sharing - WATCH

@23:57 - Maroun Najjar
Wait, I'll show you. It... So if you, sorry, I have a couple windows open, but down here, it'll give you your username.

@24:06 - Jennifer Garfield
yeah.

@24:07 - Maroun Najjar
Okay. Yeah.

@24:08 - Samara Tager
So that's what I need. us, yeah.

@24:10 - Maroun Najjar
I love this. That's made from Terminal.

@24:13 - Samara Tager
So you just open Terminal and put in the, start a new one. Wait, Jen, did you do it?

@24:20 - Jennifer Garfield
Yeah. I got my username, but I was just confirming that was a 16.

@24:24 - Ryan Herubin
Oh. Oh, Jen did use the.

@24:27 - Samara Tager
Got it.

@24:28 - Jennifer Garfield
Sorry, I can share my screen.

@24:30 - Lizzie Belgum (Change.org)
Jen, look at mine and tell me what I'm doing wrong.

SCREEN SHARING: Jennifer started screen sharing - WATCH

@24:35 - Jennifer Garfield
Oh, yeah. Sorry, I just started sharing. Because did you, can you see mine?

@24:39 - Lizzie Belgum (Change.org)
Is that helping? Oh, no, because I'm sharing, so I can't see yours.

@24:42 - Ryan Herubin
I'll stop. I can show you guys how how to fix that in the past, because I just learned how to do it.

But actually, Lizzie, Jen did put the exclamation point in front of hers, and it worked. And So that was news to me.

Because GH is actually the command, so I don't know what the bang did before that. Or if you just know your GitHub username, if you have one, like you can log Yours is lbegum, I mean, Lizzie, yours is lbegum hyphen jaynor.

@25:07 - Lizzie Belgum (Change.org)
I know yours, I've done so I know mine, but I just wanted to be able to do it. And even doing it with the exclamation mark, it did not work on my end.

@25:16 - Jennifer Garfield
Wait, Lizzie, share yours again?

@25:18 - Lizzie Belgum (Change.org)
Okay.

@25:19 - Maroun Najjar
So I think, I wonder, Ryan, if we should have done the last command you have on your website. Like, I wonder if actually we don't have GitHub in the CLI for some folks.

And that's just what we need to link?

@25:32 - Ryan Herubin
Yes, that is correct.

@25:34 - Maroun Najjar
Cool.

@25:34 - Ryan Herubin
That's good. That's good notes for the future.

@25:37 - Maroun Najjar
Cool.

@25:38 - Ryan Herubin
Future one of these.

@25:38 - Maroun Najjar
Should we, how do we get that set up for folks who don't have it? Like, I see Corinne too, and Janice, I think almost everybody, we should probably set up GitHub.

@25:53 - Ryan Herubin
Oh boy, I haven't done this in forever. It came on my laptop. So, Engineers have different setups, so it came with all that, so I just logged in, so I honestly, I haven't done this in a very long time, and so you don't do something.

@26:10 - Steve Dziedzic
It's been 20 years.

@26:16 - Ryan Herubin
Don't take me, Steve!

@26:18 - Maroun Najjar
I have an idea. Okay, so CLI, I'll use the question you prompted Corinne to talk about what we're trying to do and then give us an idea for, or an option for how to do it.

CLI is, Ryan, feel free to correct what I'm about to say, it stands for Command Line Interface, and it is basically a tool that Cloud Code and that your terminal can use to access other services.

So what we're trying to do now is instead of, is basically install GitHub for your terminal and for Cloud Code, and that's what the GitHub CLI does.

And so, yeah, I think we should do the command that Ryan just posted. what do I get? So So let's

Just type that into your terminal and let's see what we get. The other thing I was going to say is let's ask CloudCode to install the GitHub CLI for us.

But this is a good place to start, so if someone could Boiler alert, Maroon. That's exactly what I asked.

@27:14 - Ryan Herubin
I opened up CloudCLI, I was like, what do I do? Because I was like, instead of me hunting and pecking around, I was just like, let me just tell me what to do.

That's what it gave me.

@27:23 - Jennifer Garfield
brew makes me laugh so much. Well, actually, Lizzie's doesn't have it, but mine has all these beer emojis.

@27:29 - Maroun Najjar
It's like the bro-iest software.

@27:33 - Ryan Herubin
Yeah.

@27:35 - Jennifer Garfield
Ryan gets to hear all my commentary.

@27:37 - Ryan Herubin
It's fantastic. It's fantastic.

@27:41 - Maroun Najjar
Cool. So are we, yeah, are other folks also running the brew install GH process?

@27:46 - Steve Dziedzic
You should be getting something like what Lizzie...

@27:48 - Jennifer Garfield
But Ryan, I don't need to, right? Because I already have it.

SCREEN SHARING: Corinne started screen sharing - WATCH

@27:52 - Ryan Herubin
Correct. Yeah, if you're able to do the GH API user blah, blah, blah.

@27:58 - Samara Tager
command from earlier, you're fine. Okay. It'll say, like, already installed and up-to-date if you try and do it.

@28:07 - Ryan Herubin
Corinne, what are you doing?

@28:09 - Lizzie Belgum (Change.org)
I'm curious why it let me do it again, Ryan. Maybe that was a step I missed last time and haven't needed it or something.

@28:17 - Ryan Herubin
Yes. I don't know. I know you use GitHub Desktop for all of your GitHub interactions. That's why.

@28:29 - Lizzie Belgum (Change.org)
Oh, that's true.

@28:30 - Ryan Herubin
Remember, like, we never could ask Claude to do any of your GitHub commands because it would fail, and that's why.

@28:35 - Lizzie Belgum (Change.org)
Maybe it will work now.

@28:36 - Ryan Herubin
This will unlock that. Yes.

@28:40 - Maroun Najjar
This is great. So, Corinne, it looks like, and Lizzie, looks like the install was successful. I'm assuming there's probably some authentication you have to do, and I think the command is g, Brian, let me know if this sounds right, but I think it's gh off.

that's true.

@28:59 - Ryan Herubin
Um, yes. Then you have to type it over and over so no feedback.

@29:04 - Jennifer Garfield
You'll be like, do I type?

@29:06 - Corinne Sherry (she/her) - Design
Did it work? Sorry, it ghspat?

@29:10 - Maroun Najjar
Space off?

@29:11 - Corinne Sherry (she/her) - Design
Space login?

@29:12 - Ryan Herubin
I just put it in the chat, um, in lowercase.

@29:21 - Katelyn Burgin
So it told me that GitHub was installed, and I didn't get that. Oh, Siri, stop.

@29:29 - Maroun Najjar
Siri, stop.

@29:35 - Katelyn Burgin
I'm interrupting. Uh, but then when I put that in as well, still is saying command not found, I feel like.

@29:42 - Steve Dziedzic
Katelyn, were you starting from the, uh, terminal clod code or just terminal?

@29:48 - Katelyn Burgin
Oh, just terminal.

@29:49 - Steve Dziedzic
Terminal clod code? Terminal clod code has been very helpful very quickly. I, uh, I, could not do it without Clawed in the terminal.

@30:01 - Samara Tager
I'm an authorize your device.

@30:04 - Maroun Najjar
Yeah. So, Brian's answering as we go, but you'll be asked, where do you use github, do github.com?

@30:14 - Jennifer Garfield
What do you say, github.com?

@30:16 - Ryan Herubin
Lizzie, do github.com, you're on other right now, so go up and press github.com. Even though I use it also at desktop?

@30:27 - Maroun Najjar
Yeah.

@30:28 - Ryan Herubin
Yes.

@30:29 - Jennifer Garfield
So I say other?

@30:31 - Ryan Herubin
No, you say github.com, Jen.

@30:34 - Jennifer Garfield
How do you say that?

SCREEN SHARING: Janice started screen sharing - WATCH

@30:36 - Ryan Herubin
Just press enter. See, the caret is selecting github.com, how it's like a little blue color or gray color?

@30:42 - Jennifer Garfield
has this other tooltip over it, so I can't really see.

@30:47 - Ryan Herubin
Yeah, HTTPS.

@30:49 - Jennifer Garfield
Just enter?

@30:50 - Ryan Herubin
Yeah, log in with the browser, Corinne. Yeah, I'm bouncing between everybody's screen sharing, so.

@30:57 - Maroun Najjar
Yeah, this is super useful to be able to move. Yeah. Yeah, in with the web browser, just press enter.

@31:04 - Ryan Herubin
Remember, mouse is not a tool in CLI.

@31:08 - Lizzie Belgum (Change.org)
I see a lot of people hovering their mouse over things. I just wanted to call that out. Hovering our mic.

Okay, Ryan taught me if you do option and then arrows, it goes faster. So it's really annoying when you just go like arrow, arrow, arrow, arrow.

But if you go option, arrow, it jumps by every word.

@31:26 - Steve Dziedzic
No way.

@31:28 - Maroun Najjar
Oh, wow.

@31:29 - Ryan Herubin
That's incredible.

@31:31 - Maroun Najjar
You're welcome.

@31:33 - Ryan Herubin
The important things of the class that we're all learning.

@31:38 - Steve Dziedzic
Janice, did Claude give you the one-time code in Terminal?

@31:44 - Ryan Herubin
No, it doesn't do it in Terminal.

@31:46 - Janice Pang
does it in...

@31:47 - Ryan Herubin
Do you have the 2FA and 1Password?

@31:49 - Jennifer Garfield
I just got it in Terminal.

@31:51 - Steve Dziedzic
Oh, Wait, Janice, what'd you say?

@31:53 - Janice Pang
Oh, you did, did get a one-time code, which was before this screen, and then this screen is another confirm action.

@32:00 - Steve Dziedzic
That's good. Oh, bummer.

@32:02 - Samara Tager
need to confirm via email as well, I think.

@32:05 - Ryan Herubin
Yes, correct.

@32:06 - Janice Pang
Okay.

@32:06 - Ryan Herubin
Either it being one password or email, whatever you have it set up as for your GitHub account. So, Jennifer, Jen, are you good?

Yeah. Okay. So, LLC is your terminal?

@32:20 - Corinne Sherry (she/her) - Design
I had to use, like, Google authentication just to log in to Git, but that's not the auth token that I give to Terminal, right?

@32:28 - Ryan Herubin
No.

@32:30 - Corinne Sherry (she/her) - Design
So, where in the website on GitHub.com do I find the auth token that we need for Terminal?

@32:39 - Steve Dziedzic
So, what happened to me was Claude said, open up GitHub.com slash login slash device, and then copy in a one-time code that Claude gave me, and then authorize the app, and then all of a sudden Claude said, GitHub is connected, you are logged in.

@32:56 - Jennifer Garfield
Wait, are you in Claude code?

@32:58 - Steve Dziedzic
Yeah.

@32:59 - Jennifer Garfield
Mm-hmm. I'll Okay.

@33:00 - Corinne Sherry (she/her) - Design
I see. Okay. I thought I was going the opposite direction.

@33:06 - Ryan Herubin
That works. Thank you.

@33:08 - Steve Dziedzic
Nice.

@33:12 - Ryan Herubin
Learning how to interpret what CLI is telling you is a skill in and of itself.

@33:18 - Maroun Najjar
Yeah.

@33:19 - Ryan Herubin
This is the antithesis of a UI. It's a command line interface. It's different. It's okay to be tripped up in these early days.

@33:33 - Maroun Najjar
So we've got about 25 minutes left. What I think I'd love to do is swap back over to the slides and do like the next little bit so we can get those concepts in.

Before we do that, can we just quickly go around the horn just to see where everybody is just so I know where we're leaving off?

Yeah, I'm just going to call people and let me know if you've been authenticated or just like where you're at.

Lizzie, where are you at?

@33:58 - Lizzie Belgum (Change.org)
at? Lizzie, Lizzie, Lizzie, I'm stuck where it says enter the one-time code, go to GitHub in the browser, and I went to GitHub in the browser, but I'm already logged in, because I've been using it and stuff, so I don't know where to put the one-time code, because I'm already logged in.

@34:17 - Ryan Herubin
It's the URL's in your terminal, or it should be hdpsgithub.com slash login slash device in your browser.

@34:24 - Lizzie Belgum (Change.org)
so I put that in. Okay, it's not going- And takes me to, like, a logged-in state. Yeah, exactly.

@34:32 - Ryan Herubin
Okay.

@34:33 - Lizzie Belgum (Change.org)
It's just redirecting me to github.com.

@34:36 - Steve Dziedzic
Could you log out?

@34:39 - Jennifer Garfield
Sure. That's weird, Lizzie, because mine, by the end of this, was like, you were already logged in, but it didn't care.

@34:46 - Steve Dziedzic
It still let me go through all the steps.

@34:50 - Lizzie Belgum (Change.org)
Okay, I logged out and logged back in, and now it's asking for a code. Yeah. Authorize.

@34:55 - Maroun Najjar
Nice. Okay, amazing. I'm going to go just on My screen, Katie, Rafa, where are y'all at?

@35:04 - Katelyn Burgin
Oh, I'm sorry, I might have gotten a little bit lost on the end objective, and I think I'm there, but maybe not.

@35:10 - Maroun Najjar
I have my username, and I'm logged in to GitHub in the cloud terminal. That's it. That's great. Okay.

@35:16 - Katelyn Burgin
Yes.

@35:17 - Maroun Najjar
Thank you.

@35:18 - raphaelsocrates
Rafa, what about you? I just have an issue with two-factor authentication here, just trying to figure it out.

@35:25 - Maroun Najjar
Okay, cool. I'm going to go down. Akshay, have you been following us? Okay, cool.

@35:31 - Akshay Verma
I requested access, I'll catch up later.

@35:34 - Ryan Herubin
Cool, yeah.

@35:35 - Maroun Najjar
Janice, what about you?

@35:38 - Janice Pang
I am still on this confirm access screen. Let's see.

@35:46 - Ryan Herubin
Probably use your password, so you're having problems, so use your password.

@35:51 - Janice Pang
Ooh, okay.

@35:54 - Maroun Najjar
Awesome. Jen, you were a thumbs up. You were logged in. Steve, what about you?

@35:58 - Steve Dziedzic
are you Okay. volunteeree Såna's Margitans.

@36:00 - Maroun Najjar
Awesome. Samara? Ann, amazing. Corinne, you're two-factor off.

@36:08 - Corinne Sherry (she/her) - Design
I think I keep thinking I'm done and then there'll be another code. It's asked me for so many codes.

@36:17 - Ryan Herubin
You're good. Corinne, you're good. You're good. If you got that, you're logged into the terminal.

ACTION ITEM: Ensure all participants (Lizzie, Katelyn, Rafa, Janice, Corinne, Steve, Samara, Jennifer) accept repo invites - WATCH

@36:22 - Corinne Sherry (she/her) - Design
It just opened another thing in the browser asking me to authorize my device again. So it's confused with itself.

But I'll stop now.

@36:34 - Maroun Najjar
Okay. And as I'm seeing your usernames, I'm adding you to the repo, and I think you'll get an email invite.

But we probably won't get to that today, so that'll be for later. Okay, Groovy, I think that's everyone. Ryan, why don't we do the next, like, little batch of concepts?

@36:51 - Ryan Herubin
All right, cool. Yes, notes for me and Maroon. This is going to be a large part of the workload.

Cool. All right, so... Everybody has Git. What is Git? So, Git is a time machine. takes snapshots of your project, and just think of project as the code base of a working directory, a folder, a directory on your computer, and it saves it at every point you ask it to.

You can travel back and forward in that timeline however you want to, however far or however far back you want to, and nothing is ever truly lost, so you can always get it back.

So don't, like, I always tell Lizzie and Jen this, like, don't worry about breaking or deleting everything, because you can always undo it and get back to the start where you started from, the place where you started from.

So, you can spin up separate branches to try ideas out without touching a stable code baseline, and I'm going to explain that in the future with you guys.

You can experiment freely and merge what works when it works. So, um... So... ... GitHub is a shared drive.

It is the GitHub repository on your computer, out in the internet, on the server somewhere, so everybody can access it.

So it's similar to Dropbox, if you're familiar with Dropbox, which I believe everybody probably still is. I don't know if Dropbox is still a thing you need, but...

All right. And, something you guys were able to do in Claude, is you can... Claude can read the history of the repository just by asking it simple questions.

Like, tell Claude these things. And it will give you the answer if you're connected to GitHub and everything. So it will tell you and explain to you, hey, who changed the last homepage?

So, if you want to change something on the homepage, you can ask Claude this, and then, boom, immediately get to know which engineer you can kind of pair with on whatever you're doing, it's a bug fix, design update...

So you can use Git, GitHub, and Claude to help explain and get more information for you around what you want to do.

@39:09 - Jennifer Garfield
One thing I used this on recently is, you know, like, the bugs that come up in, like, non-urgent issues.

I was like, what, someone was like, why is this happening? And I went into Claude and said, what's the logic for this thing showing?

@39:21 - Ryan Herubin
And I was able to, like, help debug it. So anyway, just like a use case then.

@39:25 - Maroun Najjar
Mm Oh, cool.

@39:26 - Ryan Herubin
Yeah. So, branches. The first thing you want to do when you know I want to do X or Y or Z is you need to create a branch for X or Y or Z locally on your computer.

So how you do this, you create a branch. And I created this deck mainly off of Corgi. Lizzie and Jen, you'll know this is different for iOS because I don't have, I mean, my main line is different.

But in Corgi, let's just say you want to change a page. . On the website, you want to branch off of main because main is the stable working branch that all workload goes back into.

So everybody branches off of main, does their work, does the checks, the reviews, everything, and then goes back to main so it can then go out to QA and then finally production.

So just think of initial, nav done, branch off, these are just commits that someone, a designer, probably an engineer, has made in the past.

This is a stable, shippable code that has already been approved in either NQA or production. You then say, create a branch.

This is your safe little sandbox now of main called Feature New Hero. You can commit, you can say, okay, here's a draft of what the hero is and here's a refine.

this an end. Now, Let's Refinement commit of the code changes, and finally, you'll then merge it back in, and it'll go out to QA, then prod, and I'll explain that further.

So this branching, you also can tell Claude to do this, and these are some helpful commits that I had to generate so you can see how easy and just how natural language you can use in Claude, CLI or Claude code, to create a branch for you.

You can also ask it to switch you back to the main branch if you want to create a new branch.

So, I talked to you about commits. Commit is saving a snapshot of work you did. So, a good thing about commit is it doesn't matter how many of them you have in a given workload.

Basically, it is a body of work you don't want to lose. It's like kind of an award. It's state, a workable state, so to speak, it doesn't have to be completely working, but it's like good enough where you're like, I don't want to lose this, I'm going to commit this.

And you can add these in multiple steps on your branch when you do AI coding via Claude. And if you see this stuff, it's like, this is just like your, this will be your email address.

The commit ID is just a gibberish hash, it has a timestamp on it, and a message. So you can say what this commit, you actually did into commit, so you can be descriptive of these things.

And that's helpful for other people with the other commands they do is explain to me what just happened on this branch or on main the last 10 commits.

Like it will then go and read these and start assimilating information in the summary for you. So that's where that information comes from.

And to tell Claude to stage or commit, you can just use natural language yet again. These are the examples of how you can tell.

time, Google Now So you. Claude, that once you're done with your body of work, save it, and these are examples of how you save that in Claude.

Push and pull. So this is a way to have your Git local branch and local repository talk to GitHub.

So everything that you commit and all your commits are local to your machine. Just in case you don't want your machine to blow up or you lose it, you don't want to lose that body of work, you want to push those commits in your local branch to GitHub.

And that's what push is. You can also share, once you push, you can also share your branch with someone else that they can then pull those changes down that you just worked on, on their machine.

So if, like, Jin and Lizzie want to work on something in the iOS land, Jin can create something. Hey, I just did this analytics tweak.

an me wait for But I want, I just found out doing it that there's a design thing that needs to be done on the screen, here's my branch Lizzie, make your changes now, I'm done.

So Jen will then push those changes up to GitHub, Lizzie will then, because Jen will give her the branch name, pull those changes down and then work on it herself, so that's a way kind of engineers or designers or whomever can contribute to a work, the body of work in a branch.

@44:28 - Jennifer Garfield
So I'm, I haven't even merged it.

@44:31 - Ryan Herubin
No, you have not merged it.

@44:33 - Jennifer Garfield
Oh, okay.

@44:34 - Ryan Herubin
Merging is different.

@44:35 - Lizzie Belgum (Change.org)
that's confusing, go ahead Ryan.

@44:38 - Ryan Herubin
No, that was just merging is different.

@44:42 - Lizzie Belgum (Change.org)
Something that's confusing to me in this new language is you can pull something and it like means, it's like as basic and mundane as like downloading whatever is new.

@44:53 - Ryan Herubin
That pulling a branch is different than a pull request. A pull request is like a formal approval.

@44:59 - Lizzie Belgum (Change.org)
Okay. You So I just wanted to flag that because that really messed me up at the beginning.

@45:09 - Steve Dziedzic
One clarifying question. When Jen shares her branch with Lizzie, can Lizzie then just like bring it right up in clock code and be viewing that in the prototype and then like potentially make edits and then like read?

Yes.

@45:25 - Ryan Herubin
Because when you branch, you are changing the working directory, the code, the source, the code source, literally the text on every file in that working directory to what's in that branch.

So like you have the same code because you, as long as Lizzie and Jen have are on the same branch, they're all using the same code.

@45:50 - Steve Dziedzic
Nice.

@45:51 - Jennifer Garfield
So I can literally just go on cloud code and say, use this branch.

@45:55 - Ryan Herubin
Branch?

@45:55 - Jennifer Garfield
name?

@45:56 - Ryan Herubin
Mm-hmm.

@45:57 - Jennifer Garfield
Hmm.

@45:58 - Ryan Herubin
Yes. Okay. Because it's already pushed to origin, that is correct. So you'll hear words like origin and remote, and right now, for this level of the class, they're the same thing.

I'll put it that way. So remote and origin is GitHub right now. There is a world where they can be different, but we're not going to get into that right now.

So if you hear remote or origin, they're the same thing. Just for ease of understanding, right now.

@46:30 - Maroun Najjar
Can I take just a quick stab, Ryan, to try to summarize the concepts you've introduced so far?

@46:35 - Ryan Herubin
Sure. Yeah, absolutely.

@46:37 - Maroun Najjar
It's a bunch of new things. So you have your central code base, right? It exists up in the cloud.

When you want to work on it, you create a copy. It's called a branch. That branch is on your computer.

You can change the colors, do whatever you want to it. And then the process of taking that branch and putting it back up into that main code base.

And Ryan's going to go into the whole merging. The important thing to just call out is there's what exists in the, I'm going to keep using the word cloud, although it's like very 2000s, there's what exists in the cloud, so the remote repo, and then there's like the local copy you have on your computer, right, and so there's a whole process of like how do you keep those in sync, how do you like download the latest updates to what you have locally, so that's just one distinction to keep in mind in terms of like the setup.

@47:30 - Ryan Herubin
Yes, because once Lizzie, in my example, does her design work, Jen could think, oh, I forgot to do something else, the analytics tool, so Lizzie will then push her changes to GitHub for that range, and Jen will then pull it back down to catch back up, basically get all the code that Lizzie did, so that's kind of like how push and pull, it's supposed to be a dynamic like that, it's for collaboration.

So, um, and

@48:00 - Steve Dziedzic
And around the product org, I feel like people are prototyping HTML front end prototypes and then like sharing their entire HTML folder with other people and this would actually be very, be much more efficient.

@48:14 - Ryan Herubin
Yes.

@48:14 - Steve Dziedzic
love it.

@48:15 - Ryan Herubin
And not only will it be more efficient, every commit, you can go backwards and forward in the history of those commits, however much you want to.

So like you can literally like go back in history and be like, oh, Steve, if you did two commits, you know, if then, if Jen's like, I want to do something that doesn't have Steve's changes in it, she can branch off of before you change the commit and go in a different direction.

So like it has that power as well.

@48:43 - Samara Tager
That's cool. Is because it's saved to GitHub when you merge it? Yes.

@48:48 - Ryan Herubin
Yes, because every change is in GitHub, so like you're never going to lose those. I mean, you can, but we're not going to get into that because that's, that's more of like admin level stuff.

But so Steve's on one part of the branch and as long as it's not. Merge into main, I mean, you can go off of main, or you could go off of Steve's branch if you want to collaborate on something, like you like something that Steve did, but not all of it, you could go on to Steve's branch, and you want to commit, you want to branch off of, you can say that commit, then create a new branch off of that spot of origin.

@49:18 - Samara Tager
But is that only if you merge, or does Claude and Terminal keep a record?

@49:24 - Ryan Herubin
Your local git will keep a record of that, because it's synced up to GitHub.

@49:29 - Samara Tager
Okay, and it's synced up because we've done this login flow, and we know that it's synced.

@49:35 - Ryan Herubin
Yes.

@49:35 - Samara Tager
Okay.

@49:40 - Ryan Herubin
So, how to sync your work? How do want to push? You can tell, you don't have to worry about how to do this, you can literally tell Claude, like, right here.

Am I behind the remote branch? So if Jen and Lizzie are working on something, and Jen's at lunch, or out because it's-

You know, it's late in the afternoon, and Jen's already in dinner off with Kyle, and she can just ask Claude, am I all, do I have any changes from Jen that she didn't know me about before she went to dinner with Kyle?

Rude. So it's, you can literally talk to it like a human. I just want, I want to, I keep running on one of these screens interstitially, so to tell, you can really just use natural language and Claude IDE or Claude code to ask these questions.

You need to know any special terminal commands and stuff like that. I know the terminal commands because I've been doing it for so long, well, some of them, but yeah, Claude's really nice.

It makes, it makes this way, way better. I do this now even. So just as a point of conversation.

Oop, not too far. We have seven minutes left. Oh boy, we can do it. So, so far, we've talked about creating your local.

So, branch, making changes and pushing your commits up to GitHub. Now we're going to talk about opening up a PR.

So once...

@51:09 - Jennifer Garfield
You can create a branch in Git or just in Cloud Code, right?

@51:14 - Ryan Herubin
Cloud Code will create the branch in Git.

@51:16 - Jennifer Garfield
Right, right. But like you showed us like how to create it in Git, but also you could just do that in Cloud Code.

@51:22 - Ryan Herubin
Yeah, I... Can we practice making a branch? That was going to be part of this class that the GitHub terminal ate into.

So we are... Yes.

@51:35 - Maroun Najjar
Yeah, so I think what we'll do is I'll set up our next session. We'll just open with all of us downloading that repo I sent, and then we'll all do this together.

We'll create a branch, we'll make some edits, and we'll push it all back.

@51:50 - Ryan Herubin
So, once you have your branch, and you're like, this is my new shiny branch that I want someone to review.

Someone being an engineer. you hear. For Your squad, like your engineering partners to review, you create, you need to create a pull request.

What that does is you say, this is my branch, I want to go to main, or for Lizzie and Jen I want to go to develop branch because that's where, that's my main branch line, or if you, yeah.

Then, what that does is it opens up a line of communication to engineering on your squad that they need to review the code that you just had clogged, or any AI agent write.

And I wanted to really hone in on, PR isn't just something you do in GitHub, it's more of a conversation.

So, especially if the engineer might not know this is coming down, this is your, the point where the conversation needs to start and be like, hey, I want a new color for yellow now.

So I just did it, and here it is, and you can kind of seed the work. you With the communication, potentially, but it's more of a conversation than just say, here's my code, review it.

You want to have a conversation around it. And that's what Lizzie and Jen and I have done in our first iterations to it, and I think it's been helpful, the conversational piece to it, but I don't want to speak for Jen and Lizzie.

@53:24 - Lizzie Belgum (Change.org)
It's helpful.

@53:29 - Ryan Herubin
So review and discuss. So after your PR is created, then you review and discuss. And one, I don't want to come back to it, but this is also the ownership handoff.

When you create a PR, you will no longer be the owner of this branch in the code progression. It then belongs to one of your engineers.

Well, then come, review it, contribute to it, talk to you about what they changed, why you need to change something, whatever.

Yeah. Yeah. Yeah. Yeah. Exactly. And have that conversation, at the end of it though, the engineer will then approve and then merge the code in this branch into whatever origin you wanted to go to, main in this example.

So you, the product person right now, won't have to worry about merging. I know you guys have probably heard engineers talk about merging and all this new stuff, and rebasing, you don't need to worry about that.

That's still going to rely on the engineer, especially in Corgi, because Corgi has a lot of external CI, CD processes to get the code promoted.

And using totems and stuff like that, that you don't want to know about right now. So it's just part of the release pipeline.

Jen's like, Jen wants to know about it. So it's part of the release pipeline that engineering still manages. So this is, for all intents and purposes, the end, and then the engineer will take the branch and the code and get it QA'd and release it.

And obviously communicate. asking. care of Go ahead, Maroun.

@55:01 - Maroun Najjar
I was just going to add, and so this is for when we're working on features that will actually, like, find their way to production, right?

When it comes to just working on prototypes or concepts that we have, the merge piece is less important. Because you're kind of just working in your own little isolated environment, Cloud Code will handle all the branching and all of this stuff for you.

@55:25 - Ryan Herubin
Steve?

@55:25 - Steve Dziedzic
That's going to be my question, Maroun, actually to build on it. If I just want to play and, like, ideate on, like, in the actual, like, corgi on a branch, can I just do that and just not worry that it's kind of nonsense?

And just kind of, to my heart's content, keep pushing into the idea? Yes. Okay. Cool.

@55:47 - Ryan Herubin
That code will only live on your computer. won't live on a server or web server anywhere else. It will just be on your computer.

@55:58 - Steve Dziedzic
Good to all the teams.

@55:59 - Jennifer Garfield
teams.

@56:00 - Steve Dziedzic
So it's okay if it's just like off on its own branch. It's stored in GitHub, but it's like my nonsense branch in GitHub.

@56:08 - Ryan Herubin
Yes. That anybody would then, once you get to a point where you might want to share that nonsense branch, it's not nonsense anymore, then you can say, hey Lizzie, hey Jen, hey whoever, like this is my branch, pull it down and take a look at it.

Locally on their machine, running on their machine and nowhere else.

@56:24 - Steve Dziedzic
Mm-hmm.

@56:26 - Lizzie Belgum (Change.org)
And in that use case, Ryan, of just wanting like a sandbox essentially to play around, what would be the, like, main working development branch that you would want to branch off of?

@56:40 - Maroun Najjar
Does it matter? Or would you branch off of the main branch always? Well, I think, Ryan, if I could take a stab, we are not quite, so we're working on creating and figuring out what that is.

At least for, I think iOS is different than like Corgi, because Corgi, which if you don't know what It's our big codebase for the core product.

It's quite a big and hard thing to work with. We're working to just set up a separate template, essentially, for us all to work with.

But for right now, we're not quite sure what that is, and we're still actively figuring that out with Myron and Chris.

@57:22 - Ryan Herubin
Yeah, Maroun's right. Like, Lizzie and Jen have, it's a little bit different for me, because, and I'm in iOS land, and obviously Ricardo's in Android land, so it's different for us, but for Corgi, you always branch off of main, unless you talk to an EM or another product partner and be like, oh, I'm working on this branch, you want my branch, and they'll tell you what it is, and then you can branch off of that.

But for normal workload, you would branch off of main.

ACTION ITEM: Schedule next session (this week/next); then run hands-on Git/GitHub workshop w/ Ryan - WATCH

@57:50 - Maroun Najjar
Awesome. I'm going to just wrap us, just because I know we're at time, and talk about what we'll do next.

So, today we went through all the core concepts. Next time we'll be... All about practicing them and trying to work on one surface altogether and seeing what happens.

ACTION ITEM: Post class recap in AI Builders Slack; then ensure all participants have GitHub access - WATCH

So I'll set up time for that, hopefully, yeah, either later this week or next week. And I think between now and then what I'll do is I'll recap the class, I'll post that update in our Slack channel, and then I'll also make sure that everyone is caught up and has GitHub access and all that stuff is sort of like set up.

ACTION ITEM: Send Git/GitHub HTML doc to Maroun; then Maroun integrate into course docs - WATCH

So yeah, thank you so much, Ryan, for all the teaching and for putting all this together.

@58:31 - Ryan Herubin
Yeah. And this is an HTML file that Maroun will then fold into all the documentation that he's been generating for this course and this class, classes, and all that stuff.

So this will be shared out. I'm going to share this with Maroun for you guys to be able to look and touch whenever you want to.

@58:50 - Steve Dziedzic
This is awesome.

@58:54 - Maroun Najjar
Awesome. Thanks, y'all.

@58:56 - Jennifer Garfield
Y'all are so patient.

@58:58 - Ryan Herubin
Thank you. Yes. Yes.

@59:02 - Maroun Najjar
Thank you.

@59:03 - Lizzie Belgum (Change.org)
Thank you.

@59:04 - Maroun Najjar
Bye.
