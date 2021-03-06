# Adding a New Page

Note: usage of a staging environment is **strongly** encouraged. See [CONTRIBUTING.md](.github/CONTRIBUTING.md) for instructions.

* Create a new file in the root directory with the name `some-new-file.md`.
* Make sure the file starts with YAML front matter:

  ```yaml
  ---
  layout: default
  title: Some New File
  author: John Doe
  ---
  ```
* Add an entry in `_data/navbar_links.md` with a `url` and `text`
  attribute to make the link show up in the navbar header:
  * `url` will correspond to the `href` of the link, and should be relative to
    the root of the website (specifically, relative to `site.baseurl`)
  * `text` will correspond to the text of the link that will be created
  * the order of the entries determines the order of the links in the navbar

  ```yaml
  - url: /some-new-file
    text: new file
  ```

# Running the Website Locally

## Setting Up

Install Ruby and RubyGems; then install `bundler` and dependencies:
~~~
gem install bundler && bundle install --binstubs
~~~

## Development

To build static assets and serve the website:
~~~
./bin/jekyll serve --host=0.0.0.0
~~~

Add the `--watch` and `--incremental` flag to rebuild the website as you modify files (note: you *must* manually rebuild the website if you change `_config.yml`; jekyll does not support automatic reloading on configuration changes):
~~~
./bin/jekyll serve --host=0.0.0.0 --watch
~~~
