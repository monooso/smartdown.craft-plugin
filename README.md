# Smartdown for Craft #

[![Build Status](https://travis-ci.org/experience/smartdown.craft-plugin.svg?branch=master)](https://travis-ci.org/experience/smartdown.craft-plugin)

Smartdown for Craft is a Twig Filter which brings the unbridled joy of [Markdown Extra][md_extra] and [SmartyPants][smartypants] to [Craft][craft].

[craft]:https://craftcms.com
[md_extra]:https://michelf.ca/projects/php-markdown/
[smartypants]:https://michelf.ca/projects/php-smartypants/

Craft already supports standard Markdown, but sadly standard Markdown doesn't support lots of useful things such as footnotes, fenced code blocks, and tables. It also does nothing to spruce up your typography, leaving your site with an embarrassment of straight quotes, and faux ellipses.

Smartdown plugs both of these gaps, turning your website into a typographic dreamboat.

## Requirements ##
Each release of Smartdown is [automatically tested][travis] against PHP 7.1 and above. It's also manually tested on the most recent version of Craft.

[travis]: https://travis-ci.org/experience/smartdown.craft-plugin "See the Smartdown build status on Travis CI"

### PHP 7.0 support ###
In theory, Smartdown _should_ be compatible with PHP 7.0. In practise, it's impossible to test this, because the Codeception dependency tree includes components which only work with PHP 7.1+.

Unfortunately there's nothing we can do about that.

## Installation ##
To install Smartdown, either search for "Smartdown" in the Craft Plugin Store, or add it as a [Composer][composer] dependency.

[composer]: https://getcomposer.org "Composer is a PHP dependency manager"

Here's how to install Smartdown using Composer.

1. Open your terminal, and navigate to your Craft project:

        cd /path/to/project

2. Add Smartdown as a project dependency:

        composer require experience/smartdown

3. In the Control Panel, go to "Settings → Plugins", and click the "Install" button for Smartdown

## Basic usage ##
Use the Smartdown filter in exactly the same way as any other Twig filter.

    {{ myVariable|smartdown }}

This will parse your content with both Markdown Extra, and SmartyPants, turning this:

    "Outside of a dog, a book is a man's best friend. Inside a dog it's too dark to read..."

Into this:

> "Outside of a dog, a book is a man's best friend. Inside a dog it's too dark to read..."

## Filter parameters ##

### markup ###
The `markup` filter parameter controls whether the text will be parsed using Markdown Extra. The default value is `true`.

Example usage:

    {{ content|smartdown(markup=false) }}

### typography ###
The `typography` filter parameter controls whether the text will be parsed using SmartyPants. The default value is `true`.

Example usage:

    {{ content|smartdown(typography=false) }}
