# testRnBundleUpdate
tests of private update of RN apps

idea coming from the issue  : https://github.com/react-native-community/discussions-and-proposals/issues/536

 it is a "over the air update" but limited to Android. (for the moment)
 the aim is : 
 how and what to develop or use that exist to put inside the app and inside an API to do that feature described 
The limit is : once we have build with a stack (yarn add made and build made) it is only app code on that stack that can be modified with that tool, in fact similar with the dev process but in production with a code added in the code that ask for download and upgrade)

--------
We have to understand how :

  1.  generate a JS bundle
  2.  (so make a zip of it with app version if no package.json, zip of the app name, ending with a dedicated extention "prp" for ex.
  3.  write a process that with fetch the .prp package (easy) through an API (easy) and store it in dowload dir on Android, unzip it
  4.  install the JS bundle
  5.  restart the app or make it run with the new bundle.
----

----
as far as step 1 is concerned : 
bundle creation :
$ npx react-native bundle --entry-file index.js --platform "android" --minify "true" --bundle-output ./.bundle/bundle --sourcemap-output ./.bundle/map --assets-dest ./.bundle/assets
will create all the files under ./.bundle of the project

----
