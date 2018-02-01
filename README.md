# Give.io API Documentation #

Repository of documentation for the Give.io REST API.

This project is based on [Slate](https://github.com/tripit/slate).

## Adding to the Documentation

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

```shell
# clone repo
git clone https://github.com/DevinWalker/give-io-documentation documentation
cd documentation

# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at [http://localhost:4567](http://localhost:4567).
