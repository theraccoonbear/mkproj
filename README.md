# mkproj

## Project Scaffolding

Sure, there's lots of tools to do this, but why not make my own, half-functional, brittle version?

### Prerequisites

`mkproj` is just a bash script tying together some other people's software that's
_actually_ useful.  Make sure you have the following tools available:

 * `git`
 * `yarn`
 * `jq` (don't even ask)

### What Can It Do?

Right now?  Not much.  Basically it can currently only scaffold a TypeScript project.

### Well, how do I do that?

Easy...

`mkproj ts`

Assuming you have the prerequisites installed, you should be golden.

### OK, what does that get me?

A working (globally installed) TypeScript compiler.  A TypeScript project bootstrapped with some basic dev
dependencies for TS/types and source-mapping for sane stack traces.  This even uses some `jq` madness
to inject a few helpful `script`s into your project's `package.json`.

```
{
    "start": "...",         // runs the compiled JS
    "to-ts": "...",         // if you've copied your existing `.js` sources to `./src` it'll recursively rename them to `.ts`
    "build": "tsc",         // compile your code
    "build:watch": "tsc -w" // compile the code in watch mode
}
```