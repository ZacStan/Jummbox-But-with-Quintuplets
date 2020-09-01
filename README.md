# JummBox

JummBox is an online tool for sketching and sharing instrumental melodies.
You can find it [here](jummbus.bitbucket.io).
It is a modification of the [original BeepBox](https://beepbox.co), focused on improving ease-of-use.

All song data is packaged into the URL at the top of your browser. When you make
changes to the song, the URL is updated to reflect your changes. When you are
satisfied with your song, just copy and paste the URL to save and share your
song!

JummBox is free, as is BeepBox. If you ever feel so inclined, definitely send something to the original creator, [John Nesky](http://www.johnnesky.com/)'s
[PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=QZJTX9GRYEV9N&currency_code=USD). He deserves it :)

## Compiling

The compilation procedure is identical to the repository for BeepBox. I will include the excerpt on compiling from that page's readme below for convenience:

The source code is available under the MIT license. The code is written in
TypeScript, so to compile it you'll need to
[install the TypeScript compiler](https://www.typescriptlang.org/index.html#download-links),
and to do that you'll need to have already installed
[node and npm](https://nodejs.org/).

Running the TypeScript compiler command (tsc) in the repository should output
JavaScript (.js) files into the website/ folder. I also recommend
[installing uglify-es](https://www.npmjs.com/package/uglify-es)
because I use that to create minified JavaScript (.min.js) files. I've included
shell scripts that run the compiler and minifier for you.

Those who are familiar with TypeScript may be surprised to learn that I do not
use any of TypeScript's module systems. Instead I use
[triple-slash references](https://www.typescriptlang.org/docs/handbook/triple-slash-directives.html)
to include code and
[namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)
to keep it out of the global namespace. That means that I don't need any web
pack system to be able to deploy a single JavaScript file. I don't use any other
libraries so I don't need a package manager either, aside from installing npm in
order to install TypeScript and Uglify. BeepBox is relatively self-contained.

## Code

The code is divided into several folders. Again, this bit is all the same as BeepBox. I will include the original excerpt again for reference.

The synth/ folder has just the code you need to be able to play BeepBox songs
out loud, and you could use this code in your own projects, like a web game.
After compiling the synth code, open website/synth_example.html to see a demo
using it.

The editor/ folder has additional code to display the online song editor
interface. After compiling the editor code, open website/index.html to see the
editor interface.

The player/ folder has a miniature song player interface for embedding on other
sites.

The website/ folder contains index.html files to view the interfaces, and the
TypeScript compiler is configured to output JavaScript files into this folder.
