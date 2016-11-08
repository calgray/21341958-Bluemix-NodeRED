
# Readme
DevOps repository for UWA CITS5503 project

 Callan Gray

## Summary
This server contains nodeRED flows to retrieve twitter comments, perform simple
sentiment analysis and then plot the information received.

This is done first by using the node red ui modules which can generate live data
 with text, plots and meters.

The second approach involves storing data to a mongoDB database to aggregate
the sentiment scores to create a histogram and an average score for any hashtag.


## Setup
* Create an IBM Bluemix Node-RED application
  * this configures a NodeJS app with the Node-RED template


* Add a DevOps deployment service
  * then connect it to the NodeRED app, which creates a git repo to IBM's hub.jazz.net
  * The bluemix console will already initialize the app with the starter template,
    pull it first and then modify it from there.


* Add environment variables:
  * NODE_RED_USERNAME = 21341958
  * NODE_RED_PASSWORD = CITS5503


* Install Cloud Foundary CLI
  * https://github.com/cloudfoundry/cli/releases
  * follow the getting started page on the      bluemix app page
  * deploy using ```cf push <appname>``` shows the deploy build log as well.
  * alternatively you can simply just use the git hooks and the
  command ```git push origin master```


* Install additional nodes
  * Extra nodes are available at: http://flows.nodered.org/
  * Use the nodeRED editor to search and add new nodes
    * add node-red-contrib-ui


* Disable the static help page
  * Make the node red editor the index page by:
    * commenting ```httpAdminRoot: /red'```
    * commenting ```httpStatic: path.join(__dirname,"public")```


## Warnings
* After deploys, the app will take about 15s to show on bluemix as "running",
  up to extra minute for the node-RED to actually initialize as it needs to
  download and install packages.

* Be cautious about installing extra nodejs packages: first application attempt
  had issues where packages once added could not be removed from future deploys.

* Flow data is persistent between deploys, stored locally in some folder, but
  cannot be seen in the file browsers, as it is not part of the source code.


## Project Notes
NodeRED is tied relatively close to bluemix, and the nodeRED module has its own
framework and entry point that performs static hosting on the folder "public".

The alternative to this is to embed node-red into a custom nodejs app such as an
express app as described here: http://nodered.org/docs/embedding, but maybe do
that some other time.






# Default Readme Instructions
  This README.md file is displayed on your project page. You should edit this
  file to describe your project, including instructions for building and
  running the project, pointers to the license under which you are making the
  project available, and anything else you think would be useful for others to
  know.

  We have created an empty license.txt file for you. Well, actually, it says,
  "<Replace this text with the license you've chosen for your project.>" We
  recommend you edit this and include text for license terms under which you're
  making your code available. A good resource for open source licenses is the
  [Open Source Initiative](http://opensource.org/).

  Be sure to update your project's profile with a short description and
  eye-catching graphic.

  Finally, consider defining some sprints and work items in Track & Plan to give
  interested developers a sense of your cadence and upcoming enhancements.
