# Whitespace Linter

## Usage
Comment `/wslint` in Pull requests tab to trigger auto linter.

## Installation
```
name: Whitespace linter

on:
  issue_comment:
    types: [created]

jobs:
  whitespace_lint:
    runs-on: ubuntu-latest
    if: contains(github.event.comment.body, '/wslint')
    steps:
    - uses: actions/checkout@v2
    - name: Whitespace linter
      uses: hexrabbit/whitespace-lint@v0.0.1
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
```
