![Splat ECS](./images/splat-logo.png)

A 2d HTML5 Canvas game engine

Splat ECS is a 2d game engine made for creating multi-platform games entirely in JavaScript. Splat ECS is built around the [Entity Component System](https://github.com/ericlathrop/entity-component-system) pattern, which is flexible and promotes composition of behaviors.

# Features

* Rectangles!
* Keyboard, mouse, touch, & gamepad input
* Sounds and music (Web Audio API and HTML5 Audio)
* Sprite animation
* Asset loading, and built-in loading screen
* Games work well on phones, tablets, and desktop browsers.
* A\* Pathfinding
* Particles
* SCREENSHAKE
* Tiled map editor support
* Easing

# Supported (tested) Platforms

* Chrome (desktop & mobile)
* Firefox
* Internet Explorer (desktop & mobile)
* Safari (desktop & mobile)
* Mac using [Electron](https://github.com/atom/electron)
* Linux x64 using [Electron](https://github.com/atom/electron)
* Chrome Web Store (currently broken [see issue #69](https://github.com/SplatJS/splat-ecs/issues/69))
* Android using [Cordova](https://cordova.apache.org/)

Splat now works in Cordova, and due to updates to recent phone browsers we have seen good framerates on Android in google Chome. We have not tested Cordova builds on iOS yet, please let us know what you find out.

# Requirements
* Browser (like Firefox or Chrome)
* Text editor
* Terminal
* [Node.js](https://nodejs.org/en/)

# Create a new Game
1. [Clone or download a zip of the starter project](https://github.com/SplatJS/splat-ecs-starter-project)

Create a file named game.js and start your game with this code:
```javascript
"use strict";
var Splat = require("splat");

var canvas = document.getElementById("canvas");

var manifest = {
	"images": {},
	"sounds": {},
	"fonts": {},
	"animations": {}
};

var game = new Splat.Game(canvas, manifest);

game.scenes.add("title", new Splat.Scene(canvas, function() {
	// Initiaization
},function(elapsedMillis) {
	// Simulation
}, function(context) {
	// Draw
}));

game.scenes.switchTo("loading"); // Start loading scene which will switch to 'title' scene when all the assets in manifest are loaded.
```

Install [browserify](http://browserify.org/)
```
$ npm install --save-dev browserify
```

Then use browserify to bundle your game as a single JavaScript file for the browser.
```
$ browserify game.js -o index.js
```

Include canvas element with id "canvas" and bundled JavaScript file (Splat + Game) on your html page:
```html
<canvas id="canvas" width="1136" height="640"></canvas>
<script type="text/javascript" src="index.js"></script>
```

# Games using Splat (ECS)
* [Cluster Junk](https://github.com/TwoScoopGames/Cluster-Junk)
* [Cali Bunga](https://riseshinegames.itch.io/cali-bunga)
* [Flip Flap Pong](https://riseshinegames.itch.io/flip-flap-pong)
* [Polymorphic](http://riseandshinegames.github.io/Polymorphic/build/)
* [Electropolis](https://two-scoop-games.itch.io/electropolis)
* [Morning Ritual](http://twoscoopgames.com/morningritual/game/)
* [Drunken Boss Fight](http://aquisenberry.itch.io/jam-build)
* [Zen Madness](http://aquisenberry.github.io/ggj_meditate/build/)
* [Treatment and Control](http://twoscoopgames.com/ggj15/)
* [The Day the World Changed](https://github.com/TwoScoopGames/ggj15)
* [Uprooted](http://twoscoopgames.com/ld32/)

See more Splat games at [http://splatjs.com/](http://splatjs.com/)

Send a pull request to add your game to the list!

## Contributing

If you are interested in participating in this project, please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details on our code of conduct.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/SplatJS/splat-ecs/tags).

## Authors

* **[Eric Lathrop](https://github.com/ericlathrop)** - *Initial work*

See also the list of [contributors](https://github.com/SplatJS/splat-ecs/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.TXT](LICENSE.TXT) file for details
