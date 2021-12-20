# Jenkins Plugins

## Managing Plugin

![Manage Plugin](images/1.jpg)

![Plugin Manager](images/2.jpg)

We can enable/disable plugins by checking/unchecking checkbox on available tab.

## Updating Plugin

![Update Plugin](images/3.jpg)
We can do (shift + click) over a plugin to see what we are changing to.

    backup files are put here - previous version.
    ls -l /var/lib/jenkins/plugins/ | grep -i <<filename>>

## Adding Plugins

There are three ways we can add plugin.

1. Avaiable Tab:
![Adding Plugin](images/9.jpg)

2. Advanced Tab:
It is recomemned to use available tab to install the plugin. but if you want to do a plugin upload manually using HPI file.
![Adding Plugin](images/7.jpg)

3. Console
    
        wget <<file>>
        -> 
        ls -l
        -> ec2.hpi
        sudo cp ./ece2.hpi /var/lib/jenkins/plugins/
        -> done
        ls -l /var/lib/jenkins/plugins/
        -> list of files
        sudo chown jenkins:jenkins /var/lib/jenkins/plugins/ec2.hpi
        -> 

