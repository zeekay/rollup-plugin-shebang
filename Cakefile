require 'shortcake'

use 'cake-bundle'
use 'cake-outdated'
use 'cake-publish'
use 'cake-test'
use 'cake-version'

task 'clean', 'clean project', ->
  exec 'rm -rf lib'

task 'build', 'build project', ->
  bundle.write
    entry: 'src/index.coffee'
    compilers:
      coffee: version: 1

task 'watch', 'watch project', ->
  watch 'src/*.coffee', (filename) ->
    console.log filename, 'modified, rebuilding'
    invoke 'build' if not running 'build'
