# CozyHasher v1.2.2

A simple password hashing DLL that accepts a username and password, and generates a 512 bit key for storage. It also has a method for built-in comparison. 

### Created By

Blair Palmerlee

## Adding to Project

You can add the nuget package manually from Github or by typing:

```
dotnet add package CozyHasher --version 1.2.2
```

in your CLI.

Please note that the most current version is 1.2.2 and using any older versions is not recommended. 

## Using CozyHasher

Once the DLL has been added to your chosen project, add:

```C#
using CozyHasher;
```

To use the hasher, instanciate the class and use the following methods as needed:

```C#
String HashVal = hasherinst.MakeHash(username, password);
```
MakeHash() takes in two strings and returns a hash as a single string output. Keep in mind that the algorithm dynamically keys when it creates a class, making the output potential different on each use, despite the inputs being the same. For this reason, you cannot use this method to check validity.

To check if a username, password, and hash are valid use:

```C#
bool ValidationVar = hasherinst.CheckHash(Username, Password, KnownHash);
```
CheckHash() will take the user inputs(Username, Password) and the known hash for the given user(KnownHash), all as strings, and will return a True value if the username and password match the hash, and a False value if they do not.

## Testing

While not strictly necessary, it is highly recommended that the release be tested before implimentation. Runnting the following test code should return "Check Hash Status: True" if the version is authentic.

```C#
using CozyHasher;

Hasher hasher = new Hasher();
bool Validation = hasher.CheckHash("Validate", "Validate!:", "11BAC3CBBB10EA3BC1BBEC410DA2233123AGE6112FHB211EECAB510BJHGGFEHE");

Console.WriteLine($"Check hash status: {Validation}");

```
## Version Notes

1.2.2 fixes a critical calculation error that occured while forming hashes in specific test cases. For the safety and integrity of associated projects, it is recommended that earlier versions not be used. 
