#### [Back to table of contents](./README.md)

# Passwords
Authentication is important for IT security and privacy. It is the process of proving who you say you are. Passwords are often used alongside a username to authenticate users with a website.

This article will be examining how passwords work, how useful they are, guidelines for their use, and how to store passwords.

## How do passwords work?
When you log in to a website with your username and password the website looks into its database. If your username and password match the information within the database then the website lets you in. 

## Why are passwords useful?
Passwords are good because they are easy to remember and it is very commonly used with all types of services. 

Passwords are bad because a lot of people do not use strong passwords or they reuse passwords. When it comes to making passwords most people aren't good at it. Also, it can be easy to steal a password from keyloggers or even looking over a person's shoulder.

## Guidelines for password use
These guidelines are from NIST and are useful for users and administrators of any place requiring passwords. Some guidelines come with an in-depth explanation. You can compare these to your favorite websites to see how secure they are with passwords.

### NIST 2019 Password Guidelines
1. No complexity requirements. 
   * People forced to follow complexity requirements follow those requirements in predictable ways. Which makes them easier to guess.
   * People will follow the requirements but have a hard time remembering a complex password. So they will simply append the requirements to a simple password. Which makes them easier to guess
2. At least 8 (sometimes 6) characters.
   * With 8 characters you can have 6,095,689,385,410,816 different passwords. Not having enough characters is bad for password security.
3. Support at least 64 characters.
   * Allowing for extremely long passwords makes them better and harder to guess.
   * Passwords should not be stored as what they were entered anyways so limiting the number of characters is bad practice. 
4. Allow any character.
   * Unicode should be normalized with NKFC of NFKD.
   * If SQL injection can be done by entering passwords you have bigger problems.
5. Blacklist frequently used passwords.
   * Any passwords from a dictionary, list of common/bad passwords, passwords found in past database breaches, and context-specific words (name of service, the username, etc) should not be used again. It's important to explain to the user how to make a better password after rejection.
6. Do not allow password hints or security questions.
   * If a database with passwords and their hints/security questions leaked those pieces of information can help hackers guess passwords. 
   * Answers to security questions aren't well-kept secrets anyways.
7. Do not require users to change their password frequently
   * Forcing users to do this leads to them creating weak passwords that are usually easy to remember since they are forced to change them too often.
   * Makes users fail to log in more results in hiding when a hacker is attempting to login.
8. Let people copy and paste their password.
   * This stops people who look over the user's shoulder or keyloggers.
   * This makes it easier to use complicated passwords.
9. Use two/multi-factor authentication.
   * Helps increase security for your users even if they reuse passwords.
   * Helps defeat phishing attacks because a hacker would also need to defeat more than just a password.
10. Allow at least 10 passwords attempts before refusing any more. 
    * The weakest passwords can be brute-forced in less than 10 attempts.
    * Limits the number of times regular uses lock themselves out of the system. Just the right amount.

## Storing Passwords
The ways to store a password range from the very weak to the extremely strong. The techniques used to store passwords are important to know because they are for when a system needs to defend itself against those trying to access user accounts. Here is a list of techniques from weakest to strongest.
* Store as plaintext
  * Store passwords as is. If a hacker somehow gets access to the password database all accounts are compromised. Never store passwords this way.
* Encrypt the database
  * A hacker can compromise accounts if they can steal the encryption key and get access to the password database. Never store passwords this way.
* Store hashed passwords
  * Hash passwords before storing. A hacker with access to the database can reverse the hashes and may be able to uncover passwords. Not recommended to store passwords this way.
* Store hashed & salted passwords
  * By appending a salt to a password before hashing makes it very strong. 
* Store hashed, salted & peppered passwords
  * By appending the pepper and salt to a password before hashing makes it extremely strong.

## What is encryption, hashing, salting, and peppering?

#### Encryption 
Encryption can be thought of as locks and keys. For example, Alice wants to give something to Bob and make sure nobody else can see what Bob got. She can put her item in a box and lock it. That would be encryption. Bob would receive it and unlock it. That is decryption. 

In reality, the key would be a string of characters like "9jpivs#" and encryption would be using that key to scramble whatever data you want to protect. So looking at encrypted data would not reveal anything of the actual data.

So if the hackers obtain the key and the database then all accounts are compromised.

#### Hashing
Hashing is similar to encryption except when you scramble the data there is no you can undo it. It's a one-way operation.

So a database will store the hashed password. Every time someone tries to login the password they input is hashed. If it matches one in the database they are let in.

This makes it a bit harder for hackers to steal passwords if they have access to the database. So to break in hackers can use what is called a hash table to help themselves. A hash table just lists passwords and their corresponding hashes. So they can go backward from hash to passwords and could access some accounts in the database. These hash tables can be shared on the internet making many passwords useless.

##### Salting
Salting is a technique to strengthen hashing. The idea is before hashing a random string is generated (the salt) and appended to the password then it is hashed. In the database, the salt is stored for future retrieval. When a user logins their salt is located in the database and appended to the password and hashed again. If the hash matches what is in the database the user is let it. 

This makes it extremely difficult for hackers to steal passwords from a database. Since now their hash table is rendered useless due to the salt. Trying to make a hash table to include a salt could take an extremely long time. As long as the passwords people use are not easily guessable all accounts are safe.

##### Peppering
Peppering is supposed to be used in conjunction with salting. It is a string that would be included with the server but not kept in a database or anything like that. You would append it with the salt and password and hash-like normal. Except the pepper is secret. So now even if a hacker obtained the database they chance they would be able to reverse any hash would be very low or take an immeasurable amount of time to guess. Having a strong password is still a good idea of course.

If you make a website with user accounts you should at least salt your passwords. Anything less is a terrible idea.

## Password Tips
As strong passwords are annoying to make and remember a good solution is a password manager. A password manager can generate strong passwords and remembers them all for you. Of course, a downside is the password manager is the single point of failure if it is compromised.
A strong password is still not enough to protect yourself though. This is why using another authentication method with passwords is highly recommended. One common option is using a one-time pass program that sends a code to your phone and you'll need to enter that code alongside your password to access your account.

