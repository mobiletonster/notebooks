# .NET Interactive Notebooks can be very cool
This first method (C#) is demonstrating a simple loop where we output an integer, casted as a double, divide by 4.2 and format it to 2 decimal places and a leading zero, followed by the current datetime at execution in ticks.
```C#
for(double i=0;i<10;i++){
    Console.WriteLine($"{i/4.2:0.00} at {DateTime.Now.Ticks}");
}
```

This next method (F#) attempts to duplicate the same code as the C# example above.
```C#
for i = 0 to 9 do  
      printfn $"{((i:float)/4.2):N2} at {DateTime.Now.Ticks}"
```

The almost equivalent code in Javascript. Ticks aren't quite ticks as far as I can tell as they seem to be a different number.
```C#
for(i=0;i<10;i++){
    console.log(`${(i/4.2).toFixed(2)} at ${(new Date()).getTime()}`)
}
```

Here is a static version in HTML, because we can't really execute imperative code in a HTML as it is a declarative langauge.
```C#
<table>
<tr><td>0.00</td><td> at </td><td>1641826868456</td></tr>
<tr><td>0.24</td><td> at </td><td>1641826868456</td></tr>
<tr><td>0.48</td><td> at </td><td>1641826868456</td></tr>
<tr><td>0.71</td><td> at </td><td>1641826868456</td></tr>
<tr><td>0.95</td><td> at </td><td>1641826868456</td></tr>
<tr><td>1.19</td><td> at </td><td>1641826868456</td></tr>
<tr><td>1.43</td><td> at </td><td>1641826868456</td></tr>
<tr><td>1.67</td><td> at </td><td>1641826868456</td></tr>
<tr><td>1.90</td><td> at </td><td>1641826868456</td></tr>
<tr><td>2.14</td><td> at </td><td>1641826868456</td></tr>
</table>
```

And finally, in Powershell
```C#
for($i = 0; $i -lt 10; $i++){ 
    "{0:N2} at {1}" -f ($i/4.2), (get-date).Ticks
}
```

```C#
<# Install-Module PowershellNotebook #>

<# Get-Command -Module PowerShellNotebook | 
    Select-Object -ExpandProperty Name | 
    Foreach-Object { 
        Get-Help $_ | Select-Object Name, { $_.Synopsis.Trim() }
    } #>

    <#
ConvertFrom-NotebookToMarkdown -NotebookName /Users/tonyspencer/repos/notebooks/notebooks/csharp_fsharp.ipynb
#>
```

