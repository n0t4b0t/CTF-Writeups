# Rogueful Helper: An Unintended Solution

![Challenge Description](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/challenge.PNG)

## Approach

### Step 1: Initial Grep Search for Date and Time

Initially, I used the `grep` command, setting the recursive flag `-r`, to search for the specific date and time as shown in the challenge description. As this did not return any results, I narrowed the search to just the date.

![Step 1 Screenshot](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/expanded1.png)

### Step 2: Observing the date-time format

Although the first few results had the date and time in the format of my query, when I scrolled through the output, I noticed that some results contained a 'T' between the date and the time.

![Step 2 Screenshot](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/2.png)

### Step 3: Adjusting the grep query

I adjusted my `grep` query, which indicated that a binary file contained a date-time string matching my search criteria.

![Step 3 Screenshot](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/3.png)

### Step 4: Extracting Strings from the Binary File to find the flag

Using the `strings` command on the binary file revealed the ICMP payload.

![Step 4 Screenshot](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/4.png)

The flag was then submitted as `DUCTF{cHd5cmVxAWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWE=}`.
