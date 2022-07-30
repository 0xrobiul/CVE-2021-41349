<h1 align="center">
  <br>
  <a href="/Pic.png"><img src="Pic.png" widthh= alt="TryHackMe Scripting"></a>
</h1>

<p align="center">
<a href="https://github.com/0xrobiul/THM-Scripting/issues">
<img src="https://img.shields.io/github/issues/0xrobiul/THM-Scripting">
</a>
<a href="https://0xrobiul.me"><img src="https://img.shields.io/badge/Find%20Me-0xrobiul.me-red"></a>
<a href="https://twitter.com/0xrobiul"><img src="https://img.shields.io/twitter/follow/0xrobiul.svg?logo=twitter"></a>
</p>
      
# Summary
For this post I will be walking through the <a herf="https://tryhackme.com/room/scripting">Scripting room</a> from tryhackme.com. The idea is to use Python to write some basic scripts in order to solve challenges in a CTF format. I have given a brief summary of each task and a quick outline of the steps I followed when writing the scripts, comments in the code its self will give a more detailed idea of exactly how it works.

# Task 1 [Easy] Base64

The first task was quite straight forward. We are required to take a file that had been base64 encoded 50 time and reverse the process revealing the original string. Luckily Python has a <a herf="https://github.com/python/cpython/blob/3.8/Lib/base64.py">base64 library</a> ready for us to use so the steps we need are:

• Read the file into the `msg` variable
<br>
• Decode 50 times with a basic `for` loop
## Usage
```sh
python3 Easy.py [Lab IP]
```
# Task 2 [Medium] Gotta Catch em All

For this challenge we were required to connect to a webpage on a given port, retrieve some instructions for a mathematical process, perform a calculation and move onto the next port until we reach port 9867.

• Attempt to connect to the server until the port is live.<br>
• Once connected, request the data: operation, number, next port.<br>
• Receive the data and assign it.<br>
• Perform the operation.<br>
• Move onto next port.<br>
• Repeat this until we hit port 9867.<br>
• Display answer.<br>
## Usage
```sh
python3 Medium.py [Lab IP]
```
# TASK 3 [Hard] ENCRYPTED SERVER CHIT CHAT

For the last challenge we had to send a request to a web server via UDP and were sent instructions on how to complete the task. We were sent an IV and a key that were to be used to decrypt an AES CGM cipher text. We were also given a hash for the correct answer and had to keep requesting ‘flags’ until we found the on that matched the given checksum.

• Connect to server via UDP to get the initial instructions.<br>
• Connect again to receive the next set.<br>
• Store key and iv (Hard coded for ease).<br>
• Convert the checksum into a more usable/ readable format.<br>
• Connect agin, and receive AES CGM cipher text and tags.<br>
• Decrypt.<br>
• Hash the plain text and compare it to the given checksum.<br>
• Repeat this until a match is found.<br>

## Usage
```sh
python3 Hard.py [Lab IP]
```