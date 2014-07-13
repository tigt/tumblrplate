tumblrplate
========================

A boilerplate template for powerful, fast Tumblr themes, where the style is up to you.

tumblrplate owes an obvious, significant debt to [HTML5 Boilerplate](http://html5boilerplate.com/), and it heavily lifts from [normalize.css](http://necolas.github.io/normalize.css/) as well. Proper in-project attribution with source links will follow once the structure starts making sense.

##Notable exclusions

The tumblrplate at first appears like it's neglecting some critical code. The unique nature of the Tumblr ecosystem and infrastructure adds some wrinkles to typical front-end coding.

###Doctype

Tumblr automatically slaps `<!DOCTYPE html>` at the start of every page served, whether you specified one or not. This seems to be a security thing; it also prepends the text for its anti-phishing warning immediately afterward, in order to load it as soon as possible.

As such, specifying a doctype in your Tumblr theme is a waste of bytes. Notably, the [official Optica theme](https://www.tumblr.com/theme/37310) is guilty of this, so it's possible I'm missing something.

###Charset encoding

Tumblr already specifies UTF-8 in its server headers, which always trump a meta specification. This tumblr-wide standard is presumably for XSS prevention and to protect against any malformed charsets.

Optica also specifies UTF-8 again in its meta tags, so I wonder if they know something I don't.

###X-UA-Compatible

Similarly, Tumblr's server headers specify IE=Edge and Chrome=1 automatically.

##Notable changes

Tumblr refrains from injecting some code if it sees you already have it.

###Open Graph tags

Tumblr's automatic OG tags promote Tumblr itself, especially its apps. Nothing wrong with that, but having them promote your users' blogs is a selling point if I ever heard one.

It's possible to mostly disable them by specifying empty OG Name & URL tags, but that ends up being spectacularly nonfunctional.

###Twitter Cards

Same deal as Open Graph. Psuedo-disabling them isn't quite as worrisome as that, since Twitter is known to fall back on OG tags. However, I'm not sure if malformed Twitter tags prevent that fallback. To be safe, the same blog-central treatment is used.

##Notable additions

Of course, 5 tweaks does not a boilerplate make. Here's what tumblrplate proposes as a good standard:

###<html> lang attribute

Using Tumblr's language selection blocks, tumblrplate will automatically insert the correct language code into your pages' language attribute. If your language isn't supported, or you wish to override this behavior, there's a text field labeled ISO Language Code for you to insert the correct value.

###DNS Prefetch

By default, Tumblr inserts a DNS prefetch meta tag explicitly disallowing it. My guess is that this prevents browsers from prefetching what they assume are different subdomains, but in actuality are just long reblog chains of conversations between tumblr users with the same IP.

However, the disallow tag only turns off the default behavior of prefetching arbitrary links on the page, so if we want to specifically target some URLs, we can. I've added `secure.asssets.tumblr.com` and `static.tumblr.com`; both near-universal subdomains for Tumblr blogs, as they host the images, fonts, scripts, and other files that make up Tumblr themes and infrastructure. `assets.tumblr.com` is not included, as tumblr automatically serves a script hosted there as the first thing on any blog page.

==========

Of course, more to come.
