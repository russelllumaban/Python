<h1>Update a File Through a Python Algorithm</h1>



<h2>Project Description</h2>
At my organization, access to restricted content is controlled with an allow list of IP addresses. The <b><i>"allow_list.txt"</i></b> file identifies these IP addresses. A separate remove list identifies IP addresses that shoould no longer have access to this content. I created an algorith, to automate updating the <b><i>"allow_list.txt"</i></b> file and remove these IP addresses that should no longer have access.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 


<h2>Program walk-through:</h2>

<p align="center">
<b>Open the File that Contains the Allow List</b> <br/>
For the first part of the algorithm, I opened the <b><i>"allow_list.txt"</i></b> file. First, I assigned this file name as a string to the <b><i>import_file</i></b> variable:
<br />
<img src="https://imgur.com/EDbdyby.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Then, I used a <b><i>with</i></b> statement to open the file:
<img src="https://imgur.com/sjM57J8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In my algorithm, the <b><i>with</i></b> statement is used with the <b><i>.open()</i></b> function in read mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The <b><i>with</i></b> keyword will help manage the resources by closing the file after exiting the <b><i>with</i></b> statement. In the code <b><i>with open(import_file, "r") as file:</i></b>, the <b><i>open()</i></b> function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, <b><i>"r"</i></b> indicates that I want to read it. The code also uses the <b><i>as</i></b> keyword to assign a variable named <b><i>file</i></b>; <b><i>file</i></b> stores the output of the <b><i>.open()</i></b> function while I work within the <b><i>with</i></b> statement.

<br />
<br />
<b>Read the File Contents</b>  <br/>
In order to read the file contents, I used the <b><i>.read()</b></i> method to convert it into the string.
<img src="https://imgur.com/XeX1TSF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
When using an <b><i>.open()</b></i> function that includes the argument <b><i>"r"</b></i> for “read,” I can call the <b><i>.read()</b></i> function in the body of the <b><i>with</b></i> statement. The <b><i>.read()</b></i> method converts the file into a string and allows me to read it. I applied the <b><i>.read()</b></i> method to the <b><i>file</b></i> variable identified in the <b><i>with</b></i> statement. Then, I assigned the string output of this method to the variable <b><i>ip_addresses</b></i>. 
<br />
<br />
In summary, this code reads the contents of the <b><i>"allow_list.txt"</b></i> file into a string format that allows me to later use the string to organize and extract data in my Python program.
<br />
<br />
<b>Convert the String into a List</b>: <br/>
In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the <b><i>.split()</b></i> method to convert the <b><i>ip_addresses</b></i> string into a list.
<img src="https://imgur.com/Kswbd2d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The <b><i>.split()</b></i> function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of spliting <b><i>ip_addresses</b></i> into a list is to make it easer to remove IP addresses from the allow list. By default, the <b><i>.split()</b></i> function splits the text by whitespace into list elements. In this algorithm, the <b><i>.split()</b></i> function takes the data stored in teh variable <b><i>ip_addresses</b></i>, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable <b><i>ip_addresses</b></i>
<br />
<br />
<b>Iterate Through the Remove List</b>  <br/>
A key part of my algorithm involves iterating through the IP addresses that are elements in the <b><i>remove_list</b></i>. To do this, I incorporated a <b><i>for</b></i> loop:
<br />
<img src="https://imgur.com/CyaD41j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The <b><i>for</b></i> loop in Python repeats code for a specified sequence. The overall purpose of the <b><i>for</b></i> loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The <b><i>for</b></i> keyword starts the <b><i>for</b></i> loop. It is followed by the loop variable <b><i>element</b></i> and the keyword <b><i>in</b></i>. The keyword <b><i>in</b></i> indicates to iterate through the sequence <b><i>ip_addresses</b></i> and assign each value to the loop variable <b><i>element</b></i>.
<br />
<br />
<b>Remove IP Addresses that are on the Remove List</b>  <br/>
My algorithm requires removing any IP addresses from the allow list, <b><i>ip_addresses</b></i>, that is also contained in the <b><i>remove_list</b></i>. Because there were not any duplicates in <b><i>ip_addresses</b></i>, I was able to use the following code to do this:
<img src="https://imgur.com/HAcglfp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
First, within my <b><i>for</b></i> loop, I created a conditional that evaluated whether or not the loop variable <b><i>element</b></i> was found in the <b><i>ip_addresses</b></i> list. I did this because applying <b><i>.remove()</b></i> to elements that were not found in <b><i>ip_addresses</b></i> would result in an error.
<br />
<br />
Then, within that conditional, I applied <b><i>.remove()</b></i> to <b><i>ip_addresses</b></i>. I passed in the loop variable <b><i>element</b></i> as the argument so that each IP address that was in the <b><i>remove_list</b></i> would be removed from <b><i>ip_addresses</b></i>.
<br />
<br />
<b>Update the File with the Revised List of IP Addresses</b>  <br/>
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the <b><i>.join()</b></i> method for this:
<img src="https://imgur.com/6tBJYwc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The <b><i>.join()</b></i> method combines all items in an iterable into a string. The <b><i>.join()</b></i> method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the <b><i>.join()</b></i> method to create a string from the list <b><i>ip_addresses</b></i> so that I could pass it in as an argument to the <b><i>.write()</b></i> method when writing to the file <b><i>"allow_list.txt"</b></i>. I used the string <b><i>("\n")</b></i> as the separator to instruct Python to place each element on a new line. 
<br />
<br />
Then, I used another <b><i>with</b></i> statement and the <b><i>.write()</b></i> method to update the file:
<img src="https://imgur.com/PvvfsPf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
This time, I used a second argument of <b><i>"w"</b></i> with the <b><i>open()</b></i> function in my <b><i>with</b></i> statement. This argument indicates that I want to open a file to write over its contents. When using this argument <b><i>"w"</b></i>, I can call the <b><i>.write()</b></i> function in the body of the <b><i>with</b></i> statement. The <b><i>.write()</b></i> function writes string data to a specified file and replaces any existing file content. 
<br />
<br />
In this case I wanted to write the updated allow list as a string to the file <b><i>"allow_list.txt"</b></i>. This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the <b><i>.write()</b></i> function to the file object file that I identified in the <b><i>with</b></i> statement. I passed in the <b><i>ip_addresses</b></i> variable as the argument to specify that the contents of the file specified in the <b><i>with</b></i> statement should be replaced with the data in this variable.
<br />
<br />
<h2>Summary</h2>
I created an algorithm that removes IP addresses identified in a <b><i>remove_list</i></b> variable from the <b><i>"allow_list.txt"</i></b>" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable <b><i>ip_addresses</i></b>. I then iterated through the IP addresses in <b><i>remove_list</i></b>. With each iteration, I evaluated if the element was part of the <b><i>ip_addresses</i></b> list. If it was, I applied the <b><i>.remove()</i></b> method to it to remove the element from <b><i>ip_addresses</i></b>. After this, I used the <b><i>.join()</i></b> method to convert the <b><i>ip_addresses</i></b> back into a string so that I could write over the contents of the <b><i>"allow_list.txt"</i></b>" file with the revised list of IP addresses.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
