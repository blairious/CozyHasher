# CozyHasher
A simple password hashing DDL that accepts a password, username, and large number and generates a 64 character key for storage and comparison.
### Created By
Blair Palmerlee
## Adding Hasher to Project
Add the package to your project using the command:

dotnet add package CozyHasherLibrary --version 1.0.0

Once the package is added, add:

using  CozyHasherLibrary;

to the top of the appropriate code files. 

## Method Usage
When the method Hasher.MakeHash(pword, uname, seckey); is used. It takes as input two strings(password, username) and a ulong(key). It's recommend that the key remains an element outside of the users' control.

Using the three inputs, the hasher will create an arcane string of 64 characters, wherein much of the original data that was used to form the hash is discarded, making it impossible to reverse-engineer a full password and/or username from the resulting string. 
