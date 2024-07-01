# Win10-3.5Netframework-offline-installer
Offline install of .NET Framework 3.5 in Windows 10 using DISM

Over thousands of pages over the internet I did find this easy way and it worked perfectly

https://winaero.com/offline-install-of-net-framework-3-5-in-windows-10-using-dism/

Batch file look like this

	@echo off
	Title .NET Framework 3.5 Offline Installer
	for %%I in (D E F G H I J K L M N O P Q R S T U V W X Y Z) do if exist "%%I:\\sources\install.wim" set setupdrv=%%I
	if defined setupdrv (
	echo Found drive %setupdrv%
	echo Installing .NET Framework 3.5...
	Dism /online /enable-feature /featurename:NetFX3 /All /Source:%setupdrv%:\sources\sxs /LimitAccess
	echo.
	echo .NET Framework 3.5 should be installed
	echo.
	) else (
	echo No installation media found!
	echo Insert DVD or USB flash drive and run this file once again. 
	echo.
	)
	pause

Glade to share it with you
