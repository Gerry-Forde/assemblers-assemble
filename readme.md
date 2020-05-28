# Test to see if we can use AsciiDoc Assemblies

Uses an assembly for a solution pattern, breaking up the text into other adoc files for easier re-use and management.

This technique allows you author modules for Solution Patterns, then assemble the `walkthrough.adoc` files for Solution Explorer in a build step.

## Prerequisites

* [Ruby](https://www.ruby-lang.org/en/documentation/installation/) installed locally (i.e. `sudo apt-get install ruby-full`)
* [Asciidoctor Ruby](https://asciidoctor-docs.netlify.app/) installed locally (i.e. `sudo gem install asciidoctor`)

## Procedure

1. Author your Solution Pattern using the following file naming convention:

* `walkthroughs/assembly-<walkthrough-name>.adoc` - contains the first level heading and includes.
* `walkthroughs/<file-name>.adoc` - contains the content for each module

2.  Run the following command in the root of your repo to render the appropriate `walkthrough.adoc` files:

```
make render
```

This command coalesces the `assembly-<walkthrough-name>.adoc` file with the includes and overwrites the `<walkthrough-name>/walkthrough.adoc` file.
