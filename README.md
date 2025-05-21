# GHPages-CrashTestDummy

## Setup

1. Install Ruby:
    ```
    winget install "Ruby 3.4 with MSYS2"
    ```
1. install gem packages
    ```
    gem install bundler jekyll
    ```
1. create site (force only required if readme file present)
    ```
    jekyll new . --force
    ```
1. ensure everything certain packages are the right version for local preview by editing `gemfile`
    ```ruby
    # gem "jekyll", "~> 3.9.3"
    gem "github-pages", group: :jekyll_plugins
    gem "csv"
    gem "webrick"
    ```
1. (optional) change remote theme by editing `gemfile`
    - `gemfile`:
        ```ruby
        remote-theme:
        group :jekyll_plugins do
            gem "jekyll-feed", "~> 0.12"
            gem "jekyll-remote-theme"
        end
        ```
    - `_config.yml`:
        ```yml
        #theme: minima
        remote_theme: pages-themes/architect@v0.2.0
        plugins:
        - jekyll-feed
        - jekyll-remote-theme
        ```
1. install bundle gems locally
    ```
    bundle install
    ```
1. run the site
    ```
    bundle exec jekyll serve
    ```