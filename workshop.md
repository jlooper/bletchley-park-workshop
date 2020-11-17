# Workshop Instructions

In this workshop, we will discuss *insert your topic*.

| **Project Goal**              | *describe the goal of the project*                                    |
| ----------------------------- | --------------------------------------------------------------------- |
| **What will you learn**       | You will create a storytelling choose-your-own adventure type game by enhancing sample code                                        |
| **What you'll need**          | Follow the instructions on the [sample code repo](https://github.com/jlooper/static-game-engine) |
| **Duration**                  | 1-2 hours                                                               |
| **Just want to try the app?** | A game using this engine at its core is the [Azure Maya Mystery](https://aka.ms/AzureMayaMystery)                         |

## Pre-Learning

While you can create your web app and run it locally, you might want to deploy it to the cloud for others to enjoy and try. A good way to do that is to use Azure Static Web Apps. Learn [how to build them](https://docs.microsoft.com/learn/modules/publish-app-service-static-web-app-api/?WT.mc_id=academic-9433-jelooper) using the underlying technology used in this workshop, [VuePress](https://vuepress.vuejs.org).

## Architecture

The seed code on which you will build your project has two pages: one that takes you to another page, and another that allows you to collect an item for your inventory. 

Here's how the first screen looks now:

![homepage](screenshot.png)

Your first task is to go through the codebase and see how it functions.

In the `app` folder, you find the 'brains' of the web app, the `package.json`. This file tells your app what packages need to be installed to make it run. Before you run it locally, `cd` in your terminal to the `app` folder and, assuming you have node and npm locally installed (note the instructions on the seed code repo) type `npm i` to install the packages you need. You will run the site on localhost using `npm run dev`.

Note the `tailwind.config.js` folder. The styles of this app are driven by the [Tailwind CSS library](tailwindcss.com).

## Build the interface

*code snippets to aid in the building proces*

> *tips, tricks, callouts*

## Build the backend

*detailed instructions and code snippets*

```
{ sample code here }
```

What's going on here? 

*explanation*

## Style the app

*any frontend styling*

## Build the API

*instructions on how to build the API or other backend services*


## Deploy the app

*deployment instructions*

## Next steps

*links to Learn to further learning progress, and any path to certifications*

## Feedback

*include instructions on how to give feedback, perhaps in the issues tab if enabled* 

[Code of Conduct](CODE_OF_CONDUCT.md)

[Contributing Guide](CONTRIBUTING.md)
