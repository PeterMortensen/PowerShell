Using PowerShell Integrated Scripting Environment (ISE)
====
The PowerShell ISE works on Windows. If you are not using Windows, please see [Using VS Code](./using-vscode.md).

Editing with ISE
---
-	Launch PowerShell ISE
  *	 Press Windows Key -> type PowerShell ISE, click on PowerShell ISE to launch the ISE
-	Create a new PowerShell Script
  *	Click on File -> New
  *	Add a few lines of PowerShell scripts in your newly created file, for example,

```PowerShell
# Convert Fahrenheit to Celsius
function ConvertFahrenheitToCelsius([double] $fahrenheit)
{
$celcius = $fahrenheit - 32
$celcius = $celcius / 1.8
$celcius
}

$fahrenheit = Read-Host 'Input a temperature in Fahrenheit'
$result =[int](ConvertFahrenheitToCelsius($fahrenheit))
Write-Host "$result Celsius"
```
  * **Note**: You can find more examples [here](http://examples.oreilly.com/9780596528492/).

-	Save the script file
  *	Click on File-> Save As -> type  "helloworld.ps1"
-	Close the helloworld.ps1
  *	File-> Close
-	Reopen the helloworld.ps1
  *	File-> Open, then choose helloworld.ps1.
- For more details, go to [How to Write and Run Scripts in the Windows PowerShell ISE](https://msdn.microsoft.com/en-us/powershell/scripting/core-powershell/ise/how-to-write-and-run-scripts-in-the-windows-powershell-ise).


Debugging with ISE
----

To execute the entire script file, you can press **F5**; to execute several lines of your scripts, simply select them and press **F8**. However sometimes you would like to stop the execution on a particular line in order to exam some variables to check if the program runs as expected. In that case, you may follow the steps below. Let's take the helloworld.ps1 as an example and assume line 17 is the place where you want to stop.

-	Set a break point: Move mouse over on the line 17, and press **F9**. You will see the line 17 is highlighted which means a breakpoint gets set.
-	Press **F5** to run the script
-	Enter 80 (or any number in Fahrenheit) from the command line prompt
-	Notice that the ISE output pane becomes “[DBG]: PS C:\Test>>” prompt. This means the program is in the debugging mode. It stops at Line 17:

```PowerShell
PS C:\test> C:\test\helloword.ps1
Input a temperature in Fahrenheit: 80
Hit Line breakpoint on 'C:\test\helloword.ps1:17'
''[DBG]: PS C:\test>>'

```

- From the output pane, you can type $celcius and $fahrenheit to exam these variables to see if they are correct.

```PowerShell
[DBG]: PS C:\Test>> $celcius
26.6666666666667

[DBG]: PS C:\Tset>> $fahrenheit
80
```
- Press **F5** to let the program continue running

```PowerShell
[DBG]: PS C:\test>>
27 Celsius

PS C:\test>
```
See [How to Debug in ISE][debug] for more information.

[debug]:https://msdn.microsoft.com/en-us/powershell/scripting/core-powershell/ise/how-to-debug-scripts-in-windows-powershell-ise#bkmk_2