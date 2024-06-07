# koka-community
A meta repository containing all the goodies in one clone :)

Just clone this repository using the following commands:
```bash
git clone git@github.com:koka-community/koka-community
cd koka-community
git submodule update --init --recursive --depth=1
git submodule foreach 'git checkout main'
```

Run the following command to update all the submodules to the latest commit on the `main` branch:
```bash
git submodule update --remote
```

Most often you will want to open a `.code-workspace` file to open only the relevant folders and submodules you want to work with in vscode.
Due to the `--depth=1` flag in the update, you shouldn't have to worry about the size hopefully since it will only fetch the latest commit to work off of.

We have the following workspaces:
- admin - Contains the admin related repositories (community-docs, koka-docs, template, and `std` library)
- pure-koka - Contains the pure Koka libraries (`std`, `parsing`, `math`, `html`, `samples`, `rosetta`, `benchmarks-game` etc)
- generators - Contains code generators for the Alex Lexer as well as native (`C`) and web (`JS`) external binding generators.
- cbindings - Contains the Native code binding generator for `C` along with libraries that have been generated from C header files using it (`zlib`, `mbedtls`, `llhttp`)

`.vscode/settings.json` contains the configuration for koka's language server compiler arguments to use the submodules as include paths, 
for the whole `koka-community` repository. 
Each smaller workspace includes the workspace settings in their own `.code-workspace` file.

`language-koka*.vsix` is a development version of the koka language server extension for vscode. There are some updates that fix a few issues.

We set up a shallow clone for each of the submodules, so all of the remote branches and history won't be cloned to your computer when you clone this repo, just the latest code. If you want to fetch other branches do the following in the submodule you are working in:
```bash
git remote set-branches origin '*'
git fetch -v --depth=1
```
This will fetch the missing remote branches.
