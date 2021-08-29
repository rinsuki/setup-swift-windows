# setup-swift-windows

with this actions, you can setup Swift environment in `Windows-*` runner of GitHub Actions.

Based on @compnerd's [comment on actions/virtual-environments#1652](https://github.com/actions/virtual-environments/issues/1652#issuecomment-735446611), but I added installer's cache, that makes faster to install and saves bandwidth of swift.org.

## How to use

:warning: You need to run `seanmiddleditch/gha-setup-vsdevenv` before `setup-swift-windows`.

```yaml
jobs:
  test:
    runs-on: Windows-latest
    steps:
    - uses: actions/checkout@v2
    - uses: seanmiddleditch/gha-setup-vsdevenv@8c6bbf80998779f2bba87b1452832e561b65fd57
    - name: Install Swift
      uses: rinsuki/setup-swift-windows
      with:
        version: "5.4.2"
    - name: Test
      run: swift test
```
