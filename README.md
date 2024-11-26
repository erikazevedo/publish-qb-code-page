# publish-qb-code-page
Publish a Quickbase code page to a Quickbase realm. In this fork we remove the checkout step to allow publishing files created by previous steps. This means a checkout must be run before running this step or the file will not exist.

### Example basic workflow

```yaml
on:
  push:
    branches:
    - main
jobs:
  qbpush:
    name: Push to Quickbase
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Publish Code Page to Quickbase
        uses: erikazevedo/publish-qb-code-page@v0.5.1
        with:
          # The Quickbase realm, i.e. realm.quickbase.com
            realm: realm.quickbase.com
            # The main dbid, or appid, of the realm
            dbid: br844uajz
            # A valid usertoken with rights to create a code page
            usertoken: ${{ secrets.usertoken }}
            # The repository filepath of the code page
            path: ${{ github.workspace }}
            # The filename of the code page, with extension
            filename: index.html
            # The page ID of the code page
            pageid: 5
```
