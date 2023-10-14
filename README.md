# Google-Chrome-with-Powershell-script
1. Open a PowerShell window with administrator privileges. To do this, search for "PowerShell" in the Start menu, right-click on "Windows PowerShell," and choose "Run as administrator."
2. Copy and paste code from file install
3. Press enter and wait till it finishes

Here's a breakdown of what each part of the script does:
  1)	$LocalTempDir: Specifies the local temporary directory, typically "C:\Users<Username>\AppData\Local\Temp".
  2)	$ChromeInstaller: Defines the name of the Chrome installer.
  3)	(new-object System.Net.WebClient).DownloadFile: Downloads the Chrome installer from the specified URL and saves it to the local temporary directory.
  4)	& "$LocalTempDir\$ChromeInstaller" /silent /install: Executes the downloaded installer with the "/silent /install" command-line arguments to perform a silent installation of       Google Chrome.
  5)	$Process2Monitor: Specifies the process name to monitor during the installation, which is "ChromeInstaller" in this case.
  6)	The script enters a loop that checks for the presence of the monitored process (ChromeInstaller) using Get-Process. If the process is found, it prints a message indicating         that it is still running and sleeps for 2 seconds. This loop continues until the process is no longer found, signifying that the installation is complete.
  7)	After the installation is complete and the installer process is no longer running, the script removes the installer file from the local temporary directory using Remove-Item.

This script provides a way to automate the silent installation of Google Chrome and monitor the installation process in PowerShell. Please ensure that the URL for the Chrome installer is up-to-date, as Chrome versions and download URLs may change over time
