# bats-all-package

## What is it

It's just bats with all modules packed together:
* bats-core (https://github.com/bats-core/bats-core)
* bats-support (https://github.com/bats-core/bats-support)
* bats-assert (https://github.com/bats-core/bats-assert)
* bats-file (https://github.com/bats-core/bats-file)

## Why this

I often use bats for my projects to run it in docker against different linux distros.
* Some linux distros includes ready to use bats-core but not modules that are very useful for real world cases.
* Some linux distros includes outdated bats-core but I want to use the latest one.
* bats's contrubutor suggest to install bats via npm (https://www.npmjs.com/package/bats)... But
  * for me it overkilling.
  * there are not assert nad file modules there.
* bat's contribotor suggest to install to get bats and submodules via git submodule (https://bats-core.readthedocs.io/en/stable/tutorial.html#quick-installation). But for me it's hard to using it in the in-house infrastructure.

So I wanted to get a ready-to-use package with the core and modules included.

# Develop

## Build (pack)

## Tests

Will add in the future

# Using

Here steps for *nix. Need to make some changes for Windows.

* Download archive from from 'release' page (change 'tag_version' with latest tag).
  ```
  curl https://github.com/risik/bats-all-package/archive/refs/tags/${tag_version}.tar.gz
  ```
* Unpack where you want (for example to the `/usr/local/lib`)
  ```
  tar -xzf 
  ```
* Add bats' `bin` directoory to the `PATH` env var (optional... you may just run bats by absolute path instead)
  ```
  PATH=${PATH}:/usr/local/lib/bats/bin
  ```
* Set `BATS_LIB_PATH` env var to your base directory where you unpack bats-all package.
  ```
  BATS_LIB_PATH=/usr/local/lib
  ```
* Run bats to test your app.
  ```
  bats --tap mytest
  ```
