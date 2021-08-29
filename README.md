# setup-swift-windows

with this actions, you can setup Swift environment in `Windows-*` runner of GitHub Actions.

Based on @compnerd's [install-swift action in swift-win32 repository](https://github.com/compnerd/swift-win32/blob/2f7c0b91e031fe3dc676042c3a429052e27f9969/.github/actions/install-swift/action.yml), but I added installer's cache, that makes faster to install and saves bandwidth of swift.org.

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
