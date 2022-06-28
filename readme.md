# markelliot/autosquash@v1

This action enables automatic squash commits on pull requests when the repository has 'automatic merging' enabled.

To add this action use the following workflow:

```yaml
name: autosquash
on:
  pull_request:
    types:
      - opened
      - synchronized
      - reopened
      - edited
      - labeled
      - unlabeled
      - ready_for_review
jobs:
  autosquash:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: markelliot/autosquash@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          pull-request: ${{ github.event.pull_request }}
```
