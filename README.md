# IL Samples

Samples demonstrating the generation of MSIL assemblies using ILASM for .NET ≥ 8.0.

**Build** using

```powershell
dotnet build .\helloworld.proj
```

This will restore the necessary packages and build the project using ILASM. You may need to set the RuntimeIdentifier to match your platform, e.g., `win-x64`, `linux-x64`, etc. You can do this by passing it as a command line argument.

```powershell
dotnet build .\helloworld.proj -p:RuntimeIdentifier=linux-x64
```

Then **run** the generated assembly using

```powershell
 dotnet .\bin\helloworld.exe
```

The hello world example will print "Hello World!" to the console.

You can **debug** the generated assembly in vscode. Configurations are readily provided in the `.vscode` folder.

You will need to **modify** the location of the `helloworld.txt` file in the `helloworld.il` file to match your environment, where you will find a line like this:

```il
    .line 1,1 : 1,19 '/workspace/ILSamples/helloworld.txt'
```

Replace the path with the correct one for your system, e.g., `/home/user/ILSamples/helloworld.txt` or `C:\\Users\\User\\ILSamples\\helloworld.txt`. Note that backslashes need to be escaped with an additional backslash, but using slashes on windows appears to work as well.
