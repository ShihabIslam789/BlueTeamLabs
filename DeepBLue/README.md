# DEEPBLUE
![Senario](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Scenario.png)
# Step by Step process

This Senario does not need any downloads, all you have to do is launch the Virtual machine button on the side and put in the username to open up access to the "Investigations" folder.

All you have to do is check the logs to verify when the attack occured using the software of DeepBlue which allows for an easier time for Threat Hunting.

## Question 1

To get to the point of answering this question you have to use Windows Powershell to navigate the logs to see who executed the application. First use the search bar in the bottom left and run "Windows Powershell".

You can change Directories by using the command "cd" and the pathway you wish to go. In this case you want this directory, " cd \Desktop\investigations\DeepBlueCLI-master.

Then run the powershell script writing, ".\DeepBlue.ps1 ..\ Security.evtx

![PowerShell](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/PowerShell%20part%201.png)


![PowerShell2](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/PowerShell%20part%202.png)


If you scroll through the log you come across a person named Mike Smith who runs
 "GoogleUpdate.exe"


![Google](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Google%20Update.png)

## Question 2 + 3

To answer this questions you have to scroll through the log to find the mentioned MeterPreter tool usage  which will tell you when and what service was created and ran at that moment. 

MeterPreter is a Metasploit attack payload that interacts with the shell and executes code.

![MeterPreter](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Suspicious%20Service.png)

## Question 4

Now you want to use Windows event viewer which you can type in the Operating System searchbar and open the application that way. You want to load the log files within the lab files.

Since the question has specificed a specific time you can click on "Filter Current Log" and set the custom range from 04/10/2021 at 10:30 to 10:50 AM.  then you just find when the service was used from the last question.

![EW View](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Edit%20Event%20Viewer.png)

## Question 5 

Now between 04/10/2021 between 11:25 AM to 11:40 AM there is another  user account created by the attacker Mike. Though becareful you might be confused thinking it might be "Jack Wills" but that is incorrect. Names like these are very unusal and can be hidden in sight.

The answer actually is "user ServiceAct /add". A service account is something you would leave on always to easily access the needed tools from it. It's clever to hide as such b/c it makes sense that such an account would exist, but the reason we think its a malicious account is beacuse it was made by Mike.

![Service](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Service%20account.png)


## Question 6 

To answer this you want to continue to scroll through the logs and find what Groups the account has been added to. You will find it is added to two groups which are Administration and Remote Desktop user. So it can leave with the data as much as the attacker wants. 


### Results

If you followed so far your lab would look like this
![answers](https://github.com/ShihabIslam789/BlueTeamLabs/blob/main/DeepBLue/Lab%20Answers.png)


