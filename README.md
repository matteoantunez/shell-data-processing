# <center>Shell Data Processing</center>

## Overview
For week two, we are tasked to do shell data processing. To get acclimated with PowerShell, we used it to create the repository and two different files (.gitignore & README.md).

To create these files, first, we have to select the <i>'Run Powershell Window here as a Administrator'</i> when you right click within the file window. Once this is selected, PowerShell opens up on the screen.

Next, to create our repository, we enter the following code into PowerShell:

```PowerShell
> mkdir shell-data-processing
```

This will create a new folder within your main folder. From here you can use the following code to enter the file and began manipulating the repository:

```PowerShell
> cd shell-data-processing
```

Within this folder, we can then use the ```ni``` command to create the README.md and .gitignore files:

```PowerShell
> ni README.md
> ni .gitignore
```

To verify that the files we just created are completed successfully, we can use the follwing code that makes a list of all current files:

```PowerShell
> ls 
```

Although short, this command will give you a brief list of all files in the directory.

Then, we can enter VS Code directly from PowerShell to begin editing files:

```PowerShell
> code .
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

## Collecting Source Data from URL

Moving on to data processing, I found an article on cnet.com that discusses the possibliity and expectations for a next stimulus check. That can be found here: https://www.cnet.com/personal-finance/when-will-the-next-stimulus-check-come-these-are-two-possible-timelines-right-now/.

Within PowerShell, we can run the ``` curl ``` command to grab the source of the URL and output the text to a specified file:

```PowerShell
> curl "https://www.cnet.com/personal-finance/when-will-the-next-stimulus-check-come-these-are-two-possible-timelines-right-now/" -O "data.txt"
```
<sub>Note: The URL can be replaced with any other article. The code should still work the same.</sub>

Once the article has be saved to the file, use <i>ALT + SPACE + C</i> to close PowerShell. Then, we <i>right-click</i> within the same folder and select <i>'Git Bash Here'</i>. A new command prompt will open, allowing us to run Bash commands.

<br>

## Transformation of Data

When we grab the source, the data is not the cleanest. The source data typically contains lots of HTML code and everything remains in long lines. Using the following command, we can make individual words reside on a single line.

```Bash
tr ' ' '\12' < data.txt
```
<sub>Note: data.txt can be renamed to any file of your choosing</sub>

## Sort & Consolidate Data
Currently, we have grabbed the code and seperated the words in sentences. Next, we will 'pipe' the data into the ``` sort ``` command:

```Bash
tr ' ' '\12' < data.txt | sort
```

Next, we can use the ``` uniq -c ``` command in addition to the one above to reduce the output and count the unqiue occurences of each word:

```Bash
tr ' ' '\12' < data.txt | sort | uniq -c
```

With the reduced output, we can then use the ``` -nr ``` flag to sort the data, once-more, but in <b>reverse-numerical</b> form:

```Bash
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr
```

Lastly, we can add the ``` > result.txt ``` code to the end to save the data to a new file:

```Bash
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr > result.txt
```

## Tips and Tricks

### Bash Shell (General Tips)
- <i>Up-Arrow</i>: Replaces current text with previous command that was submitted
- <i>CTRL + SHIFT + C</i>: Copy in Bash
- ``` -n ```: Numeric
- ``` -r ```: Reverse
- Single Letter Flag (i.e. ``` -r ```): Only <b>1</b> dash
- Multiple Letter Flag (i.e. ``` -rn ```): Only <b>1</b> dash
<br></br>

### Bash Shell (Important Commands) 

- ``` > ```: Redirects content from directory to file
<br><sub>Note: If there is a file in the same directory, that file will be overwritten.<sub>
<br>

- ``` >> ```: Redirects and Appends the conent from the directory to the end of the file
- ``` ls ```: Lists the contents in the default directory
    - Use ``` ls > temp.txt ``` to save the results to a seperate file 
- ``` cat ```:  Display contents of temp.txt in prompt window


