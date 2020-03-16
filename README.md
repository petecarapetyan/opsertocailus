# opsertocailus
an experiment in directory structures to accommodate various friends and competing concerns.

## Rationale:

If your starter kit doesn't include every edge case project - then you're going to end up with a bunch of `creativity`. Which, in this case is a euphemism for every like project is different even when - uh - maybe it's really not. 

Like, I'll put my images in `/src/ui/pics` and you put yours in `/lib/img` and he puts his in `/assets` ... no thanks.

That's not going to work, for me. When projects are different, they need to be different by which folders are missing because we didn't need them.


## Examples of different _types_ of UI projects we expect to be coding with this same starter kit:
- standard PWAs
- non-standard PWAs such as MPA
- standard static sites
- static sites built from prismic or other CMS inputs
- "micro-sites" wherever that dividing line is gawd help us 
- capsules - whatever that is other than a huge market that NW is already serving for years
- ad capsules - same as above except has google ad capsule wrapper
- embeds - similar to one of the above
- plenty of MVPs - amorphous apps that are really just barely started as working applications


## taken from:

ideas from many competing example projects

- rdx-example
- vp-starter
- npm init @open-wc March 15 version
- firebase init
- my old life as a java coder
- 11ty
- thinking about specific un-named future projects static sites, pwa, other
- linux (thanks Andy) https://www.howtogeek.com/117435/htg-explains-the-linux-directory-structure-explained/

## other uncongealed thoughts:

- I really don't like folders as groupings where naming conventions could work better - EXCEPT when you can have a VERY few folders. Like 5
- folders should always be short. There are only 5, so abbreviations are OK
- if you're going to settle on only 5 or so folders, and always keep them universal, you better be pretty well thought out on those
- if you have to change the folders because of the type or use case of project, that's OK for some but I'd rather not be in that group of humans that has to figure out what it all means. Just do it one way and be done with it, like Linux 
- if a folder is used for specific platforms but those platforms are not used on every project then we might have a problem. ie `public` vs `dist`
- naming conventions for sorting out large sets (especially as opposed to folders) 
- typical projects end up needing something such as an `assets` folders by any of a dozen names

## good uses for folders
- folders that are used to exclude focus - but only when few and can't be done with naming conventions
- when stuff inside the folder is truly alike - such as web components

## i know it's not conventional but can any of these be moved into /etc?
I find the number of config files that aggregate at the root of EVERY project extremely bothersome in my IDE. I wish we could stuff them all in an `etc` folder and keep the root folder a bit cleaner. 5 straggler files in root is too much, any more is worse

- rollup.config.yada.js
- tsconfig.json
- workbox...
- custom-elements.json
- karma.conf.js
- 

## sometimes file type is enough:
- example: separate folders for different types of media? 
- maybe not: same folder, because .mpg and .png are good enough to keep things organized
- this is especially true when an artifact is not accessed for daily changes, like a Web Component

## Typescript
- is it OK to just assume that everything is typescript? Yes for a company, no for something else like OWC which we are not
- if we are typescript you can just have one file for every wc
- 

## Naming Conventions
- prefixes are key for Web Component naming conventions: i. e. page-some-thing to keep all pages in one group
