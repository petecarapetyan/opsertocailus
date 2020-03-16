# opsertocailus
an experiment in directory structures to accommodate various friends and competing concerns.

## Rationale:

If your starter kit doesn't include every edge case project - then you're going to end up with a bunch of `creativity`. Which, in this case is a euphemism for every like project is different even when - uh - maybe it's really not. 

Like, I'll put my images in `/src/ui/pics` and you put yours in `/lib/img` and he puts his in `/assets` ... no thanks.

That's not going to work, for me. When projects are different, they need to be **different by which folders are missing** because we didn't need them.


## Examples of different _types_ of UI projects we expect to be coding with this same starter kit:
- standard PWAs
- non-standard PWAs such as MPA
- standard static sites
- static sites built from prismic or other CMS inputs
- static sites generated from an SSG such as 11ty
- "micro-sites" wherever that dividing line is gawd help us 
- capsules - whatever that is other than a huge market that NW is already serving for years
- ad capsules - same as above except has google ad capsule wrapper
- embeds - similar to one of the above except designed to fit inside another site
- plenty of MVPs - amorphous apps that are really just barely started as working applications

## Examples of fundamental stack differences:
- might be deployed to firebase hosting
- might be deployed to netlify
- might be deployed to AWS and then a coding
- might consume any of several authentication/authorization systems
- might consume any of several REST API or even GraphQL
- might use any of several combinations of white-label or styling approaches

## Stacks that might not be so different between projects:
- Default Typescript where JS is required
- accept js where TS not appropriate
- if dynamic SPA/PWA then Lit, service worker, rollup, redux(ugh) etc

## taken from:

ideas from many competing example projects

- rdx-example
- vp-starter
- npm init @open-wc March 15 version
- firebase init
- my old life as a java coder
- 11ty kind of projects
- thinking about specific un-named future projects static sites, pwa, other
- linux (thanks Andy) https://www.howtogeek.com/117435/htg-explains-the-linux-directory-structure-explained/

## other uncongealed thoughts:

- I watched one project become almost incoherent when different folders were used for components. See below:
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

## Expanded src?
Java works on a slightly different standard:

- `src/java/whatever`
- `src/test/whatever`

If we did that, it might be OK but is slightly non-standard in the UI community? Would that be offputting?

Also what about stories???
- `/stories/`
- `/src/...`

or ? This might clean up the root but now we're _really_ non-standard in the JS community?

- `/src/stories/`
- `/src/js/`
- `/src/test/`

## Long stories about projeect where different folders were used - bookmarks, components

##### Bookmarks

My bookmarks folders are a complete nightmare - because of folders. They all start out perfectly, of course.

But then I start getting folders on PWAs and JS and apps and UI and various aspects of development that I am also concerned about.

What i discover is that the categories start morphing over the years, and what I thought was interesting about an article because it was about JS ends up being a PWA issue. Or was it an SPA issue. So how do I even look for it? Every folder gets all jumbled and cross-purpose, so I just give up before even looking, 90% of the time.

Tags would be a much better way for me to organize bookmarks. But you can't transfer that kind of thinking to files.

##### React Component Example: _True Story!_

in 2018-2019 we had this nightmare project with seemingly hundreds of pages and subpages and views and grids and sections and specialty widgets like rows and row headings and ... on and on. It was a designer's wet dream - everything was special and creative and it's own really cool component. It started out huge, and then doubled, etc. And it was all React components, inside React components, inside more React components.

It was a perfect nightmare for proving out how many ways folders can lead us astray while trying to help us.

At first, it went perfecly logically - since it was components inside components inside components the folders were simply arranged the same way. Genius! 

But then, the one widget inside another component gets used also inside this component. Hmmm. Can you guess what happened? Yup! Rather than re-use the component, they copy pasted the component into another folder in the new parent component structure! That was how many of the initial problems were solved! Else you would never even be able to find all your shared components. Now, all manner of tweaking and duplication of effort could occur, and nothing was truly re-used!

It didn't stop there. It got much worse - and most of it seemed highly correlated to trying to make the folder structure work.

A year into the project, you could tell that the developers were becoming dismayed by the proliferation of copy-paste junk that they had created. Again, they turned to folders for the solution. But this time, they started experimenting with entirely _**new**_ ways of organizing folders. It got really creative. Now, parts of the app were designed with the redux stores in the same folders and the React components that used them. Only once again, there was some unanticipated cross folder sharing of redux behaviors, so that got really confusing really fast. It didn't help that we had so many "components" that were almost identical to other components, only not. So a whole tree of folders would again be copy-pasted and name-changed.

By mid 2019 the project seemed so tangled up I gave up on it and asked to be put on another project. My little pea sized brain was no longer capable of keeping up.

##### Java: folders as /src/java/com/corp/xyz/coolapp/thatpart/yofunction/whatever/yada/widget

One of the really cool features of the java world is it's massive size, so everyone started out following very rigid standards.

One of those very rigid standards was the above naming structure. Everyhing in java goes in folders like `/src/java/com/corp/xyz/coolapp/thatpart/yofunction/whatever/yada/widget` which does an amazing job of keeping things from stomping on each other. One problem solved.

The side effect of this solution is to create massive complex folder structures that you have to drill down through to get to anything. This has many advantages as well as disadvantages.

But if you do it for a couple of decades like myself, you really become aware of the disadvantages. A good IDE can really help, but we don't always have that same IDE in a js app.

##### Is there a lesson? What would it be?

What I have learned is that there are no perfect solutions, but every solution in turn tends to create it's own problems. 

So the only way out is to see, over time, which combinations of side effects are least troubling.

The most obvious nightmare scenario to solve for, in the current design - is the proliferation of WebComponents of highly variable complexity.

My guess is that the answer arrived at over time is going to be analogous to a `node_modules` folder. Highly imperfect in so very many ways, but good enough in most ways. 

But - and this is the most important part, from what I have unscientifically observed - the one thing that will never work is subsections such as `src/wc/views` or  `src/wc/widgets` or  `src/wc/yada` - just as there is no subsections of `node_modules/foo` or`node_modules/bar` or`node_modules/yada`.

This isn't because subsections of `node_modules/foo` or`node_modules/bar` or`node_modules/yada` would have been a bad thing - just that they would always be more misleading than not, over time. Sometimes a foo is also a bar, just less so, and only in certain circumstances. So do you put it in subsections of `node_modules/foo` or`node_modules/bar`? Nah, just one horrible directlry. Nasty, but effecitive.
