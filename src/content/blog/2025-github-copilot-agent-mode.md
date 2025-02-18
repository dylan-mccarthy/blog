---
title: 'GitHub Copilot Agent Mode'
description: 'Lets take a look at the new Agent Mode in GitHub Copilot'
pubDate: 'Feb 18 2025'
heroImage: '/blog-header.png'
---

Last week, we explored how GitHub Copilot can help with planning and breaking down tasks. This week, I want to introduce you to a new feature: Agent Mode.

Agent Mode is a new way of using GitHub Copilot in your IDE. It provides Copilot with the functionality to iterate on its own to achieve the goals set in your initial prompt.

To access Agent Mode, you need to be using the preview version of Visual Studio Code. Once configured, you can find Agent Mode within the Copilot Edits tab:

![AgentMode](/blogimages/gh-copilot-agent/AgentMode.png)

You can switch between Edit Mode and Agent Mode using the dropdown menu. You can also choose which base LLM Copilot uses. For the examples in this post, I used Claude 3.5 Sonnet.

## Let's Put Agent Mode to Work

To assign a task to the agent, I set up a basic NextJS application using `npx create-next-app@latest` and ran it with the following prompt:

![InitalPrompt](/blogimages/gh-copilot-agent/InitalPrompt.png)

The goal here is to give it a series of things to accomplish, and so far in testing I have found the more detailed you can make the request will effect the quality of the result at the end. I intentionally left some details, like the colour scheme, ambiguous to test how the agent handles such scenarios.

## Initial Response and actions

After receiving the prompt, Copilot returned the following:

![InitlalPromptResponse](/blogimages/gh-copilot-agent/InitlalPromptResponse.png)

We can see that it started off by looking for files matching tsx and css, already picking up that we are using TypeScript here.

After locating the necessary files, it created a file and a component to handle the theme. It then prompted us to run a command to create some directories.

By hitting continue the command is run in a terminal for us

![CommandError](/blogimages/gh-copilot-agent/CommandError.png)

However, the command failed due to incorrect syntax for creating multiple directories. Although Agent Mode got tripped up initially, it noticed the error and tried an alternative approach.

![CommandFix](/blogimages/gh-copilot-agent/CommandFix.png)

Unfortunately it doesn't seem to recognize why the command is failing, but instead of getting stuck and giving up it switched to using another method and continues on

![ContinueDev](/blogimages/gh-copilot-agent/ContinueDev.png)

![ContinueDev2](/blogimages/gh-copilot-agent/ContinueDev2.png)

Again it hits another area where a command is required, this time to install the testing components, and with this command there is no errors and they install just fine.

Once installed the agent continues on

![ContinueDev3](/blogimages/gh-copilot-agent/ContinueDev3.png)

Here we get prompted by Copilot asking if we want to continue iterating, this is a limit set by the tool to stop after so many responses and check that the agent is going the right way. So far things look good so we continue on.

![RunTests](/blogimages/gh-copilot-agent/RunTests.png)

So now the agent has put in place the tests into the package.json here and asks us to run them in the command line.

![TestResults](/blogimages/gh-copilot-agent/TestResults.png)

The tests run and all pass, the agent picks up from the command line again and can see the tests have passed.

 ![DevFinished](/blogimages/gh-copilot-agent/DevFinished.png)

And we are done, let's have a look at what has been build.

## Agent Output

Let's now have a look at what the agent produced, starting with the site main page:

![MainPage](/blogimages/gh-copilot-agent/MainPage.png)

The main page looks acceptable, but it reflects the ambiguous colour scheme from the prompt. Although the result isn’t perfect, all the content is present, and the overall structure provides a solid starting point.

Next we have the Team Page

![TeamPage](/blogimages/gh-copilot-agent/TeamPage.png)

Again the colours are not the best but it has created a pretty serviceable page here, ready for the real information to be plugged in.

And lastly the contact form:

![ContactPage](/blogimages/gh-copilot-agent/ContactPage.png)

Looks pretty good.

So what about the Light/Dark modes? Well we can see there is the button for it, but when clicked it only changes the colour of the header, we could ask it to fix that and continue iterating, but for this demonstration we can leave that for later on.

## Summary

We have seen that Agent Mode enables Copilot to do more with less prompting, as it iterates on its own while checking against the initial goals.

It still faces challenges and relies heavily on the quality of the initial prompt, but overall, I am impressed by its ability to iterate independently, read terminal output to identify issues, and continue despite early errors.

While the demo might be pretty simplistic I think this is where Copilots can really help us achieve more productivity, by getting the boiler plate out of the way and helping us get to the stage where deep knowledge is needed around the business and system designs.

If you would like to review the generated check out the GitHub repo [here.](https://github.com/dylan-mccarthy/GH-Copilot-AgentMode-Blog-demo)

And if you would like to try out agent mode visit the GitHub blog with the details [here.](https://github.blog/news-insights/product-news/github-copilot-the-agent-awakens/)

Let me know how your experience with Agent Mode goes!
