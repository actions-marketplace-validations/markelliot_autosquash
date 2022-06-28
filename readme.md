markelliot/autosquash@v1
========================
This action enables automatic squash commits on pull requests when the repository has 'automatic merging' enabled.

To add this action use the following workflow:
```yaml
name: autosquash
on:
  pull_request_target:
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
    - uses: markelliot/autosquash@v1
```
