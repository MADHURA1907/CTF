# Riddle Registry — CTF Writeup

## Challenge Information

- **Challenge Name:** Riddle Registry  
- **Author:** Prince Niyonshuti N.  
- **Category:** Forensics  
- **Difficulty:** Easy  
- **Platform:** (Add platform name if applicable)  

---

## Description

This challenge provides a PDF file filled with misleading and irrelevant text. The description hints that the real flag is hidden within the file’s metadata. The task is to analyze the PDF file and extract the hidden flag from its metadata fields.

---

## Tools Used

- Kali Linux  
- ExifTool  
- base64 (Linux utility)  
- VirtualBox (for shared folders)  

---

## Step-by-Step Solution

### Step 1 — Download the Challenge File

The provided link was used to download the PDF file:
confidential.pdf


---

### Step 2 — Access the File in Kali Linux

Since the file was downloaded on the Windows host system, a VirtualBox shared folder was configured. The file was accessed in Kali Linux at:

/media/sf_Downloads/confidential.pdf


---

Step 3 — Extract Metadata

ExifTool was used to inspect the PDF metadata:

The following Base64-encoded value was found in the Author field:

Author : cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOGY5MWQ2OH0=


---

Step 4 — Decode the Encoded String

The encoded Author value was decoded using:

echo cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOGY5MWQ2OH0= | base64 -d


---

Final Flag
picoCTF{puzzl3d_m3tadata_f0und!_c8f91d68}

Commands Used
exiftool confidential.pdf
echo cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOGY5MWQ2OH0= | base64 -d

 ### What Didn’t Work
1. Searching for the flag in visible PDF text
2. Using strings alone without checking metadata
3. Manually inspecting the PDF content without metadata tools

### Lessons Learned
1. PDF metadata is a common place to hide flags in forensic challenges
2. Base64 encoding is frequently used to obfuscate sensitive strings
3. ExifTool is essential for digital forensics and CTF challenges
4. Always follow challenge hints carefully

### What I Learned Personally
1. How to configure VirtualBox shared folders for file access
2. How to identify and decode Base64 strings in real scenarios
3. How to approach forensic challenges methodically
4. How to document technical work clearly for a professional portfolio
