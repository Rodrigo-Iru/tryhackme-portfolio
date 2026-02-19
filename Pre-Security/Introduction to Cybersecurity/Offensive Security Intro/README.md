# Offensive Security Intro

**Platform:** TryHackMe  
**Learning Path:** Pre Security  
**Level:** Introductory 

--

## 🧠 Lab Overview.
A fake banking application called FakeBank is deployed in a controlled environment.
The purpose of this exercise is to introduce basic offensive security concepts by analyzing a web application from an attacker’s perspective.
The lab demonstrates how hidden functionality within a web application can be discovered and abused.

## 🌐 FakeBank Web Application
![Web ss](<img width="642" height="687" alt="image" src="https://github.com/user-attachments/assets/772b30bf-3ad2-4ef4-9b98-7ed829b2ca37" />)

--

## 🔎 Initial Attack Approach. 
As mentioned earlier, the objective of this exercise is to find a way to exploit the FakeBank application to manipulate account funds.
We are provided with valid user credentials, simulating a normal bank customer.
One common attack technique against web applications is searching for hidden or unlinked functionality. Sometimes, developers leave sensitive features accessible through secret or unreferenced URLs.
If such URLs are discovered, an attacker may be able to perform unauthorized actions.

--

## 🛠️ Directory Enumeration with DIRB
To identify hidden URLs, the tool DIRB was used.
DIRB performs a brute-force attack by testing a list of potential directory and file names against the target web server.
The command structure is simple:
    dirb http://target-url

It requires:
-> The target URL
-> A wordlist (automatically loaded in this case)

--

## 💻 DIRB Execution 
![Terminal ss](<img width="565" height="535" alt="image" src="https://github.com/user-attachments/assets/35bfdb3a-905b-4f07-9241-1ffca000d09e" />)
Some key parts of the output:
- URL_BASE → The target URL provided to the tool
- WORDLIST_FILES → The location of the wordlist used for brute-force testing
- Lines starting with + → Discovered directories or pages (hidden URLs)

These discovered paths represent potential hidden functionality within the application.

--

## 🔐 Hidden Page.
![Page ss](<img width="648" height="619" alt="image" src="https://github.com/user-attachments/assets/52475f46-7d99-4ce2-a6c0-0fc6bf4c2f52" />)
On this page, it was possible to submit an account number (provided at the beginning of the lab) and specify an amount to modify the account balance.
This demonstrates how exposed administrative or backend functionality can be abused if proper access controls are not implemented.

--

## 🧠 Security Insights
This lab reinforced the importance of proper access control mechanisms.
Hidden or unlinked endpoints should never be assumed secure. 
If a resource is accessible without proper authorization checks, it becomes part of the attack surface.
Enumeration techniques remain a fundamental step in web application security testing, often revealing overlooked weaknesses.

































