# Bundler behavior POC

This repo is meant to demonstrate a strange behavior in bundler when multiple gems from the same git source. 

This repo contains three different gems: `base_gem`, `some_gem`, and `multiple_dependency`. The first two have no dependencies and a single dependency respectively. The behavior is highlighted in the third use case where we want to include both `base_gem` and `some_gem` as dependencies. 

## Steps to reproduce:
1. `$ cd gems/multiple_dependencies`
1. `$ bundle install`

## Output
```
Fetching git@github.com:ajorgensen/bundler-poc.git
Fetching gem metadata from https://rubygems.org/
Could not find gem 'base_gem' in git@github.com:ajorgensen/bundler-poc.git (at master@002e6fd).
The source does not contain any versions of 'base_gem'
```

## Expected output
A successful output from `bundle install`