# project-helix.io

Project Helix documentation site based on… Helix!

Check [www.project-helix.io](http://www.project-helix.io/index.html)... coming soon!

## Installation

Clone current repo and simply run `hlx up`.

If you want to see content from remote repository, run `git submodule init`

## Deploy

### Setup

Ensure that you have the correct environment variable defined.:

```
$ source secrets/helix.env
$ printenv  | fgrep HLX_
HLX_WSK_NAMESPACE=helix
HLX_WSK_AUTH=...
HLX_FASTLY_NAMESPACE=...
HLX_FASTLY_AUTH=...
```

If the `secrets/helix.env` is missing, you need to decrypt the first. 
We're using [blackbox](https://github.com/StackExchange/blackbox) to encrypt the secrets. Follow
the installation instructions if needed. 

Then run:

```
$ blackbox_decrypt_all_files
```

### Deploy

```bash
hlx deploy --default REPO_RAW_ROOT https://raw.githubusercontent.com --default REPO_API_ROOT https://api.github.com/
```

### Publish

```bash
hlx publish
```

