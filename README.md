# Introduction
An Google appengine deployment of some functionality based on [sanskrit-coders/sanskritnlpjava](https://github.com/sanskrit-coders/sanskritnlpjava) and related projects.

# Users
## Web-UI users
* The corresponding webserver hosts pages such as: <http://sanskritnlp.appspot.com/forms/Chandas-de.htm> etc..
    * (These are listed from <https://sites.google.com/site/sanskritcode/projects>.)
* Last update : 2017-03-23

# Contributors
## Links to general comments
See [indic-transliteration/README](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md) for the following info:

  - [Setup](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#setup)
  - [Deployment](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#deployment)
    - [Regarding **maven targets** in intellij](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#regarding-**maven-targets**-in-intellij)
    - [Building a jar.](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#building-a-jar.)
  - [Technical choices](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#technical-choices)
    - [Scala](https://github.com/sanskrit-coders/indic-transliteration/blob/master/README.md#scala)

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

