# koka-community
A meta repository containing all the goodies in one clone :)

Just clone this repository using the following commands:
```bash
git clone git@github.com:koka-community/koka-community
cd koka-community
git submodule update --init --recursive
```

`.vscode/settings.json` contains the configuration for koka's language server compiler arguments to use the submodules as include paths.
`language-koka*.vsix` is a development version of the koka language server extension for vscode. There are some updates that fix a few issues.