## Red Gate Deployment Manager, Team Foundation Server (or Service) integration

These files are custom build templates for TFS that allow you to call the RgPublish command line to publish your projects to Deployment Manager.

They extend the fields available in the build definition, allowing you to easily customise the publish process.

![TFS build definition](http://thefutureofdeployment.com/wp-content/uploads/2013/11/DmTfs.png)

The template modifies the build number format to be just the BuildID. The BuildID is an integer that continues to increase, unlike the build revision number that resets each day. The version number of the published package is the value used for Publish version number followed by the build number. Eg. 1.0.0.259. This should be suitable for most cases, but you can always tweak the behaviour as needed.

There are versions available for both TFS 2010 and 2012.

**To integrate the custom template into your build process**, you can either:

* **Use these templates directly.** This is easiest. It’s only possible if you are currently using the default build template, as you’ll otherwise lose any customisations you’ve made.
* **Merge the changes into your build template.** This is a little bit tricky. You need to make sure the right pieces of XML go in the right places.  It’s worth it though, if you’re reusing a custom build template across a number of different projects. The diff is available to [view online](http://diffchecker.com/o2ijdfhr).

You'll need to make sure the RgPublish.exe command line is available to the build agent in some way. You could either copy it to your build agent, or commit it to TFS. You can download the latest version of this command line from the Tools menu in your Deployment Manager installation.
