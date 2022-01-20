open powershell and **type** 

**to see version**

```powershell
$PSVersionTable
```

**to create a directory**

```powershell
New-Item -Path 'D:\temp\Test Folder' -ItemType Directory
```

**to create a file**

```powershell
New-Item -Path 'D:\temp\Test Folder\Test File.txt' -ItemType File
```

**to copy folder**

```powershell
Copy-Item 'D:\temp\Test Folder' 'D:\temp\Test Folder1'

    OR  

Copy-Item 'D:\temp\Test Folder' -Destination 'D:\temp\Test Folder1'
```

**to copy file**

```powershell
Copy-Item 'D:\temp\Test Folder\Test File.txt' 'D:\temp\Test Folder1\Test File1.txt'

    OR  

Copy-Item -Filter *.txt -Path 'D:\temp\Test Folder' -Recurse -Destination 'D:\temp\Test Folder1'
```

**to delete folder**

```powershell
Remove-Item 'D:\temp\Test Folder1'

    OR  

Remove-Item 'D:\temp\Test Folder' -Recurse
```


**to delete file**

```powershell
Remove-Item 'D:\temp\Test Folder\test.txt'

    OR  

Remove-Item 'D:\temp\Test Folder\test.txt' -Recurse
```

**to move folder**

```powershell
Move-Item D:\temp\Test D:\temp\Test1
```

run this below command after adding some file into **Test** folder, it will move files along with folder 

```powershell
Move-Item D:\temp\Test D:\temp\Test1
```

**to move file**

make sure both folders are already created and Test.txt is also present.

```powershell
Move-Item D:\temp\Test\Test.txt D:\temp\Test1
```

**to rename folder**

make sure **Test1** named folder is **not** already present.

```powershell
Rename-Item D:\temp\Test D:\temp\Test1
```

**to rename file**

not case sensitive (means **test.txt** is same as **Test.txt**)

```powershell
Rename-Item D:\temp\Test\test.txt test1.txt
```

**to get file contents**

```powershell
Get-Content D:\temp\Test\test.txt
```

*to get **size** of file contents*

```powershell
(Get-Content D:\temp\test\test.txt).length
```

**to check folder existence**

```powershell
Test-Path D:\temp\test

# returns true or false
```


**to check file existence**

```powershell
Test-Path D:\temp\test\test1.txt

# returns true or false
```

**to system date**

```powershell
Get-Date

    OR

get-date

output: Thursday, 20 January, 2022 01:42:33 AM

# both cmdlets works bcz not case sensitive

Get-Date -DisplayHint Date

# this above cmdlet displays only date

output: Thursday, 20 January, 2022

Get-Date -DisplayHint Time

# this above cmdlet displays only time

output: 01:43:49 AM
```

**to set  date**

you need administrator permissions

```powershell
set-date -Date (Get-Date).AddDays(1)

     OR

set-date -Date (Get-Date).AddDays(-1)
```

**to create file**

file can be of any **type** be it .txt, .xml, etc.

```powershell
New-Item D:\temp\test\test.txt
```
**to add content in file**

```powershell
Set-Content D:\temp\test\test.txt 'Hello Sonu Kushwaha'
```
**to get content of a file**

```powershell
Get-Content D:\temp\test\test.txt
```
**to clear content of a file**

```powershell
Clear-Content D:\temp\test\test.txt
```
**to append content of a file**

this text will be added in **new line**

```powershell
Add-Content D:\temp\test\test.txt 'World!'
```
**to create an Alias**

```powershell
New-Alias -Name help -Value Get-Help 
```
**to see all Alias**

```powershell
Get-Alias
```






**declare an array**

```powershell
$A = 1, 2, 3, 4

   OR

$A = 1..4  
```
**to get type of an array**

```powershell
$A.getType()
```

**to create an array**

```powershell
$array = @("item1", "item2", "item3")

    OR

$myList = @(0..4)

write-host("Print array")
$myList

```
**to get elements of an array**

