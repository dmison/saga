# Saga

[![Travis](https://img.shields.io/travis/txus/saga.svg?style=flat-square)](https://travis-ci.org/txus/saga)

Saga is an experimental programming language for interactive fiction. Think
"choose your own adventure" but with the dynamism of a Turing machine.

TL;DR (a better writeup will come soon): Stories are sets of passages with
pre-conditions, consequences and choices with consequences. Pre-conditions and
consequences are facts.

Playing a story starts with an empty bag of facts, and as you go through
passages you accumulate facts, which the engine uses to decide which passages
are possible next. If there is a choice between many, it is random (this will
change when probabilistic events are introduced.)

#### What's in this repo?

Eventually this Readme will be nice and complete but for now just something to
get you started.

This repo contains two separate projects that share some common code:

* IDE: An IDE to build stories.
* Player: An app to play stories.

The interpreter used by the player lives in the `saga.engine` namespace.

Saga programs (stories) are exported and imported as EDN files. More about this
to come.

![Saga IDE](/screenshots/ide.png?raw=true "Saga IDE")

## Building

You'll need [Boot](http://boot-clj.com) (`brew install boot-clj`).

To build the IDE:

    boot package -t ide
    open target-ide/ide.html
    
To build the player:

    boot package -t player
    open target-player/player.html
    
## Developing

This project is built entirely in ClojureScript. The IDE and the Player are both
separate Om Next apps. You'll need [Boot](http://boot-clj.com) (`brew install boot-clj`).

To work on the IDE:

    boot ide-dev
    open localhost:3000/ide.html
    
To work on the player:

    boot player-dev
    open localhost:3000/player.html

## Tests

There are currently no automated tests. To run them anyway:

    boot test
    
## Roadmap

### General 

* [x] Basic IDE working
* [x] Basic Player working
* [x] Exporting stories from IDE as EDN files
* [x] Loading stories from Player as EDN files
* [x] Saving / restoring app state automatically from local storage (IDE & Player)
* [x] HTML5 Offline capability
* [x] Material design in the IDE
* [ ] Material design in the Player
* [ ] Probabilistic passage links
* [ ] Probabilistic facts

### Tooling / Debugging

* [ ] Debugging a passage by running it with a canned bag of facts
* [ ] Debugging-enabled player within the IDE (manipulating facts, etc)
* [ ] Debugging-enabled player within the IDE (manipulating facts, etc)
* [ ] User-driven, generative testing of stories

### Sanity

* [ ] Test everything!!!
* [ ] Write about Saga's design decisions

### Release

* [ ] Package Player as a React Native app
* [ ] Set up Github releases with Travis CI artifacts
