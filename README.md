# CozyHasher v2.0.1

A simple password hashing DLL that accepts a username and password, and generates a 256 byte key for safe storage. It also has a method for built-in comparison. This tool was built for use in C# projects. 

### Created By

Blair Palmerlee

## Adding to Project

You can add the nuget package manually from Github or by typing:

```
dotnet add package CozyHasher --version 2.0.1
```

in your CLI.

Please note that the most current version is 2.0.0 and using any older versions is not recommended. 

## Using CozyHasher

Once the DLL has been added to your chosen project, add:

```C#
using CozyHasher;
```

MakeHash(string username, byte[] password) takes a username as a string and a password as a byte array, and returns a hash as a single string output. Keep in mind that the algorithm dynamically keys when it creates each string, making the output potential different on each use, despite the inputs being the same. For this reason, you cannot use this method to create two identical codes to manually check validity.

To check if a username, password, and hash are valid use:

```C#
bool ValidationVar = Hasher.CheckHash(Username, Password, KnownHash);
```
CheckHash(string Username, byte[] Password, string KnownHash) will take the user inputs(Username, Password) and the known hash for the given user(KnownHash) and will return a True value if the username and password match the hash, and a False value if they do not.


## Version Notes

### Summary: 

2.0.1 Fixes:

* A known error which caused patterning has been fixed. 
* Additional password data protection in at a memory level has been added.

2.0.0 has huge improvements over previous versions. Beyond hashing to a larger size, the algorithm has become more advanced and far more obscure. While former versions could generate several hashes from the same user data, CozyHasher can now produce and reliably check enormous numbers of unique hashes from the same username and password. The data written to memory is now treated much more carefully, in the form of arrays with active garbage collection and clearing of data as it's used.
