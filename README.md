# publish-qb-code-page
Publish a Quickbase code page to a Quickbase realm

### Example workflow

```yaml
name: Update Code Page

on: push

    # Runs a set of commands using the runners shell
    - name: Run publish code page
      uses: deryck1228/publish-qb-code-page@v1.4
      with:
        realm: 'realm.quickbase.com'
        dbid: 'br844uajz'
        usertoken: ${{ secrets.usertoken }}
        path: ${{ github.workspace }}
        filename: codepage.html
        pageid: 20
```
