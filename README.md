blink-jenkins
=============

Display current state of a Jenkins instance using a blink(1) from 
ThingM (http://www.kickstarter.com/projects/thingm/blink1-the-usb-rgb-led). 

Polls the server at 15 second intervals, and will display green if all jobs built successfully, yellow if one or more jobs are unstable, and red if one or more have failed. It will also blink if one or more jobs are currently building.

Simply run the python file, passing it the `--host` parameter to tell it where your Jenkins instance lives. You may also pass the `--user` and `--password` parameters if your Jenkins instance requires basic authentication. Jobs can be ignored by passing them as a comma-delimited string of names under the `--ignore` parameter.

Example execution for Windows machines (useful as part of a batch script)

    python jenkins.py --host http://my.jenkins.server.com/ --ignore TestBuild1,BrokenBuild

Command line options:

    -h      | --host     | The URL of the Jenkins server (root view or individual job page).
    -u      | --user     | The HTTP Basic Authentication username.
    -p      | --password | The HTTP Basic Authentication password.
    -i      | --ignore   | A comma-separated list of the job names to ignore the status from.
    -device | --deviceid | The Id of the Blink(1) to activate. (Zero-indexed list of devices, default is 0).

![Build Failed!](https://raw.github.com/MMTDigital/blink-jenkins/gh-pages/img/build-failed.jpg)
![Build Success!](https://raw.github.com/MMTDigital/blink-jenkins/gh-pages/img/build-success.jpg)