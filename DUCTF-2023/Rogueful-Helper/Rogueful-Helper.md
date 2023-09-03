# Rogueful Helper: An Unintended Solution

![Challenge Description](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/challenge.PNG)

## Introduction

I am not an expert in forensics, but I am well-versed in finding things using grep and regular expressions. Typically, this involves complex patterns and piping, but this challenge was unexpectedly simple to solve using basic grep functionality.

## Approach

### Step 1: Initial Grep Search for Date and Time

Initially, I used the `grep` command, setting the recursive flag `-r`, to search for the specific date and time as shown in the challenge description. As this did not return any results, I narrowed the search to just the date.

![Step 1 Screenshot](https://raw.githubusercontent.com/n0t4b0t/CTF-Writeups/main/DUCTF-2023/Rogueful-Helper/Screenshots/1.png)

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

## Conclusion

While some might consider the use of grep for flag discovery to be controversial, I view it as a method of leveraging hacking skills to identify and exploit vulnerabilities—precisely the essence of CTF competitions.
