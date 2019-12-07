# The base framework.


I wrote __Mana__ about a year ago and used it for a project
on Upwork. It was...okay. Using it for a real application
pointed out some of the flaws and gave me some things to
think about. I knew where improvements could be made and so
it was time to get to work.

I had the idea for __bitraq__ a while ago but I didn't have
the time to waste on personal projects - it just wasn't a
luxury I could afford, Mana was a necessity...but sometimes
it's hard to suppress that need to bring your ideas to life!

So, learning from some of the problems I had with Mana -- I
decided to throw this together. It's a lot cleaner and
tighter. Using it to build bitraq has been a far more
pleasant experience - I don't want to take Mana down because
it was something I enjoyed writing and think it's still a
fairly decent project.


## Improved templating engine.

I've designed it so that the page templates can include
CSS - we can add styling using:

```
	[CSS[
		.some-style {
			...
		}
	]CSS]
```

These blocks are extracted from the templates and compiled
and inserted into the HTML document, we can do similar with
JavaScript:

```
	[JS[
		some code
	]JS]
```

Then, in our layout:

```
	<!DOCTYPE html>
	<html lang="en">
		<head>
			<style>
				<!-- collected CSS blocks are compiled and expanded here -->
				[[CSS]]
			</style>
			<script>
				<!-- collected JS blocks are compiled and expanded here -->
				[[JS]]
			</script>
		</head>
```

This works pretty well, I've also ensures that the CSS and
JS code are eval()'d in php so we can use variables and
other php goodies within these blocks - allowing for fairly
complex and dynamic code to be generated for the front-end.

This has been awesome since a template is now more like a
self-contained component, it's a nice way to work. Some
might not like that a huge chunk of CSS will be inlined 
into their document - you can still include a .css file
directly if that's what you want. But in terms of speed
it's one HTTP request less at the end of the day.

For __bitraq__ I have a main .css layout that contains
site wide styling, and each individual page loading components
with their own embedded CSS and JavaScript, so it's relatively
clean and easy to manage and maintain projects.

When I'm done with bitraq I'll upload the completed project
and that will give a full demo on how it all works together,
but it's a lot nicer than Mana and I'm happy with it, I'll
be using it again for sure.

The templating engine is just better all-round, having put
more thought into the design. I separated much of the functionalty
out so it's cleaner and more modular.


## Improved data model.

I uploaded this class a few days ago because it's useful just
on it's own. There were odd isssues with Mana and how I was
defining/creating table schemas - it was more complex than it
had to be and tightly coupled with other modules within Mana,
which was bad!


## Static hell

Yeah, I ued a lot of singletons and static classes in Mana,
seemed like a good way to go at the time but cracks did start
to show when the project got larger.

That's gone - I've also added a batching system that allows
a single request to queue up multiple actions for execution,
it's running really well and offers far more flexibility than
Mana did - so definitely a huge improvement and I'm pretty
pleased with how it's performing.


## Bitraq

Should probably give some background, here. Bitraq is sort of
like Stack Overflow but with a twist. Rather than request help
with something code-specific, bitraq allows you to define new
projects, you add a project - a link to the repo, some info
about the project and from there you can produce bug reports
for those projects.

These reports can then be viewed by other members, the report
will tell you about a specific issue with an application, and
how to reproduce that issue for yourself. 

Users can then offer solutions to the problem and the user
can accept an answer that solves the problem - in this case the
user who answers gains a point on their reputation.

So it's a similar merit-based platform, but a way for people to
collaborate and solve issues/bugs with existing applications or
applications they're currently working on.

Aside form that, it acts like a typical social media site, you
can add friends, message other users, etc.

I'm in that final 20% bit where it's kinda...ugh! But almost there
and happy with the progress. I'm going for MVP - not so concerned
about aesthetics and fancy bells and whistles for now, it looks
nice and is fully responsive as it is which is important, but once
it's fully functional I'll spend more quality time on the UI.

Suggestions, criticisms - contributions? Have at it, it's all
good.

Will keep this updated as I go, but anyone is free to tinker with
this code as they wish I really don't mind. 

will do my best to knock some documentation together, I intend
to continue developing this framework - once bitraq is complete
I intend to add API functionality, for now it's serving full
HTML pages but I want to be able to use it for fetching JSON
objects. I wrote __Bricktop__ a while ago which was my effort
in dabbling with building a front-end framework, lot of fun
and learnt a lot, but learnt more since so there's room for
improvement - maybe one day I'll be developing projects using
my own stack! How cool would that be?

Will update as often as I can - been busy as hell the past
few months and neglected my github, need to be a bit more selfish
with my time I reckon! Excpect to see more regular activity
over the coming months.


Michael.
