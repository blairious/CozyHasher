# CozyHasher v1.3.2

A simple password hashing DLL that accepts a username and password, and generates a 512 bit key for storage. It also has a method for built-in comparison. This tool was built for use in C# projects. 

### Created By

Blair Palmerlee

## Adding to Project

You can add the nuget package manually from Github or by typing:

```
dotnet add package CozyHasher --version 1.3.2
```

in your CLI.

Please note that the most current version is 1.3.2 and using any older versions is not recommended. 

## Using CozyHasher

Once the DLL has been added to your chosen project, add:

```C#
using CozyHasher;
```

To use the hasher, instanciate the class and use the following methods as needed:

```C#
String HashVal = hasherinst.MakeHash(username, password);
```
MakeHash() takes in two strings and returns a hash as a single string output. Keep in mind that the algorithm dynamically keys when it creates each string, making the output potential different on each use, despite the inputs being the same. For this reason, you cannot use this method to create two identical codes to manually check validity.

To check if a username, password, and hash are valid use:

```C#
bool ValidationVar = hasherinst.CheckHash(Username, Password, KnownHash);
```
CheckHash() will take the user inputs(Username, Password) and the known hash for the given user(KnownHash), all as strings, and will return a True value if the username and password match the hash, and a False value if they do not.

As a note: Make sure to always store resulting string in a variable. The final hash may include escape characters. 

## Testing

While not strictly necessary, it is highly recommended that the release be tested before implimentation. Runnting the following test code should return "Check hash status: True" if the version is the most recent release.

```C#
using CozyHasher;

Hasher hasher = new Hasher();
bool Validation = hasher.CheckHash("Validate", "Validate!:", "11[1S*&[1[10U?(0e1I.LJ310BH2!+)1!(0`LG11#DaR211LLJ67=100laWWVLOg");

Console.WriteLine($"Check hash status: {Validation}");

```
## Version Notes

1.3.2 Expands the ascii character range that is used for greater obsurity in the produced hash. 
