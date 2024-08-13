# Update-a-file-through-a-Python-Algorithm
## Project Overview
In my organisation, access to restricted content is managed through an **'allow list'** of IP addresses, which is specified in the **"allow_list.txt"** file. Additionally, a separate remove list details IP addresses that should be denied access. I developed an algorithm to automate the process of updating the **"allow_list.txt"** by removing IP addresses that are no longer authorised to access the content.

## Open the file that contains the allow list

In the initial part of the algorithm, I accessed the **'allow_list.txt'** file. I first assigned this file name as a string to the **'import_file'** variable:

<img width="362" alt="Screenshot 2024-08-13 at 11 45 35" src="https://github.com/user-attachments/assets/a03285c7-1a7b-41df-87db-6acf83f090f0">


I then employed a **'with'** statement to access the file:

<img width="362" alt="Screenshot 2024-08-13 at 11 45 35" src="https://github.com/user-attachments/assets/44b30618-f02d-413b-989a-f7cdc5fa5508">

In this algorithm, the **'with'** statement is used in conjunction with the '**.open()'** function in read mode to open the allow list file for reading purposes. This allows me to access the IP addresses contained within the file. The **'with'** keyword ensures that the file is properly closed once the operations are complete. In the code **'with open(import_file, "r") as file:'**, the **'open()'** function takes two parameters: the first specifies the file to be accessed, and the second indicates the mode, with **"r"** denoting read mode. The as keyword is used to create a variable named file, which holds the file object while operations are performed within the **'with'** block.


## Read the file contents

To read the contents of the file, I used the **'.read()'** method to convert it into a string.

<img width="622" alt="Screenshot 2024-08-13 at 11 52 34" src="https://github.com/user-attachments/assets/cf48a26a-1c72-4a34-af38-3504d1622dce">

When using the **'.open()'** function with the **"r"** argument for reading, the **'.read()'** method can be called within the with statement. This method transforms the file content into a string, enabling me to access it. I applied the **'.read()"** method to the file variable defined in the with statement and then stored the resulting string in the ip_addresses variable.

In summary, this code reads the contents of the **"allow_list.txt"** file into a string format, which I can then use to organise and extract data within my Python program.

## Convert the string into a list

To remove individual IP addresses from the allow list, I needed to convert it into a list format. I achieved this by using the .split() method to turn the ip_addresses string into a list.

<img width="527" alt="Screenshot 2024-08-13 at 11 59 39" src="https://github.com/user-attachments/assets/40a0f03a-7061-4b21-a766-d62562c04a6c">


The **'.split()'** method is applied to a string variable and transforms its contents into a list. This conversion simplifies the task of removing IP addresses from the **'allow list'**. By default, **'.split()'** divides the text by whitespace into separate list elements. In this process, the **'.split()'** method takes the **'ip_addresses'** string, where each IP address is separated by whitespace, and converts it into a list of IP addresses. I then reassigned this list back to the **'ip_addresses'** variable.

## Iterate through the remove list


A crucial part of my algorithm involves iterating through the IP addresses listed in the **'remove_list'**. For this, I used a **'for'** loop:


<img width="319" alt="Screenshot 2024-08-13 at 12 01 42" src="https://github.com/user-attachments/assets/dd835655-9ed1-4a1d-9d62-c4dcc1e01bf3">


In Python, a **'for'** loop allows code to be executed repeatedly for each item in a sequence. The purpose of the **'for'** loop in this context is to apply specific operations to every element within the sequence. The for keyword initiates the loop, followed by the loop variable element and the keyword **'in'**. The **'in'** keyword directs the loop to go through each item in the **'ip_addresses'** sequence and assign each value to the element variable.

## Remove IP addresses that are on the remove list

My algorithm needs to remove any IP address from the **'ip_addresses'** list that is also present in the **'remove_list'**. Since there were no duplicates in **'ip_addresses'**, I used the following approach:

<img width="531" alt="Screenshot 2024-08-13 at 13 30 48" src="https://github.com/user-attachments/assets/efc29257-3a48-4415-b032-4d23d7918ca6">

Inside the for loop, I set up a condition to check if the current element from the loop was in the **'ip_addresses list'**. This step was crucial to avoid errors, as attempting to remove elements not found in **'ip_addresses'** would cause issues.

Within this condition, I used the **'.remove()'** method on **'ip_addresses'**. I passed the loop variable element as the argument, ensuring that each IP address found in the **'remove_list'** was removed from **'ip_addresses'**£.

## Update the file with the revised list of IP addresses

As the final step of my algorithm, I needed to update the allow list file with the new list of IP addresses. To achieve this, I first converted the list back into a string using the **'.join()'** method:

<img width="625" alt="Screenshot 2024-08-13 at 13 34 20" src="https://github.com/user-attachments/assets/cfb236ca-7c88-425d-96fd-1f4699479780">

The **'.join()'** method merges all items in an iterable into a single string. It is used with a string that defines the separator between the elements of the iterable. In this case, I used the **'.join()'** method to transform the **'ip_addresses'** list into a string so it could be passed to the **'.write()'** method for updating the **"allow_list.txt"** file. I chose **"\n"** as the separator to ensure each IP address appears on a new line.

Subsequently, I used another with statement along with the **'.write()'** method to update the file:

<img width="430" alt="Screenshot 2024-08-13 at 13 34 51" src="https://github.com/user-attachments/assets/bf905c83-970b-4bd5-b59b-13339298486c">

In this instance, I used the **"w"** mode with the **'.open()'** function within the with statement, indicating that the file should be opened for writing and its contents replaced. This allowed me to use the **'.write()'** function to output the new string data to **"allow_list.txt"**, thereby updating the file with the revised IP addresses. The **'.write()'** function replaced the old content with the updated **'ip_addresses'** data, ensuring that any removed IP addresses no longer had access.

# Summary

I developed an algorithm to remove IP addresses listed in a **'remove_list'** variable from the **"allow_list.txt"** file, which contains approved IP addresses. The algorithm involved opening the file and reading its contents as a string, which was then converted into a list stored in the **'ip_addresses variable'**. I iterated through the IP addresses in the **'remove_list'**, checking each one to see if it was in the **'ip_addresses'** list. If an IP address was found, I used the **'.remove()'** method to delete it from the **'ip_addresses'** list. Finally, I employed the **'.join()'** method to convert the updated **'ip_addresses'** list back into a string and overwrite the **"allow_list.txt"** file with the revised list of IP addresses.

