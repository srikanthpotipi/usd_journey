# usd_journey

# Pre Built USD - Windows
## Issues 
### pxr module not found 
> Add the `usd\lib\python` to the PYTHOHPATH

```
$PythonLibPaths = "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\lib\python\;C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\python\" 
$Env:PYTHONPATH= "$PythonLibPaths$([System.IO.Path]::PathSeparator)$Env:PYTHONPATH"
```

### DLL load failed while importing _tf: The specified module could not be found.
```
Traceback (most recent call last):
  File "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\bin\usdview", line 28, in <module>
    import pxr.Usdviewq as Usdviewq
  File "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\lib\python\pxr\Usdviewq\__init__.py", line 27, in <module>
    from pxr import Tf
  File "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\lib\python\pxr\Tf\__init__.py", line 178, in <module>
    PreparePythonModule()
  File "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\lib\python\pxr\Tf\__init__.py", line 103, in PreparePythonModule
    module = importlib.import_module(
  File "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\python\lib\importlib\__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
ImportError: DLL load failed while importing _tf: The specified module could not be found.
```

> Add the usd lib and bin paths to the `PATH` variable. If you are in a venv, add them in the Activate.ps1

```
$UsdLibPath = "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\lib\"
$UsdBinPath  = "C:\Users\srikanth.potipireddi\dev\usd_prebuilt\usd\bin"
$Env:PATH = "$UsdLibPath$([System.IO.Path]::PathSeparator)$Env:PATH"
$Env:PATH = "$UsdBinPath$([System.IO.Path]::PathSeparator)$Env:PATH"
```

### No module named 'PySide2' 
> pip install PySide2
