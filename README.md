## Gitlab Trigger Action

### Inputs
endpoint - (Optional) Endpoint to Gitlab. e.g. https://gitlab.example.com. Leave blanc for default <br>
token - Your Gitlab token. Make sure token has rights to launch pipelines <br>
projectId - ProjectId of your pipeline repo <br>
envs - (Optional) Environment variables you want to pass to Gitlab <br>
ref - (Optional) Git branch of target pipeline repo

## Example
```yaml
name: Build

on:
  push:
    branches:
    - '*'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: qameta/gitlab-trigger@master
      with:
        token: ${{ secrets.GITLAB_TOKEN }}
        projectId: "154854"
        envs: VERSION=${{ steps.version.outputs.name }},ARCH=amd64
```