```powershell
for($i = 0; $i -lt $array.length; $i++){ $array[$i] }
```

**more about an array**

```powershell
$myList = 5.6, 4.5, 3.3, 13.2, 4.0, 34.33, 34.0, 45.45, 99.993, 11123

write-host("Print all the array elements")
$myList

write-host("Get the length of array")
$myList.Length

write-host("Get Second element of array")
$myList[1]

write-host("Get partial array")
$subList = $myList[1..3]

write-host("print subList")
$subList

write-host("Assign values")
$myList[1] = 10
$myList

```

**foreach loop**

```powershell
foreach ($element in $array) { $element }

    OR

$array | foreach { $_ }
```

**while loop**

```powershell
$counter = 0;

while($counter -lt $array.length){
   $array[$counter]
   $counter += 1
}
```

**dowhile loop**

```powershell
$counter = 0;

do {
   $array[$counter]
   $counter += 1
} while($counter -lt $array.length)
```

**if statement**

```powershell
$x = 10

if($x -le 20){
   write-host("This is if statement")
}

```

**if else statement**

```powershell
$x = 30

if($x -le 20){
   write-host("This is if statement")
}else {
   write-host("This is else statement")
}
```
**else if statement**

```powershell
$x = 30

if($x -eq 10){
   write-host("Value of X is 10")
} elseif($x -eq 20){
   write-host("Value of X is 20")
} elseif($x -eq 30){
   write-host("Value of X is 30")
} else {
   write-host("This is else statement")
}
```
**nested if statement**

```powershell
$x = 30
$y = 10

if($x -eq 30){
   if($y -eq 10) {
      write-host("X = 30 and Y = 10")
   }
}   
```
**switch case**

```powershell
switch(3){
   1 {"One"}
   2 {"Two"}
   3 {"Three"}
   4 {"Four"}
   3 {"Three Again"}
}
```


**switch with break**

```powershell
switch(3){
   1 {"One"}
   2 {"Two"}
   3 {"Three"; break }
   4 {"Four"}
   3 {"Three Again"}
}
```

**switch with array as input**

```powershell
switch(4,2){
   1 {"One"}
   2 {"Two"}
   3 {"Three"; break }
   4 {"Four"}
   3 {"Three Again"}
}
```

**To get process running on system**

```powershell
Get-Process [r-s]*

   OR

Get-Process

   more on it

Get-Service * | Sort-Object ServiceType `
| Format-Table Name, ServiceType, Status -AutoSize
```
**backticks**
```powershell
Write-host "Title Subtitle"

   to add new line

Write-host "Title `nSubtitle"

   to add tab

Write-host "Title `tSubtitle"
```
**get location**

same as **pwd** ( present working directory )
```powershell
Get-Location
```
**sort and get unique values**

```powershell
$list = "one","two","two","three","four","five"

$list | sort | get-unique
```
**measure object**

```powershell

get-content D:\temp\test\test.txt | measure-object -character -line -word
```
**files present in current directory and its property**

```powershell
Get-ChildItem

   other

Get-ChildItem | Measure-Object
```
**compare files**

```powershell
Compare-Object -ReferenceObject $(Get-Content D:\temp\test\test.txt) -DifferenceObject $(Get-Content D:\temp\test\test1.txt)

   more on it

Compare-Object -ReferenceObject $(Get-Content D:\temp\test\test.txt) -DifferenceObject $(Get-Content D:\temp\test\test1.txt) -IncludeEqual

```

**format list**

```powershell
$A = Get-ChildItem D:\temp\test\*.txt
Format-List -InputObject $A
```
**get service list**

```powershell
Get-Service

   OR

Get-Service | Format-List
```










<br><br><br><br>


## Source [tutorialspoint.com/powershell/powershell_quick_guide.htm](https://www.tutorialspoint.com/powershell/powershell_quick_guide.htm)


