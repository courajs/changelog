1.0.27 / 2011-08-24
===================

  * v1.0.27
  * isRetry needs to be passed to cacheAddPublish
  * Fixes [#1285](https://github.com/isaacs/npm/issues/1285) Run prepublish *before* adding to
    cache
  * Fix [#1302](https://github.com/isaacs/npm/issues/1302) Clear out the json cache on unbuild
  * Spit out all usages when --long is set
  * Don't deref undefined command names
  * Allow calling camelCase or css-case for commands
  * Add Conny
  * Avoid git going "error: RPC failed; result=22, HTTP code = 417"
  * If a non-writable stream is supplied to output, then die horribly
  * Use process.stdout/err if the stdoutFD or stderrFD is supplied
  * Don't swallow exceptions that are not properly loggable
    Since a throw due to an ini resolve error or as a result of a
    callback happening more than once usually indicates some kind of
    early termination error, it's best to just throw horribly
    in those cases.
  * Support using 'node npm.js blah'
  * Close [#1299](https://github.com/isaacs/npm/issues/1299) Don't catch silently
  * Don't make the first arg always an array.
  * Ensure that npm.commands functions always called with an args array
  * Call the cb to prefix, root, and bin with the printed value
  * Add user info to 'scripts' helpdoc
  * Fix [#1296](https://github.com/isaacs/npm/issues/1296) Better messaging on bad url configs
  * Add git url info
  * Close [#1284](https://github.com/isaacs/npm/issues/1284) Make EPIPE less noisy

1.0.26 / 2011-08-17
===================

  * v1.0.26
  * Preserve other members of command functions
  * Friendlier 'npm.install(foo)' for repl poking.
  * Fix [#1272](https://github.com/isaacs/npm/issues/1272) Better first-class citizenship for
    git urls
  * Re [#1269](https://github.com/isaacs/npm/issues/1269) Install into DESTDIR if set

1.0.25 / 2011-08-15
===================

  * Support removing non-existent users from package manatainer lists
  * Provide default cb if none supplied
    Make it much nicer to poke around on the repl.  The default
    callback function just dumps the data or error to stdout
    or stderr.
  * v1.0.25
  * Use the non-delta uri for inital search index build
  * Don't set agent:false if http2 is in use

1.0.24 / 2011-08-010
====================

  * v1.0.24
  * Force exit. Temporary workaround for Linux rimraf timeout issue.
    TODO: Fix properly.

1.0.23 / 2011-08-07
===================

  * update which (trivial)
  * debuggery
  * v1.0.23
  * Remove base64 module. Just use the Buffer directly
  * .js extensions on require() calls in npm.js
  * Abstract out 'which'
  * make doc
  * Remove minimatch.js, using dep now
  * Handle git+ urls in the name@url case
  * Close [#1225](https://github.com/isaacs/npm/issues/1225) Add git url support. Experimental
  * unbreak ini stuff. no longer using '-' key
  * Use standalone ini parser
  * Add proto-list as dep and submodule
  * update rimraf
  * Allow private per-package confs
    Just prefix them with a _.  Transparent to the receiving module.
  * Use rimraf instead of local thing
  * fixup rimraf
  * Add rimraf submodule
  * minor faq fixes
  * Put .js on filenames
  * Question about Capitalization
  * Close [#1235](https://github.com/isaacs/npm/issues/1235) Swap out unicode tree chars
  * Better error handling for adduser
  * undefined log message error
  * Setting the host there is the wrong thing to do
  * Set host header explicitly
  * Clean up and refactor the oversized npm.load function
  * Close [#1214](https://github.com/isaacs/npm/issues/1214) Don't create an invalid engine range
  * newloctimeout should not be a global.
  * Revert "Check hostkey fingerprints when registry is https"
    This reverts commit ca52fe6045d6acf37597c66d30b5c2d490b07f79.
  * Check hostkey fingerprints when registry is https
  * Add a --yes config flag (with -y and -n shorthands)
  * Fix invalid array length when no search hits found
  * Confusion about args vs conf
  * Report 404 errors properly with non-vhosted registries
  * Closes [#1199](https://github.com/isaacs/npm/issues/1199) Support 'npm unpublish .'
  * Close [#1068](https://github.com/isaacs/npm/issues/1068) Add header to search output
  * Re [#1196](https://github.com/isaacs/npm/issues/1196) Warn on non-array 'files' in json
  * slide@1.1.3
  * Support npm_debug env in install script
  * Default prefix to PREFIX environ if set
  * No need to clean cache as often, makes search slow
  * Clearer messaging of cleanup prefix
  * Prefer https:// to git:// for github urls
  * Close [#1187](https://github.com/isaacs/npm/issues/1187) Use https:// for submodules instead
    of git://
  * Remove mkdir walk log, add cache.add install log

1.0.22 / 2011-07-24
===================

  * v1.0.22
  * Exit with the proper code on failure

1.0.21 / 2011-07-24
===================

  * v1.0.21
  * docs got messed up somehow
  * v1.0.20
  * doa bug, annoying.

1.0.19 / 2011-07-23
===================

  * v1.0.19
  * Close [#1175](https://github.com/isaacs/npm/issues/1175) Add --production flag
  * Better checks for proper gid/uid in mkdir
  * Add a bunch of logging and commentary for [#1153](https://github.com/isaacs/npm/issues/1153)
  * Update semver to 1.0.9
  * s/sys/util/g finally
  * remove async-map file
  * Use asyncMap from slide module
  * Use chain function from slide module
  * Add slide as dep
  * Abstract out graceful-fs
  * Add Felix Geisendörfer
  * Add tildes for >=0.1.0, not 1.0.0
  * Only use tilde range descriptor when package >=1.0
    Problem: When using `install --save`, npm prefixed the installed
    package version with the tilde range descriptor. This makes sense
    for packages that follow semver and have reached 1.0.0. But for
    packages < 1.0.0 semver allows APIs to change freely, so those
    should be packaged with the exact version that was installed,
    as implemented by this patch.
