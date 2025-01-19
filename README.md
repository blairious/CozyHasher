# CozyHasher v1.1.1

A simple password hashing DLL that accepts a username and password, and generates a 512 bit key for storage. It also has a method for built-in comparison. 

### Created By

Blair Palmerlee

## Testing

While not strictly necessary, it is highly recommended that the release be tested before implimentation. Runnting the following test code should return "Check Hash Status: True" if the version is authentic.

```C#
using CozyHasher;

Hasher hasher = new Hasher();
bool Validation = hasher.CheckHash("Validate", "Validate!:", "E1AB510BJHGGFEHDAC413CJB020CIECCA3DF5CGECAB510BJHGGFEHDAC413CJB0");

Console.WriteLine($"Check hash status: {Validation}");

```
