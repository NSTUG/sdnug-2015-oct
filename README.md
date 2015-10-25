# Sacramento .Net User Group
Windows 10 IOT on a Raspberry PI serving a MVC6 application.

#### Basic Commands:

Install Chocolatey and NodeJs

	@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
	choco install nodejs.install -y
	 
Install vNext Execution Environment

	@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&{$Branch='dev';$wc=New-Object System.Net.WebClient;$wc.Proxy=[System.Net.WebRequest]::DefaultWebProxy;$wc.Proxy.Credentials=[System.Net.CredentialCache]::DefaultNetworkCredentials;Invoke-Expression ($wc.DownloadString('https://raw.githubusercontent.com/aspnet/Home/dev/dnvminstall.ps1'))}"

Install Required Packages

	npm install -g yo bower grunt-cli gulp generator-aspnet
	dnvm update-self
	dnvm install latest -r coreclr -arch ARM -u
	dnvm install latest -r coreclr -arch x86 -u
	dnvm install latest -r coreclr -arch x64 -u
	dnvm install latest -r clr -arch x86 -u
	dnvm install latest -r clr -arch x64 -u

Install VS Code as Editor

	choco install visualstudiocode
	
Run Basic Website Scaffolding

	yo -v 
		Choose Asp Generator
		Choose Basic Web Application
	cd "WebApplicationBasic"
	dnu restore
	dnu build
	dnx web 