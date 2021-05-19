# Using UAssetAPI 

**This is not a coding tutorial! skip this if you have low to zero experience with C# programming**</br>
_Need help with coding? ask Tipssi._ 


## Clone and build DLL
- Clone [UAssetAPI](https://github.com/atenfyr/UAssetAPI) repo.
- Open project in Visual Studio and build DLL.
- (Don't forget to set Output Type to Class Library in Project Settings)

## New Project
Create a new project and add reference to the DLL.

![](Images/api1.png)

## Code Snippet(Example)
This code loops through all Categories and their content, looks for RelativeLocation, gets coordinates, prints them and makes some changes(adds 1000 to Z coordinates), and saves changes when done. 

![](Images/api2.png)

## Results:

After simple packing:</br>
Every object which contained a valid RelativeLocation got elevated by 1000 units on the Z axis(height).

![](Images/api3.png)