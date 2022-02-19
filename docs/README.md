# PHOCKHEADS.com
Source for phockheads.com website.

## What is Phockheads?
PHOCKHEADS is a parody of Namecoin's BLOCKHEADS on Bitcoin's counterparty.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).

## Installation
The website runs on top jekyll and github pages. 

### Prerequisites
Before you can start you need to install [Ruby and jekyll](https://jekyllrb.com/docs/installation/).

### Setup and run
Clone the repo, install bundles and run the project:

*Note: If you're setting up the project in order to contribute your own tokens, please follow the [CONTRIBUTING.md](CONTRIBUTING.md) section instead. You will need to fork the project instead of running it from this repository.*

```sh
git clone https://github.com/phockheads/phockheads.git
cd phockheads/docs
```

To test everything displays correctly make sure you are in the `docs` folder and run:
```sh
bundle
bundle exec jekyll server
```

Open the website on http://localhost:4000

