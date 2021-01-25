# Shell Data Processing

## Overview
For week two, we are tasked to do shell data processing. To get acclimated with PowerShell, we used it to create the repository and two different files (.gitignore & README.md).

To create these files, first, we have to select the <i>'Run Powershell Window here as a Administrator'</i> when you right click within the file window. Once this is selected, PowerShell opens up on the screen.

Next, to create our repository, we enter the following code into PowerShell:

```Powershell
> mkdir shell-data-processing
```

This will create a new folder within your main folder. From here you can use the following code to enter the file and began manipulating the repository:

```Powershell
> cd shell-data-processing
```

Within this folder, we can then use the ```ni``` command to create the README.md and .gitignore files:

```Powershell
> ni README.md
> ni .gitignore
```

To verify that the files we just created are completed successfully, we can use the follwing code that makes a list of all current files:

```Powershell
ls 
```

Although short, this command will give you a brief list of all files in the directory.

Then, we can enter VS Code directly from PowerShell to begin editing files:

```Powershell
code .
```

## List of Commands
- ``` mkdir (folderName)```
    - Creates a new folder in the current folder
- ``` cd (folderName) ```
    - Moves Powershell into the selected folder
-  ``` ni (fileName) ```
    - Creates a new file in the current folder
- ``` ls ```
    - Prints out a list of files in the current fileo
- ``` code . ```
    - Opens VS Code using the currently used file

## Analyzing Data from Online Source

Moving on to data processing, I found an article on cnet.com that discusses the possibliity and expectations for a next stimulus check. That can be found here: https://www.cnet.com/personal-finance/when-will-the-next-stimulus-check-come-these-are-two-possible-timelines-right-now/.

Within PowerShell, we can run the curl command to grab the source of the URL and output the text to a specified file:

```PowerShell
curl "https://www.cnet.com/personal-finance/when-will-the-next-stimulus-check-come-these-are-two-possible-timelines-right-now/" -O "data.txt"
```
<sub>Note: The URL can be replaced with any other article. The code should still work the same.</sub>

Once the article has be saved to the file, use <i>ALT + SPACE + C</i> to close PowerShell. Then, we <i>right-click</i> within the same folder and select <i>'Git Bash Here'</i>. A new command prompt will open, allowing us to run Bash commands.
<br></br>
### Transformation of Data

When we 


