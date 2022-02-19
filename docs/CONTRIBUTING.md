# Contributing to PHOCKHEADS
The PHOCKHEADS project operates an open contributor model where anyone is welcome to contribute their artwork.

## Getting Started
New artists are very welcome!

Before you start contributing, familiarize yourself with the project's [conventions](https://github.com/phockheads/phockheads/wiki/How-to-contribute).

If you have more questions please join us on Telegram: [https://t.me/PHOCKHEADS](https://t.me/PHOCKHEADS)

## Contributor Workflow
Once your artwork has been minted on Counterparty, you may create a patch (pull request) in the repository. 

*Note: Please **do NOT** create pull requests for assets that haven't been minted yet!*

To contribute a patch, the workflow is as follows:

* Fork repository ([only for the first time](https://docs.github.com/en/get-started/quickstart/fork-a-repo))
* Create topic branch
* Commit patches

For more information on how to contribute on GitHub [follow this guide](https://www.dataschool.io/how-to-contribute-on-github/).

## Add your phockheads series
To add your artwork to the respository, you only need to create a single file. The system will build the website automatically. 

The file with your phochkheads should be named as `<grail card name goes here>.md` and has to be saved in `_series` folder, eg: `_series/trollphocks.md`.

The file uses `YAML` syntax, so please make sure all the indentations are correct, otherwise the system will fail to build it.

The content of the newly created file should be as follows:

```yaml
---
name: <Grail card name (e.g. TROLLPHOCKS)>
author: <Your name or nickname>
image: <link to assets image>
date: YYYY-MM-DD # Mint date
description: <A short description of the series>
subs: 
  - 
    name: <subasset name 1 (e.g. TROLOLOLO)>
    image: <subasset image 1>
    supply: <subasset supply 1>
  - 
    name: <subasset name 2 (e.g. TROLLFACE)>
    image: <subasset image 2>
    supply: <subasset supply 2>

# Do NOT edit beyond here
layout: series
---
```

If you have any doubts, please refer to [_series/phocks.md](https://raw.githubusercontent.com/phockheads/phockheads/main/docs/_series/phocks.md) as an example.

Commit and push the changes to your repository and create a pull request in the main repo.

### Generate enhanced asset information (optional)
You can generate a json file that contains enhanced asset information for your grail card on xchain.io ([example](https://xchain.io/asset/phocks)).

Create a file called `<your grail card name goes here>.md` in `xchain` directory (eg. `xchain/trollphocks.md`) with the following content:

```yaml
---
layout: xchain
---
```

The system will then automatically build a json file on: 
`https://phockheads.com/xchain/<your grail card name goes here>.json` ([example](https://phockheads.com/xchain/phocks.json))

Open your Counterparty wallet (such as FreeWallet), and edit the description of your grail card so that it contains the above link.

![Change token description](assets/change-description.png)

# Crash course on using git
The following are basic git commands to get you started.

### Set up repository
These steps are only done once.

Clone repo:
```sh
git clone https://github.com/<github username>/phockheads.git
cd phockheads/docs
```

Add remote repo to your config:
```sh
git add upstream https://github.com/phockheads/phockheads.git
```

Check that it's been added:
```sh
git remote -v
```

### Sync with the main repository
Before commiting and pushing subsequent changes, it's best to update your repository from the parent one, although not required if you only make changes to your phockheads file. 

*Note: You can skip this step in the case you just forked the main repository.*

Fetch changes: 
```sh
git fetch upstream
```

In the case there are remote changes, you will need to merge and push them to your repository. If there are no changes you can skip theste steps.

```sh
git checkout main
git merge upstream/main
git push origin
```

### Create a new branch
It is best to make changes in a separate branch outside of main. For each change, you need to create a new branch named for example: *patch-1*, *patch-2* etc.

```sh
git checkout -b <the name of new branch goes here>
```

You can now start making your changes.

### Commit your changes
When you add or update your `_series/<grail card name goes here>.md` file, you need to commit and push the changes.

```sh
git add .
git commit -m "Add/Update <grail card name goes here>"
git push origin
```

### Create a PR
Go to the [main repository](https://github.com/phockheads/phockheads.git). It should automatically provide you with a "create new PR" button. 

If you're not sure what to do, please refer to [this guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).