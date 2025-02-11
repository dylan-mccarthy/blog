---
title: 'AI Enchanced Workflow using GitHub Copilot'
description: 'My experience using GitHub Copilot to enhance my workflow'
pubDate: 'Feb 11 2025'
heroImage: '/blog-header.png'
---

Planning for software projects can be difficult at times, having to spend a lot of time defining all the features, then understanding the technical requirements and if you miss something it can be a pain to add later.

But as AI becomes more intertwined with the day to day experience of being a software developer I thought it might be helpful to show one of the ways that I have been using AI in my own projects to help me be more productive and get my plans in shape.

While I will be going through things step by step this is by no means the only way to use AI to help with development, this is just the current way that I have been using it.

With that said let's start off with a new project, for this example I'll be building a basic e-commerce website.

The first thing I do is that I use AI as a sounding board, to help flesh out the idea that I have and help me think of things that I might not have thought about.

I am going to use GitHub Copilot on GitHub.com for this example but it can just as easily work using ChatGPT, Claude or even a local LLM.

## Breaking down the idea into features

So we start with a simple prompt:

![Starting Prompt](/blogimages/ai-workflow/startPrompt.png)

This is pretty basic but here you can see that I've indicated three key things, first what it is that I want to build, the E-Commerce website, second the framework which is NextJS and last is that I want to use TypeScript for this.

Now before I start really diving in it is worth mentioning that I did create a new repo for this already with the default NextJS TypeScript application.
I have found that while GitHub Copilot can help with creating this it does tend to be easier to use the CLI tool to ensure you have a good base project that builds cleanly.

So here is the response from Copilot:

![First response](/blogimages/ai-workflow/firstResponse.png)

So we can see that it has given a good list of features, and also included some advanced features in this list which is great. From here it is usually a good idea to spend some time iterating over the idea to come up with a definitive list of features, but for this example we are just going to keep moving forward.

## Features into Technical Requirements

Now that we have a list of features, the next step is working out how to implement this, again we use Copilot to help us break things down.

![Features Prompt](/blogimages/ai-workflow/featuresPrompt.png)

This can help give me details around how to implement things and also expose parts of the application which don't appear as features visible to the user but are still required.

Here is the response:

![Features Response](/blogimages/ai-workflow/featuresResponse.png)

So here we can see that along with breaking down the technical parts it also starts to help us by suggesting possible technologies to use so that we can make decisions. Here you could ask for more detail on a technology or even input using some different ones that are not on the list. The more detail you go into here the easier it will be for the next step, breaking down these items into tasks.

## Creating Tasks using GitHub Issues

From here I prompt Copilot with the following:

![Tasks Prompt](/blogimages/ai-workflow/tasksPrompt.png)

And in response I get the this from Copilot:

![Tasks Response](/blogimages/ai-workflow/tasksResponse.png)

So it doesn't look like it has provided us with exactly what we asked for, and this can be a common occurrence with using tools like Copilot, The key here is to understand what it has given us, in this case it has given a recap of the features we worked on in the previous two sections, what is important to notice though is that it is asking for you to confirm the plan before is moves on, it also asks if you want to use any specific labels.

So here is what I responded with:
![Tasks Response](/blogimages/ai-workflow/tasksRefinePrompt.png)

And in response I got a list of Issues to create to track our tasks. I did also ask after the list for it to format it into a table so it was easier to see here:

![Tasks Table](/blogimages/ai-workflow/tasksTable.png)

## Next Steps

Without tasks outlined we can now move them into GitHub Issues. Once they are in place, GitHub Projects provides a structure way for us to track progress and plan out what tasks need to be done next.

You can also work with Copilot to further refine the tasks, adding more detail, adjusting the labels or manipulating the tasks as you need.

The biggest advantage here is that it can be so easy to iterate over an idea while still having the context of what you have been working on before, letting you adjust the plan to your liking while also getting feedback on things you might have missed or not thought about.

## So where to from here?

While you could just now move to building out the project yourself there is also two different AI enabled ways you could go.

These are GitHub Copilot Workspace and GitHub Copilot Agent.

Copilot Workspace is a platform that is built into GitHub.com and enables us to feed in the issues and have Copilot try to solve the issue for you, whereas the Agent approach has you open the codebase locally and provide the instructions to the Agent using the GitHub Copilot chat interface.

Both are still in technical preview right now, but have different ways in which they try to have Copilot do more, I'll cover more on both of these in later blogs.

## Conclusion

So to wrap things up, bringing AI tools like GitHub Copilot into your workflow can make a big difference in productivity.

By using Copilot to help brainstorm ideas, break down features into technical requirements, and generate structured tasks, you can streamline the planning and development process, making it easier to stay on track and iterate on ideas quickly.

While AI won’t replace good planning and critical thinking, it can act as a great assistant, helping to refine ideas and surface things you might have overlooked.

I’d love to hear how you’re using these tools in your own projects—what’s worked well for you, and where have you found challenges? Let’s keep the conversation going!
