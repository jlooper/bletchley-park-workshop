# Workshop Instructions

In this workshop, we will discuss *insert your topic*.

| **Project Goal**              | *describe the goal of the project*                                                                |
| ----------------------------- | ------------------------------------------------------------------------------------------------- |
| **What will you learn**       | You will create a storytelling choose-your-own adventure type game by enhancing sample code       |
| **What you'll need**          | Follow the instructions on the [sample code repo](https://github.com/jlooper/static-game-engine)  |
| **Duration**                  | 1-2, or more if you create a complex story! hours                                                 |
| **Just want to try the app?** | A game using this engine at its core is the [Azure Maya Mystery](https://aka.ms/AzureMayaMystery) |

## Pre-Learning

While you can create your web app and run it locally, you might want to deploy it to the cloud for others to enjoy and try. A good way to do that is to use Azure Static Web Apps. Learn [how to build them](https://docs.microsoft.com/learn/modules/publish-app-service-static-web-app-api/?WT.mc_id=academic-9433-jelooper) using the underlying technology used in this workshop, [VuePress](https://vuepress.vuejs.org).

## Pre-Coding

Fork the [seed code](https://github.com/jlooper/static-game-engine) and start exploring the game engine. Make sure you environment is set up as described in the seed code README.
## Architecture Review

The seed code on which you will build your project has two pages: one that takes you to another page, and another that allows you to collect an item for your inventory. 

Here's how the first screen looks now:

![homepage](images/screenshot.png)

Your first task is to go through the codebase and see how it functions.

### Running the App

In the `app` folder, you find the 'brains' of the web app, the `package.json`. This file tells your app what packages need to be installed to make it run. Before you run it locally, `cd` in your terminal to the `app` folder and, assuming you have node and npm locally installed (note the instructions on the seed code repo) type `npm i` to install the packages you need. You will run the site on localhost using `npm run dev`.

### Styles

Note the `tailwind.config.js` folder. The styles of this app are driven by the [Tailwind CSS library](tailwindcss.com). You can see how Tailwind markup styles 
elements by looking at `app/game/.vuepress/components/theme/layouts/Layout.vue`. Syntax like this: `<div class="markdown-body font-serif bg-white m-2 sm:m-3 md:m-6 lg:m-12 text-lg rounded-lg">` is typical of Tailwind. `Bg-white` for example creates a white background for the `<div>` in question. 

You can override styles in the `app/game/.vuepress/components/theme/styles/` folder. In the `index.styl` file you can create a new look for your game.

> Take the time now to think about the type of story you want to tell. Sketch it out on paper. Are you creating a space mystery? A spooky old attic? A futuristic city? A medieval castle? Think about the colors and fonts that might look good in your game. 

While your game is running, edit the `index.styl` file to make the colors look like your game theme. The top area has backdrops, so look for interesting images from Unsplash or other Creative Commons imagery to use to give an atmosphere to the game. These images go into `public/images` and you can change backdrops in the numbered markdown files like `1.md`.
## Design the game

Now that you have the game running and styled, you can start designing the steps of the game. You can create a linear game by creating a sequence of markdown pages in the `game` folder. You can create a branched experience by adding subfolders like: `game/mission1/1.md`, `game/mission2/1.md` where you give the player decisions on which way to go.
## Build the game

The basic way to build this game is to add markdown pages, written with a storyline, and including markup to switch pages and gather items.

### Inventory

In your markdown file, allow the user to pick up an inventory item by embedding an Item: `<Item id="1" />`. This item number refers to an item you add to `app/game/.vuepress/theme/utils/items.json`. This JSON-formatted file contains all the inventory available to your player:

```
[
	{
		"id": 1,
		"instructions": "Pick up the",
		"name": "key",
		"initialHide": true,
		"result": "You use your ship's robotic arm to pick up the key."
	
		
	},	
	{
		"id": 2,
		"instructions": "instruction 2",
		"name": "name 2",
		"gameItem": "game item 2",
		"initialHide": true
	}
]
```
If you add a piece to be picked up, add a comma to the previous element, and create a new object:

```
    {
		"id": 3,//match the id
		"instructions": "Pick up the",//written instructions
		"name": "jewel",//clickable word
		"initialHide": true,//don't show this item until a condition is met
		"result": "The jewel suddenly burns red hot!"//what happens when you collect the item
	}
```

### Pages

To add a page, you can use syntax like this: `<Page url="2" instructions="" action="Fly West" condition="1" />` - here, you send your adventurer to page 2 (`2.md`), with optional instructions. The page link will hint where you're going, and the page link won't show until a condition is met (in this case, you have to pick up a key to see the link). Experiment with the engine to customize your user's journey. If you want to make changes to the logic of the relationship between inventory and page, edit the `app/game/.vuepress/game/Page.vue` file. You can see how certain elements appear and disappear based on the way the page links are formatted.

## Deploy the app

If you'd like to deploy this game to the cloud using Azure Static Web Apps, here's a button to help you do that: 

[![Deploy to Azure button](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/?feature.customportal=false&WT.mc_id=academic-9433-jelooper#create/Microsoft.StaticApp)

## Next steps

You can always make a game more complex! How can you add more interest, or a more winding storyline, to your game?
## Feedback

If you have feedback on this workshop, open a GitHub issue on this repo to let us know.

[Code of Conduct](CODE_OF_CONDUCT.md)

[Contributing Guide](CONTRIBUTING.md)
