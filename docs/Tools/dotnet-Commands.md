---
title: die NuGet-Befehle DotNet | Microsoft Docs
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 12/08/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
description: "Eine kurze Referenz für NuGet-bezogenen Befehlen, die über die Befehlszeilenschnittstelle Dotnet."
keywords: "Dotnet NuGet-Befehle, Dotnet Pack, Dotnet-Wiederherstellung, Dotnet Nuget \"lokal\", Dotnet NuGet-Push, Dotnet NuGet-löschen"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: d06e4590ab87b68e7846a13b2eba0f59eb9529d6
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="dotnet-commands"></a><span data-ttu-id="5a2b0-104">ein DotNet-Befehle</span><span class="sxs-lookup"><span data-stu-id="5a2b0-104">dotNet commands</span></span>

<span data-ttu-id="5a2b0-105">DotNet-Befehlszeilen-Schnittstelle, die unter Windows, Mac OS X und Linux ausgeführt wird, bietet eine Reihe von wesentlichen nuget.exe-Befehlen wie nachstehend aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-105">The DotNet command-line interface, which runs on Windows, Mac OS X, and Linux, provides a number of essential nuget.exe commands as listed below.</span></span> <span data-ttu-id="5a2b0-106">Wobei Dotnet die gewünschten Befehle bereitstellt, ist es nicht notwendig, nuget.exe herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-106">Where dotnet provides the desired commands, it's not necessary to download nuget.exe.</span></span>

- <span data-ttu-id="5a2b0-107">[**Dotnet Pack**](/dotnet/core/tools/dotnet-pack?tabs=netcore2x): Packs den Code in ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-107">[**dotnet pack**](/dotnet/core/tools/dotnet-pack?tabs=netcore2x): Packs the code into a NuGet package.</span></span> <span data-ttu-id="5a2b0-108">Ab NuGet 4.0, führt dies denselben Code wie `nuget pack`.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-108">As of NuGet 4.0, this runs the same code as `nuget pack`.</span></span>
- <span data-ttu-id="5a2b0-109">[**Dotnet Wiederherstellung**](/dotnet/core/tools/dotnet-restore?tabs=netcore2x): stellt die Abhängigkeiten und Tools eines Projekts wieder her.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-109">[**dotnet restore**](/dotnet/core/tools/dotnet-restore?tabs=netcore2x): Restores the dependencies and tools of a project.</span></span> <span data-ttu-id="5a2b0-110">Ab NuGet 4.0, führt dies denselben Code wie `nuget restore`.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-110">As of NuGet 4.0, this runs the same code as `nuget restore`.</span></span>
- <span data-ttu-id="5a2b0-111">[**Dotnet Nuget "lokal"**](/dotnet/core/tools/dotnet-nuget-locals): Löscht ab oder listet lokalen NuGet-Ressourcen wie z. B. http-Anforderung Cache, temporären Cache oder computerweite globalen Pakete (Ordner).</span><span class="sxs-lookup"><span data-stu-id="5a2b0-111">[**dotnet nuget locals**](/dotnet/core/tools/dotnet-nuget-locals): Clears or lists local NuGet resources such as http the -request cache, temporary cache, or machine-wide global packages folder.</span></span>
- <span data-ttu-id="5a2b0-112">[**Dotnet Nuget Push**](/dotnet/core/tools/dotnet-nuget-push): Es wird ein Paket an einem Server und veröffentlicht ihn, gilt für nuget.org, Visual Studio Team Services oder von Drittanbieter-NuGet-Servern.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-112">[**dotnet nuget push**](/dotnet/core/tools/dotnet-nuget-push): Pushes a package to a server and publishes it, applicable to nuget.org, Visual Studio Team Services, or any third-party NuGet servers.</span></span>
- <span data-ttu-id="5a2b0-113">[**Löschen von Dotnet Nuget**](/dotnet/core/tools/dotnet-nuget-delete): Löscht oder unlists ein Paket von einem Server, auf nuget.org, Visual Studio Team Services oder von Drittanbieter-NuGet-Servern anwendbar.</span><span class="sxs-lookup"><span data-stu-id="5a2b0-113">[**dotnet nuget delete**](/dotnet/core/tools/dotnet-nuget-delete): Deletes or unlists a package from a  server, applicable to nuget.org, Visual Studio Team Services, or any third-party NuGet servers.</span></span>