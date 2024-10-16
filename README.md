# Use-of-Weak-Hash

## Planform: rangeforce
## Scenario
As a security specialist for ComTech, you have been tasked with seeking out all the vulnerabilities in company-owned assets. While poking around on ComTech's legacy website backend that exposes phpMyAdmin for managing the SQL database, you notice a potentially weak hashing algorithm.

In this challenge, you must find and crack the weak password hash.

## Steps

<img width="573" alt="image" src="https://github.com/user-attachments/assets/60f45936-76ed-4a40-a3a2-68d2fe706647">


After browsing through the database, I located a table that contained user credentials, specifically usernames and password hashes. My goal was to check if the passwords were protected with a strong hashing algorithm.

<img width="442" alt="image" src="https://github.com/user-attachments/assets/0bd43de6-82d3-4d77-b350-f83a92593d45">


Upon closer inspection, I noticed that the passwords were hashed using the MD5 algorithm. MD5 is widely known for its vulnerabilities and should not be used for password hashing due to how easily it can be cracked with precomputed hash tables.

I exported one of the MD5 hashes from the database and used an online tool called CrackStation.net to see if I could crack it.

<img width="759" alt="image" src="https://github.com/user-attachments/assets/484cd45a-4bd5-45e1-a349-11f783c6ea77">



## How I think this vulnerability can be prevented:

After cracking the hash, I recommended that ComTech switch from MD5 to more secure hashing algorithms, such as bcrypt, PBKDF2, or Argon2. These algorithms provide resistance against cracking attempts, especially those based on rainbow tables and precomputed hash databases. Additionally, I suggested securing the phpMyAdmin interface to prevent unauthorized access to the database in the future.
