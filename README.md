# Space Ghost

This ghost theme puts a heavy emphasis on tags and images. It features a large
hero taking up nearly the entire viewport and three tags on the homepage
immediately below the fold. All tags (including these featured ones) can have an
associated page which will appear above the tagged posts.

Live demo site coming soon.


## Usage
1. [Download](https://ghost.org/developers/) and setup Ghost
2. `cd /path/to/ghost/content/themes`
3. `git clone https://github.com/hbaughman/space-ghost`
4. Restart Ghost (if running) -- command differs based on your setup
5. Select the theme in Ghost's settings
6. Turn on "Public API" and "Internal Tags" in `Settings > Labs > Enable Beta
   Features` (If you don't see "Internal Tags" you probably have to upgrade to
   Ghost 0.9.0).
6. Create and publish a new Post
  - Check "Turn this post into a static page"
  - Set the "Post URL" (a.k.a. the slug) to `tags`
7. Add a link to `/tags` in your "Navigation" links


### Disqus Comments
1. Uncomment the line `{{!> disqus}}` in `post.hbs` (remove the `!`)
2. Setup your [disqus account](https://disqus.com/)
3. Replace `DISQUS-SHORT-NAME` in `partials/disqus.hbs` with your short name


## Conventions

### Projects

Tags work as per normal in Space Ghost, but can *optionally* have an associated
page which describes their function. This lets you post links, contact
information and any number of pictures. This page will appear above the tagged
posts when viewing the first page of the tag (e.g., on `/tag/family-history`,
but not on `/tag/family-history/page/2`).

To link a page to a tag you **must** enable the "Public API" and "Internal
tags". The associated page must follow these rules exactly:

- Have the internal tag "#project" ([internal tags are identified by the leading
  "#" symbol](http://support.ghost.org/internal-tags-beta/)).
- Be tagged with the target tag (obviously).
- Have "Turn this post into a static page" checked
- **Optional**: Check "Feature this post" to show it on the homepage. I
  recommend you limit yourself to three, though this is *not* enforced.

You *must* enable "Public API" (see "Usage") for project pages to appear. 

### Home Page

To add colored blocks to the homepage (see the example site), create static
pages with the tag "home". They will appear in reverse chronological order.


## Development
1. Fork the `dev` branch
2. Follow the steps in Usage to setup Ghost Scroll
3. `npm install -g gulp`
4. `npm install`
5. `gulp`
6. **Optional** Install the [livereload extension](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei?hl=en)
7. Modify JS and SASS in the `src` directory. Do not touch the contents of
   `assets/js` or `assets/css`, they are overwritten by the build process.
8. Submit a pull request

