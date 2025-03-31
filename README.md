# Windsurf AI Pro Free Trial Reset - Complete Guide

This repository provides four different methods to reactivate the free trial of Windsurf AI Pro. If you've lost access or want to test the software for a longer period, follow the instructions below.

## ⚡ Methods Covered

1. **Windows Sandbox** - Creating a temporary machine.
2. **Hyper-V** - Using a virtual machine.
3. **New User Method** - Creating a new user profile.
4. **Pre-Activated Accounts** - A quick and easy solution.

---

## 🖥️ Method 1: Windows Sandbox (Windows Pro, Enterprise, and Education)

1. Press **Win + R**, type `optionalfeatures`, and hit **Enter**.
2. Find **Windows Sandbox** in the list, check the box, and click **OK**.
3. Restart your PC.
4. Open Windows Sandbox, install Windsurf AI, and create a new account.

### Installing Windows Sandbox on Windows 11 Home
If you are using Windows 11 Home, follow these steps:

1. Open Notepad (**Win + R → type `notepad` → Enter**).
2. Copy and paste the following code into Notepad:

```batch
@echo off

echo Checking for permissions
>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"

echo Permission check result: %errorlevel%

REM --> If error flag set, we do not have admin.
if '%errorlevel%' NEQ '0' (
echo Requesting administrative privileges...
goto UACPrompt
) else ( goto gotAdmin )

:UACPrompt
echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\getadmin.vbs"
echo UAC.ShellExecute "%~s0", "", "", "runas", 1 >> "%temp%\getadmin.vbs"

echo Running created temporary "%temp%\getadmin.vbs"
timeout /T 2
"%temp%\getadmin.vbs"
exit /B

:gotAdmin
if exist "%temp%\getadmin.vbs" ( del "%temp%\getadmin.vbs" )
pushd "%CD%"
CD /D "%~dp0" 

echo Batch was successfully started with admin privileges
echo .
cls
Title Sandbox Installer

pushd "%~dp0"

dir /b %SystemRoot%\servicing\Packages\*Containers*.mum >sandbox.txt

for /f %%i in ('findstr /i . sandbox.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"

del sandbox.txt

Dism /online /enable-feature /featurename:Containers-DisposableClientVM /LimitAccess /ALL

pause
```

3. Save it as **sandbox-installer.bat** (select **All Files** as the file type).
4. Right-click the file and **Run as Administrator**.
5. Restart your PC after installation.

---

## 🔄 Method 2: Hyper-V (Windows Pro, Enterprise, and Education)

1. Press **Win + R**, type `optionalfeatures`, and hit **Enter**.
2. Check **Hyper-V**, click **OK**, and restart your PC.
3. Open **Hyper-V Quick Create**, follow the steps, and choose Windows 10 MSIX.
4. Set up your virtual machine, install Windsurf AI, and create a new account.

### Enabling Hyper-V on Windows Home
Since Windows Home doesn't include Hyper-V by default, follow these steps to enable it:

1. Open Notepad (**Win + R → type `notepad` → Enter**).
2. Copy and paste the following code into Notepad:

```batch
@echo off

echo Checking for permissions
>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"

echo Permission check result: %errorlevel%

REM --> If error flag set, we do not have admin.
if '%errorlevel%' NEQ '0' (
echo Requesting administrative privileges...
goto UACPrompt
) else ( goto gotAdmin )

:UACPrompt
echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\getadmin.vbs"
echo UAC.ShellExecute "%~s0", "", "", "runas", 1 >> "%temp%\getadmin.vbs"

echo Running created temporary "%temp%\getadmin.vbs"
timeout /T 2
"%temp%\getadmin.vbs"
exit /B

:gotAdmin
if exist "%temp%\getadmin.vbs" ( del "%temp%\getadmin.vbs" )
pushd "%CD%"
CD /D "%~dp0" 

echo Batch was successfully started with admin privileges
echo .
cls
Title Hyper-V Installer

pushd "%~dp0"
dir /b %SystemRoot%\servicing\Packages\*Hyper-V*.mum >hv.txt
for /f %%i in ('findstr /i . hv.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"
del hv.txt
Dism /online /enable-feature /featurename:Microsoft-Hyper-V-All /LimitAccess /ALL
pause
```

3. Save it as **hyperv-installer.bat** (select **All Files** as the file type).
4. Right-click the file and **Run as Administrator**.
5. Restart your PC after installation.
6. After restarting, you can open Hyper-V Manager and create virtual machines.

---

## 👤 Method 3: Creating a New User (Windows, Linux, macOS)

- On Windows:
  1. Go to **Settings > Accounts > Family & other users**.
  2. Click **Add another user to this PC**.
  3. Choose **Add a user without a Microsoft account**.
  4. Set up the new user and log in.
  5. Install Windsurf AI and create a new account.

- On Linux/macOS:
  - The process varies by system. Look for a tutorial on how to create a new user for your OS.

---

## 🛒 Method 4: Pre-Activated Accounts

If none of the methods above work for you, you can get a **pre-activated account** for just **$1**. This saves time and effort, allowing you to access all Windsurf AI Pro features instantly.

🔗 **[Get a pre-activated account here](#)**

---

## ❗ Troubleshooting

- **Temporary email banned?** Try another provider.
- **Windows Home missing Sandbox/Hyper-V?** Follow the instructions above.
- **Issues with account activation?** Leave a comment or open an issue!

If you encounter any problems, feel free to contribute to the discussion. Let's help each other out! 🚀

