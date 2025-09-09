# picoCTF Writeup – Obedient Cat

**Challenge Name:** Obedient Cat  
**Author:** syreal  
**Category:** General Skills  
**Points:** 5  

---

##  Description
This file has a flag in plain sight (aka "in-the-clear"). Download the flag.  

Hints:  
1. Any hints about entering a command into the Terminal (such as the next one) will start with a `$`... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.  
2. To get the file accessible in your shell, enter:  
   ```bash
   $ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Use man cat to learn how to display file contents.

 Initial Thoughts
The challenge hints strongly that the flag is inside a simple text file named flag.

Since it’s “in-the-clear,” no decoding or cracking is required.

Likely solution: use the cat command to print the file.

 Steps to Solve
First, I downloaded the file using:

bash
Copy code
we get https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Then I checked the directory to confirm the file exists:

bash
Copy code
ls
Finally, I displayed its contents with:

bash
Copy code
cat flag
 Flag
Copy code
picoCTF{s4n1ty_v3r1f13d_f28ac910}
Lessons Learned
Learned how to use wget to download files from a URL.

Practiced using the cat command to print file contents in Linux.

Reinforced the importance of reading hints in problem statements carefully.