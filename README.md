# Introduction
An Google appengine deployment of some functionality based on [sanskrit-coders/sanskritnlpjava](https://github.com/sanskrit-coders/sanskritnlpjava) and related projects.

# Users
## Web-UI users
* The corresponding webserver hosts pages such as: <http://sanskritnlp.appspot.com/forms/Chandas-de.htm> etc..
    * (These are listed from <https://sites.google.com/site/sanskritcode/projects>.)
* Last update : 2017-03-23

# Contributors
## Setup
* Strongly recomment Intellij Idea IDE.
  * Just point it to the IML file and .idea/* files.

## Where is the code?
* src/main/ has subfolders called java, scala. They respectively contain code written in those languages.
* Javascript code is in war/js.
* HTML forms are found in war/forms.

## Deployment
* Regarding **maven targets**:
  * You can set up a maven goal in intellij as well.
  * In intellij: Don't be fooled by weird messages in the Run widget - look at the messages widget.

### Deploying to google cloud.
* Note that we're using appengine-maven-plugin in <pom-war.xml>. In intellij pass this file explicitly with -f pom-war.xml.
  * It's use is described [here](https://cloud.google.com/appengine/docs/standard/java/tools/maven).
* `mvn appengine:update` should do the trick - if you have right maven version.
  * If you are doing this from intellij:
    * a browser window will pop up, get SSO authentication done,
    * give you a code to paste in the maven widget.
* Local build
  * Alternative: `mvn clean install`
    * Files are output in target/ .
  * Intellij AppEngineDev plugin
    * Uses the artifacts:
        * sanskritnlpjava-g-appengine-exploded.war, which includes sanskritnlpjava.
* Local dev server run: `mvn appengine:devserver`
* Manage online at <https://console.cloud.google.com> . Navigate around a bit.
  * Quotas [link](https://console.cloud.google.com/appengine/quotadetails?project=sanskritnlp).
    * As of 201705 - seems to include 1GB incoming and outgoing bandwitdth. 

