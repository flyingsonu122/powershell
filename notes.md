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

   # OR  

Copy-Item 'D:\temp\Test Folder' -Destination 'D:\temp\Test Folder1'
```

**to copy file**

```powershell
Copy-Item 'D:\temp\Test Folder\Test File.txt' 'D:\temp\Test Folder1\Test File1.txt'

   # OR  

Copy-Item -Filter *.txt -Path 'D:\temp\Test Folder' -Recurse -Destination 'D:\temp\Test Folder1'
```

**to delete folder**

```powershell
Remove-Item 'D:\temp\Test Folder1'

  #  OR  

Remove-Item 'D:\temp\Test Folder' -Recurse
```


**to delete file**

```powershell
Remove-Item 'D:\temp\Test Folder\test.txt'

   # OR  

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

   # OR

get-date

$output: Thursday, 20 January, 2022 01:42:33 AM

# both cmdlets works bcz not case sensitive

Get-Date -DisplayHint Date

# this above cmdlet displays only date

$output: Thursday, 20 January, 2022

Get-Date -DisplayHint Time

# this above cmdlet displays only time

$output: 01:43:49 AM
```

**to set  date**

you need administrator permissions

```powershell
set-date -Date (Get-Date).AddDays(1)

    # OR

set-date -Date (Get-Date).AddDays(-1)
```











