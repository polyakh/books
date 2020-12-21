### Chapter 4

### Chapter 7
**What’s Webpack All About?** <br/>
There are just a few core concepts that you must have at least a basic grasp of to use Webpack with your applications.

1. Dependency Graph
   When you tell Webpack to bundle your application, it looks at all the files it finds in
   It examines them and determines which files depend on which others. It builds what’s called a
   dependency graph from that analysis, and with that, it can determine what needs to be
   included, what can be dropped, what order things need to be in, and so on. Without
   the dependency graph, nothing Webpack does would be possible, so while you won’t
   be dealing with it directly in any way, it’s essential to understand that’s how Webpack is
   doing its work on your behalf.
   
2. Entry
   When Webpack builds the dependency graph, it’s constructing a tree structure under
   the covers, and any tree structure must begin from a single point, or node, or in the case
   of Webpack and web applications: a module.
   Webpack will assume the entry
   point is called ./src/index.js, relative to the directory it’s run in. But you, of course,
   can name a different starting entry point.
   Regardless, from that starting point, the dependency graph is built as Webpack examines the entry
   point and then recursively examines each file that it in any way depends on.
   
3. Output
   That’s the typical model that Webpack follows:
   a src directory where all your unbundled source code lives. But where does Webpack
   put your bundled code? The answer, by default, is a directory named dist (short for
   distribution). Further, by default, the name of the bundle that will be created is main.js
   
4. Loaders
   Out of the box, Webpack only understands one thing: JavaScript (well, it also
   understands JSON files, but given that JSON is a subset, or component, of JavaScript,
   it’s still really just one thing).
   A loader has two critical attributes associated with it: a test property and a use
   property. The test property enables Webpack to determine which files it should
   transform. The use property specifies what loader to use for it. When put together, a
   rule is formed that Webpack will follow that basically says: “Hey, Webpack, when you
   encounter a reference to a file whose path matches the test property, go ahead and
   process that file with the loader specified by the use property, pretty please?”
   ```javascript
      module : {
         rules : [
            { test : /\.(jpg|png)$/, use : { loader : "url-loader" } }
         ]
   }
   ```
   
5. Plugins
   Need to optimize your bundle? Plugin! Need to insert some environment variables
   into your bundle? Plugin! Need to add I18n resources to your bundle? Plugin! Want to
   add some sort of copyright notice to the top of each generated bundle? Plugin!

Modes
Whenever Webpack performs a build, it can be done in one of several modes: development,
production, or none. Which mode is used determines which of the built-in
plugins are
used, if any, and controls what options are passed to them to do their work. In simplest
terms, the mode determines what optimizations Webpack does to your bundles.