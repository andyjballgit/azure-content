<properties
   pageTitle="Update your Service Fabric development environment | Microsoft Azure"
   description="Update your Service Fabric development environment to use the latest runtime, SDK, and tools."
   services="service-fabric"
   documentationCenter=".net"
   authors="seanmck"
   manager="timlt"
   editor=""/>

<tags
   ms.service="service-fabric"
   ms.devlang="dotNet"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="10/30/2015"
   ms.author="seanmck"/>

# Update your Service Fabric development environment

 Azure Service Fabric periodically provides new releases of the runtime, SDK, and tools for use in local development. By keeping your local development environment updated with these releases, you can make sure that you always have access to the latest features, bug fixes, and performance improvements when you are building and testing your applications locally.

## Clean up your local cluster

 Service Fabric does not currently support upgrading the Service Fabric runtime while a local cluster is running. In order to ensure a clean upgrade, it is important that you clean up your local cluster first.

 > [AZURE.NOTE] Cleaning your local cluster will remove all deployed applications and their data.

 You can clean your local cluster as follows:


 1. Close all PowerShell windows and open a new one as an administrator.

 2. Navigate to the cluster setup directory by using `cd "$env:ProgramW6432\Microsoft SDKs\Service Fabric\ClusterSetup"`.

 3. Run `.\CleanCluster.ps1`.


## Update the runtime, SDK, and tools

 Once you have successfully cleaned up your existing cluster, you can proceed with the upgrade as follows:


 1. Start the Web Platform Installer to [update to the new release][1].

 2. Upon completion, open a new PowerShell window as an administrator and navigate to the cluster setup directory by using `cd "$ENV:ProgramFiles\Microsoft SDKs\ServiceFabric\ClusterSetup"`.

 3. Run `.\DevClusterSetup.ps1` to set up your local cluster.

That's it! You can now start Visual Studio and continue building Service Fabric applications.

>[AZURE.NOTE] The default project structure has changed in this release. You should be able to open and run existing projects in Visual Studio. However, if you encounter any issues with building, deploying, or debugging your applications, consider creating a new project and migrating your code over to it.

 [1]:  http://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric "WebPI link"
