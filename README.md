# Allstarlink Always Busy

Do you ever go through node after node looking for which ones have an interesting qso underway, a news report or something that sounds worth listening to?

These are two scripts to be used by ham radio operators with Allstarlink nodes.

It is good fun connecting to whichever node is the most active in the world without knowing which country it is, what language they may be speaking or what the topic will be...


## Getting Started
There are two scripts.

The first script is findactivenode
* This script gets all the currently keyed nodes from : http://stats.allstarlink.org/stats/keyed
* The list of nodes are compiled into a list. This list gets added to every 30 seconds.
* After 10 minutes the list starts getting written over.
* The script organises the list in order starting with the nodes that have been keyed the most often.
* The most keyed node is written to the file currentactiveallstarnode

You can run findactivenode on any Linux device. If you want to watch the file get updated then use the below command:

```
tail -f ./currentactivenode
```

The second script is named allstaralwaysbusy. 
* This script will connect your node to the node that has been identified with findactivenode.
* It will first disconnect your node
* Wait 3 seconds
* Then connect to the node that was identified as the most active

I have left lots of notes in the scripts explaining each step that is taken.

In order to use the script allstaralwaysbusy it will need to be copied into a directory on your node.
You then ssh to your node, go to the Command Line Interface and run the node.
When you run this script it will disconnect your node from any nodes it is currently connected to, wait 3 seconds then connect to whichever node is the mode active.

Just a note however. Some nodes don't have any traffic. And some nodes simply won't let you connect. So if you find it is not working check in Supermon which node you are connected to and you will likely find that it is registered as being keyed up however there is no traffic. I don't know why this happens.

## Prerequisites

You will need to have the installed. Curl is a terminal web browser. If you are running Ubuntu then you can download it from the Ubuntu app store. 
Or, the below command will also install it:

```
sudo apt install  curl
```

## Author

* **hatchet-elf - ham radio operator vk3elf**
* **https://github.com/hatchet-elf/Allstarlink-always-busy** 


## License

This project is licensed under the MIT License - see the [LICENSE] file for details

