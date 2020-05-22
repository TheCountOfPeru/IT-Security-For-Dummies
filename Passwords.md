# Passwords
Authetication is a important of part IT security and privacy. It is the process of proving who you say you are. Passwords are often used alongside a username to authenticate users with a website.

This article will be examining how passwords work, how useful they are, guidelines for their use, and how to store passwords

## How do passwords work?
When you login into a website with your username and password the website looks into it's database. If your username matches the information within the database then the website lets you in. 

## Why are passwords useful?
Passwords are good because they are easy to remember and it is very commonly used with all types of services. 

Passwords are bad because a lot of people do not use strong passwords or they re use passwords. When it comes to making passwords most people aren't good at it. Also it can be easy to steal a password from keyloggers or even looking over a person's shoulder.

## Guidelines for password use
These guidelines are from NIST and are useful for users and administrators of any place requiring passwords. Some guidelines come with an in depth explanation.

### NIST 2019 Password Guidelines
1. No complexity requirements. 
   1. People forced to follow complexity requirements follow those requirements in predictable ways. Which makes them easier to guess.
   2. People will follow the requirements but have a hard time remembering a complex password. So they will simply append the requirements to a simple password. Which makes them easier to guess
2. At least 8 (sometimes 6) characters.
   1. With 8 characters you can have 6,095,689,385,410,816 different passwords. Not having enough characters is bad for password security.
3. Support at least 64 characters.
   1. Allowing for extremely long passwords makes them better and harder to guess.
   2. Passwords should not be stored as what they were entered anyways so limiting the number of characters is bad practice. 
4. Allow any character.
   1. Unicode should be normalized with NKFC of NFKD.
   2. If SQL injection can be done by entering passwords you have bigger problems.
5. Blacklist frequently used passwords.
   1. Any passwords from: a dictionary, list of common/bad passwords, passwords found in past database breaches, and context-specific words (name of service, the username, etc) should not be used again. It's important to explain to the user how to make a better password after rejection.
6. 