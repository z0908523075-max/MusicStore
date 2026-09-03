MusicStore (ASP.NET Core 範例應用程式)
============================================

AppVeyor: [![AppVeyor](https://ci.appveyor.com/api/projects/status/ja8a7j6jscj7k3xa/branch/dev?svg=true)](https://ci.appveyor.com/project/aspnetci/MusicStore/branch/dev)

Travis:   [![Travis](https://travis-ci.org/aspnet/MusicStore.svg?branch=dev)](https://travis-ci.org/aspnet/MusicStore)

此專案是 ASP.NET Core 的一部分。您可以在 [Home](https://github.com/aspnet/home) 存放庫中找到 ASP.NET Core 的範例、文件和入門說明。

## 執行應用程式：
* 如果您有 Visual Studio 2017
	1. 在 Visual Studio 2017 中開啟 `MusicStore.sln`，並在 `IIS Express` 上執行各個應用程式。

* 如果您沒有 Visual Studio 2017
	1. 開啟命令提示字元並執行 `cd \src\MusicStore\`。
	2. 執行 `dotnet restore`。

**注意：** 應用程式和測試需要本機安裝 Visual Studio 2017 LocalDB 才能執行。
**注意：** 由於 Mac 上通常無法使用 SQL Server，因此會使用 `InMemoryStore` 來執行應用程式。所以您所做的變更將不會保留。

## 在 Docker Windows 容器上執行

 * [安裝 Docker for Windows](https://docs.docker.com/docker-for-windows/) 或 [設定 Docker Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/containers_welcome)
 * `docker-compose -f .\docker-compose.windows.yml build`
 * `docker-compose -f .\docker-compose.windows.yml up`
 * 在 Windows VM IP 或（如果容器在本機執行）容器 IP 上存取 MusicStore：`docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" musicstore_web_1`

## NTLM 驗證
更多資訊請參閱 [src/MusicStore/StartupNtlmAuthentication.cs](src/MusicStore/StartupNtlmAuthentication.cs)。

## OpenIdConnect 驗證
更多資訊請參閱 [src/MusicStore/StartupOpenIdConnect.cs](src/MusicStore/StartupOpenIdConnect.cs)。
