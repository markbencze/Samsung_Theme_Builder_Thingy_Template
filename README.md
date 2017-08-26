#Samsung theme Template Builder Thingy by Mark Bencze
Theme Template for Samsung 7.0 phones
![Alt text](/_app/src/main/res/drawable-xxxhdpi-v4/theme_preview_0.png?raw=true)

Step 1: import project into android studio
Step 2: allow Gradle to finish doing it's thing.  You'll notice a progress bar at the bottom doing stuff.  It may take a few minutes depending on your computer.
Step 3: on the left side of the page close to the top you'll see a "project" tab written vertically along with the android studio icon below it.  Click on that.  Then just to the right and
above it you will see an "Android" tab with a drop down menu.  Click the menu drop down and select "Project".  This may trigger gradle to do it's thing again.  If it does, let it finish.
Step 4: You will see "offical theme tool source" folder.  click on it to expand it.  This is what we're working with.  Do not worry about or touch "External Libraries"
Step 5: While you have "offical theme tool source" selected (highlighted) go to the edit tab at the top of the screen.
Step 6: Go to find, Replace in path and search for "com.yourname.themename".  Replace that with whatever you want to call it.  This should be self explanitory on the naming of it.
make sure in this pop up menu under scope that you have "whole project" selected and then press find.  This will change 675 files give or take.  you want to select "yes to all" when asked.
Step 7: In the folder _app/src/main you will find you AndroidManifest.xml.  Enter the name of your theme there.  You do not need to use an underscore _  You can use a space if you wish.

Now this next part is very important.  Failure to follow this will cause your theme to fail to work.  The manifest I have provided in the _apps folder has about 60 or so asset names.
So does the json.file and you'll also notice that you have the same amount of folders in this source.  All three of these must match.  For example: If you do not wish to use the asset
"touchwiz" in your theme, you must delete that reference carefully from the AndroidManifest, json.file as well as remove the folder from the source to the source.
The three things need to communicate and jive with each other and if you do not have them all in sync you will get an error during installation of the theme on your device saying in a toast
message "Master Package Not Formed Properly".  So if you get this, it is your fault not mine!  I warned you!

Remember that if your manifest says to build the touchwiz apk and you don't have it or, you've improperly named things within that apk the theme will not build properly.  That should
make sense right?

Ok great that wasn't hard at all was it?

The next part is for if you want to add additional assets.  If you do not with to you can skip to the "Build Part".
Now let's say you have additional assets you with to add to this ie: navbar.  For one always use lower case letters when adding a new asset apk to this (including the manifest).  The same
rule applies that we just spoke about.  Add the name to your manifest and your json.file first.  Then call the folder whatever it's called.  ie: "navbar".  do not call the folder "com.navbar"
or anything like that.
So what you need to do is take an existing asset folder and make a copy of the folder.  for example settings folder.  You'll then change the name of your folder that you made a copy of
to "navbar" since that's the example we're using right now.  You will notice there is a .iml file as well inside our copy.  We need to change the name of that to "navbar.iml" in order to have
the asset apk form properly.  You can do this either inside android studio by either right clicking on the file and going to "refactor" and then rename.  Or you can do this
outside of android studio. You do not need to open the .iml file and edit it.  You do however need to open the build.gradle file for the app and change the last part of the app name
located on line 8.  This will still be showing the original app name.  We don't want to make a duplicate right?  So make sure you adjust that.  The build.gradle is really the brains
of the operation in this whole program.  As you can see they actually control everything and will overwrite your manifests.  You do not need to touch the manifest for each asset apk either.

So now you will see a "settings.gradle" file at the bottom (directly below this readme file!!!)  open this file.  At the top you will see a series of asset folder names that are identical to
the names of the folders already provided in here.  So if you want to add a new asset you must also reference it here.  Follow the structure of how this is already written to add another one
in.  It's as simple as writing: ie: ":appname",   Just remember that at the very end there is no comma!

"Build Part"
So you're ready to test your theme and just want to build it.  At the top go to the "build" tab and select "build apk".  This will build all your asset apks in a min or two depending
on the speed of your computer.  When it's done you'll see a notification telling you it was successful.  You can go see for yourself by going to _app/src/main/assets and you will see your
asset apks.
Next you need to build the main apk.  Go back to the build tab and this time select build signed apk.  You will now need to either make a private signing key or use an existing one if you
have one.  It's not hard to make one so figure that out or google it.  the first popup window shows the theme being on the _app folder.  that's where it needs to be so do not select
anything else or it will not make the apk.  So next go through the signing key process. On the last part you will select the version you want to make.  Either Release or debug.  By default
it will be set to Release.  Keep it this way and select both check boxes for jar and apk signature under signature versions.  Then hit Finish and you're all done!  In about 2 seconds your
theme will be made and ready to install!

I hope you find this tool useful!  It was a huge pain in the ass to make this and a lot of work!
