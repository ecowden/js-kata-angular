JavaScript Kata Template Project
================================

The goal of this project is to get you writing code as quickly as possible.

This is a pretty simple setup to do test first development with JavaScript using the Jasmine test framework and
the Testacular test runner.

Sugar.js is included for convenience.

This project is designed to be used with IntelliJ IDEA, though there's no reason that it shouldn't work with other
editors as well.

### Before starting
 1. Install [Node.js](http://nodejs.org/)
 1. Install [Testacular](http://vojtajina.github.com/testacular/).  We'll use this for running tests.

        npm install -g testacular

 1. Install [Bower](https://github.com/twitter/bower).  We'll use this for grabbing dependencies.

        npm install -g bower

### Set up the project
 1. Get the project.  The simplest way is to download the project as a zip archive from GitHub.  Advanced users are
    free to perform a git clone.  Really advanced users may want to create a fork.
 1. Open the project in your IDE of choice.  Everything should be set up already for IntelliJ IDEA users.
 1. Use Bower to grab dependencies.  For IntelliJ IDEA users,
    there is a build config for this.  For all others:

        bower install

 1. Verify the Bower install operation by checking for a 'components' directory in the project.  Inside it should be
    directories for both 'angular' and 'sugar.'  Some users have reported needing to run Bower twice the first
    time they use it.

### To start testing

One you start the Testacular runner, it should watch for changes and continuously run appropriate tests.

 * For IntelliJ IDEA users, run the "Testacular Start" run configuration.
 * Alternately, run:

        testacular start

### Troubleshooting

 1. I'm getting weird errors when I try to npm install anything.  Also, I'm on a *nix platform.

    You may need to invoke the command with sudo.  This should not happen on MacOS if you installed Node using Homebrew.

 1. I installed Testacular and Bower via NPM, but it can't find them when I run them.

    If you installed Node via Homebrew on MacOS, the NPM bin directory might not be on the path.  Try:

        sudo nano /etc/paths

    add /usr/local/share/npm/bin
    hit ctrl-x, then y to save and exit
    restart your terminal

 1. I'm getting errors when I try to start Testacular.

    By default, this project is configured to use PhantomJS as the test browser.  Either:
    * Install PhantomJS.  On MacOS with Homebrew:
          brew install phantomjs
    * - OR - edit testacular.conf.js.  Set the "browsers" element to the browser or browsers of your choice.

 1. I tried 'bower install,' but it didn't create a 'components' directory in my project.

    First, sometimes the IDE does not immediately pick up file changes that happen outside of it.  Check for the
    directory outside of the IDE using Finder/Explorer/Terminal/etc.

    Second, some users have reported that their very first 'bower install' doesn't work.  Try running it a second time,
    just in case.

### Notes for Posterity

1. We have configured Bower to grab Angular via the ZIP distribution provided by Google.  It would be nice if
   there were a good Bower repository for it, but, alas, there's a bunch that have different things, they're
   all out of date and none of them have the testing files.  As such, you'll need to update the
   version manually in the component.json file.