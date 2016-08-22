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
6. Turn on "Public API" in `Settings > Labs > Enable Beta Features`
7. Add a link to `/tag/project` to your "Navigation" links
   9) on `Settings > General`


### Disqus Comments
1. Uncomment the line `{{!> disqus}}` in `post.hbs` (remove the `!`)
2. Setup your [disqus account](https://disqus.com/)
3. Replace `DISQUS-SHORT-NAME` in `partials/disqus.hbs` with your short name


## Conventions

### Projects

Tags work as per normal in Space Ghost, but can **optionally** have an associated
page which describes their function. This post will appear above the tagged
posts when viewing the first page of the tag (e.g., on `/tag/family-history`,
but not on `/tag/family-history/page/2`).

Associated pages must follow certain conventions:

- Have the tag "project"
- Have the tag they are associated with (e.g., "family-history")
- Have the "Post URL" (a.k.a. the slug) set to the same value as the tag (e.g.,
  "family-history")
- Check "Turn this post into a static page"
- **Optional**: Check "Feature this post" to show it on the homepage (max 3)

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

