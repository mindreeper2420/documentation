# Travis CI
Travis CI configuration file examples.

## Ruby
Using Ruby as the base language: [travis-ruby.yaml](https://github.com/mindreeper2420/documentation/blob/master/travis-ci/travis-ruby.yml)
```yaml
language: ruby
cache: bundler
rvm:
  - 2.6.3
before_install:
- bundle install
- npm install
- npm install gulp-cli -g
script:
- gulp deploy
install: true
deploy:
  provider: pages
  skip_cleanup: true
  local_dir: docs
  github_token: $GH_TOKEN  # Set in the settings page of your repository, as a secure variable
  keep_history: true
  target_branch: gh-pages
  on:
    branch: master
```
