# academic-org-theme

This is a Jekyll Theme for creating website for academic conferences, groups, and organisations. Having an advanced blog layout page, a complicated landing page, or providing lots of "profile"-style social media links is less important than providing clear and consistent pages.

This theme started out from a basic theme I developed for [my homepage](https://charlesmartin.au), and then for the [NIME community](https://nime.org).

## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "academic-org-theme"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: academic-org-theme
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install academic-org-theme

## Usage

TODO: Write usage instructions here. Describe your available layouts, includes, sass and/or assets.

The theme uses [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag/) to provide metadata in the page headers, you may want to look at the [usage](https://github.com/jekyll/jekyll-seo-tag/blob/master/docs/usage.md) page for that plugin.

```bash
bundle exec jekyll serve
```

## Building for deployment

To build the solution for deployment on the production website **nime2026** you have to execute this script, while on the `develop` branch

```bash
bundle exec jekyll build --config _config.prod.yml
```

This will generate the content on the `_site` directory which should be moved or copied to the root directory of the **nime26** repo, which should always be on the `gh-pages` branch. 

To make sure this works flawlessly, I usually first clean all the content in the root directory of the **nime26 repo**, commit and push, to make sure this triggers a change in the GitHub server. Only then do I move the content from nime26-staging. 

## Developing with concurrent Git branches

If we are using concurrent Git branches, the cleaner approach is to work on your own branch, pull/merge from develop regularly, if there’s a csv conflict, resolve the conflict in the file, commit the resolved version, merge the branch back when ready.

As usual, branches don’t eliminate csv conflicts, they make the conflicts visible and reviewable instead of silently overwriting each other’s work.

The critical files here are the database files `proceedings.csv` and `sessions.yml` in the `_data` directory. To coordinate better who is editing the `proceedings.csv` file, I recommend developers to take turns in editing the file in their own branch and give notice to the other when they do so, before they merge their branch into `develop`. They next developer must pull the latest from the origin into `develop` and merge the last state of `develop` onto their branch before making changes, and resolve all the conflicts locally. 

Deleting a file to solve conflicts is side stepping the Git methodology, and can lead to problems.  


## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/smcclab/academic-org-theme. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](https://www.contributor-covenant.org/) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `academic-org-theme.gemspec` accordingly.

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
