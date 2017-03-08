require 'shortcake'

use 'cake-test'
use 'cake-publish'
use 'cake-version'


option '-b', '--browser [browser]', 'browser to use for tests'
option '-g', '--grep [filter]',     'test filter'
option '-t', '--test [test]',       'specify test to run'
option '-v', '--verbose',           'enable verbose test logging'

task 'clean', 'clean project', ->
  exec 'rm -rf dist'

task 'build', 'build project', ->
  # babel    = require 'rollup-plugin-babel'
  handroll = require 'handroll'

  bundle = yield handroll.bundle
    entry:     'src/index.coffee'
    external:  true
    sourceMap: true
    # use: [
    #  babel runtimeHelpers: true
    # ]

  yield bundle.write format: 'cjs'
  yield bundle.write format: 'es'

task 'watch', 'watch project', ->
  build = (filename) ->
    console.log filename, 'modified, rebuilding'
    invoke 'build' if not running 'build'
  watch 'src/*.coffee', build
  watch 'node_modules/', build, watchSymlink: true
