# Basic Job Structure

## Structure
Project -> configure -> configure in the way you want

## Parameter

Project ->  configure -> This project is parameterizied -> Add parameter -> String Parameter
![****](images/11.jpg)

![****](images/12.jpg)

Project ->  configure -> Build -> Execute shell -> Command

    echo " Hello" $name
![****](images/13.jpg)

## Notifications

Post Build Notificaions.

Jenkins has varity of plugins to support this.

Email,
SMS,
Zoom,
Skype,
Slack

# **Agents and Distributed Builds**

## Setting up a Build Agent

It is a good practice to not run build on Jenkins Master. they should run on remote build agent so that all the hoursepower master has is used on coordinating builds and all the horsepower agents have is used for creating builds.

Manage Jenkins ->  Manage Node

# **Source Code Management, Build Tools, and Test Reports**


# **Upstream, Downstream, and Triggers**


# **Jenkins on the Command Line**