LSU Phoenix Alumni Association
==============================

Source code for the Phoenix Chapter of the LSU Alumni Association's website.

## High-level Info

This site is hosted on GitHub Pages. It is a Jekyll site and is automatically generated and deployed from the `master` branch.

This site makes heavy use of Markdown. If you are unfamiliar with it, you should check out GitHub's [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) article. You will need to be comfortable with it, but fortunately it's quite easy to pick up.

## Installing

To get the site to run locally, you need a few things installed on your system:

- Ruby (should come standard)
- [Jekyll](http://jekyllrb.com) - `gem install jekyll`

Clone the repo, install dependencies, then run a local server:

```sh
git clone git@github.com:mmcbride1007/lsu-phoenix-alumni.git
jekyll serve
```

## Updating

There are a few different areas for updates, so depending what you need to change, find the appropriate section below.

### General

After all changes have been made, regardless of what you've changed, you can commit your changes and push the site up to GitHub, where it will be deployed automatically using GitHub Pages:

```sh
git add .
git commit -am 'some changes'
git push
```

**NOTE:** Be careful, when you run this, your changes will go live immediately. Make sure it all works on your machine before running this! You may want to consider using branches and the Pull Request features of GitHub.

### Announcements

The six most recent announcements will be shown on the home page, all others will be on the Announcements page. If you want to add a new announcement, all you need to do is create a file in the `_announcements` directory. The file should be a Markdown file (`.md`). Jekyll uses YAML front-matter to store data. You can read about it on their website if you want. For a new announcement, you will need the following front-matter:

```yml
---
title: "My Announcement Title"
date: 2016-12-04
---
```

The title and date will show on the home page. The date is the date that you are posting the announcement. The content below the triple-dash block (front-matter) will be the content of your announcement. Name your file whatever you'd like, but I suggest just using the title with hyphens or something similar to make it easy on yourself.

#### Deleting Old Announcements

Announcement out of date? Just delete the file and commit your changes.

### Events

Like announcements, events are Markdown files that you put in the `_events` directory. Events will show up both on the home page (it will automatically take the 6 most recent) and on the Events page (all events will show). You will need a little more data in the front-matter for events, since they can link to longer posts. Check out the example below:

```yml
---
layout: event
title: Crawfish Boil
date: 2016-09-17 13:00:00
excerpt: Join us for our annual crawfish boil on Saturday, September 17 starting at 11:00am!
venue:
  name: Old Town Gringos Restaurant & Bar
  address: 4209 N Craftsman Ct, Scottsdale, AZ 85251
  phone: (480) 423-3800
  locationUrl: https://goo.gl/maps/Wxj53jm56gw
---
```

Some important things to note about that:
- The `date` is the date of the event, not the date that you post it on the site, unlike an announcement.
- You MUST include `layout: event` in the front-matter for the page to render properly when clicking to view event details.
- `excerpt` is just a brief snippet about the event to let people know what's going on.
- The `venue` object is not required. If present, it will attempt to display as many properties as possible. The example above shows all available properties.
- `locationUrl` is not required - you could put the location as plain text in your post, and that would be fine. If you use this YML property, it should be a Google Maps URL. The easiest way is to go to [Google Maps](https://google.com/maps), find your location, click the "Share" button, and copy the URL. I recommend checking the box that says "Short URL" simply because it's less clutter, but either one works just fine.

Like announcements, the content of the post will be below the front-matter. You will use Markdown to write event info. However, you will only see the excerpt on the home page. All other event details will be on the detail page (when you click "more" from the homepage or click the event title on the Events page). This is where you will see the location info as well.