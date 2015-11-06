# npm asset management example

while bower becomes more and more irrelevant (at least for me) because of npm, there may be a necessity to handle the loaded asset dependencies seperately from other production npm packages, e.g. like express and so on.

An idea on how to solve this is described here. Just manage the asset dependencies in an own project folder, and assign it as a scoped dependency inside your main package.json file.

By doing this your asset files will be grouped in the scope folder, and can for example packaged into the result build for your frontend code seperately from your backend dependencies,
that you may not want to be accessible for clients too.

## build

When your build your stuff like this, you have to remember, that this type of dependency listing is not a link to your sub folder, so installing new asset dependencies, you have to make sure, to remove the installed asset-dependency version from your node_modules folder, and rebuild it.

And also make sure, to run `npm install` in your asset directory in beforehand.

For development purposes `npm link` may be your friend.
