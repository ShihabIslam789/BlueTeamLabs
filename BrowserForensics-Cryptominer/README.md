# Cryptominer

![Lab Scenario]([Lab Senario.png](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/BrowserForensics-Cryptominer/Lab%20Senario.png))

# Step by Step process

    First your going to need to download the encrypted files in the lab and familiarize
    You want to download the "Browser dump" and place it somewhere you can access easily.
    Also you want to download a "BrowserHistoryViewer" incase the you need the tool for the lab. 

    If you tried opening the Browser Dump file you will need the password stated in the website to decrypt itr for access. Then access the  folder and decrypt the "BrowserData" folder. When opening the folder you will notice the file has "ad1" extension, which means it is a specific container to hold this information.

    To open that file download a program called FTK imager. This tools helps with forensics 
    Analysis and can open the "ad1" file. Once downloaded go to "File -> add Evidence Item -> Image File", upload the path the ad1 file. 

# Question 1

to answer this question you have to know how to navigate the directory of the files. If you google profiles it will tell you it is under Appdata folder under roaming. But if you navigate the files through FTK program you will notice there is only "Mozilla" folder. Thw question asked for Google Chrome specifically,  so you have to ask yourself what about the local users to the machine. 

you if done right you will have gone through the directory like this:
"browserdata.ad1\Custome Content Image\PhysicalDrive\root
\App Data\Local\Google\Chrome\User data\"

you notice there is the Default option and profile 1 meaning there is a total of 
2 profiles as the answer.

# Question 2

Your going to need to use the Browser History app, but first in FTK imager right click the folder "user" and extract it somewhere you can access. You can open it using the Browser History viewer, and make sure to set it up so you can see data from any point in time and from a specified folder. Enter the file path for users and the browsing history can be seen.

You can scroll down and see what the user looked up and eventually you will find the themes he was looking at was "Earth in Space" at 3:31: 53 pm. Now you can go back to the FTK and search extensions modified at that time and find the Manifest.json file and see "Earth and Space is installed and the right answer.

# Question 3 + 4

Through the FTK image app, you have go through the extensions and find the installed cryptominer within the files.  You will find it in the "egnfmleidkolminhjlkaomjefheafbbb"
folder and the description of the cryptominer extension. 

# Question 5

In the code is where the malware is written and can be noticed within the extension path it originates from "background.js" It has a bigger file size from something simple. 
you want to extract that and look into it.

## NOTES
    Keep in mind when clicking on an executable the malware could go off. First thing to do is change the file extension to be visible in the "view tab" in file explorer. rename the file extension to something makes it non-excutable.

Now open the background file in notepad and you will find the name of the cryptominer used in the extension.

# Question 6

In the background file you opened there is the variable named "hashesPerSecond" the number used there is the answer.

# Question 7 

The public kety can be found in the variable miner within the parenthesis

# Question 8

You can google cryptolootminer and see the twitter page.
