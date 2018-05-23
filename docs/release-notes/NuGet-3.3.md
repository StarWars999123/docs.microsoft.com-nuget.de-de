---
title: 3.3 NuGet-Versionshinweise
description: Versionshinweise für NuGet 3.3 einschließlich bekannte Probleme, Fehlerbehebungen, Funktionen und Archivierung von dcrs Design.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 11/11/2016
ms.topic: conceptual
ms.openlocfilehash: adf193437de237ed32da481e627552a8dba6f656
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="nuget-33-release-notes"></a><span data-ttu-id="fe9b7-103">3.3 NuGet-Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="fe9b7-103">NuGet 3.3 Release Notes</span></span>

<span data-ttu-id="fe9b7-104">[Anmerkungen zur Version des NuGet-3.2.1](../release-notes/nuget-3.2.1.md) | [NuGet 3.4-RC-Versionsanmerkungen](../release-notes/nuget-3.4-RC.md)</span><span class="sxs-lookup"><span data-stu-id="fe9b7-104">[NuGet 3.2.1 Release Notes](../release-notes/nuget-3.2.1.md) | [NuGet 3.4-RC Release Notes](../release-notes/nuget-3.4-RC.md)</span></span>

<span data-ttu-id="fe9b7-105">NuGet-3.3 wurde am 30. November 2015 mit einer erheblichen Anzahl von benutzerschnittstellenupdates und Befehlszeilen-Funktionen sowie eine Auflistung von nützlich Korrekturen für den NuGet-Clients freigegeben.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-105">NuGet 3.3 was released November 30, 2015 with a significant number of user interface updates and command-line features as well as a collection of useful fixes to the NuGet clients.</span></span>

## <a name="new-features"></a><span data-ttu-id="fe9b7-106">Neue Funktionen</span><span class="sxs-lookup"><span data-stu-id="fe9b7-106">New Features</span></span>

* <span data-ttu-id="fe9b7-107">Anmeldeinformationsanbieter wurden eingeführt, die NuGet-Befehlszeilen-Clients in der Lage, um die nahtlose Zusammenarbeit mit einem authentifizierten Feed sein können.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-107">Credential Providers have been introduced that allow NuGet command-line clients to be able to work seamlessly with an authenticated feed.</span></span> <span data-ttu-id="fe9b7-108">[Anweisungen zum Installieren der Visual Studio Team Services-Anmeldeinformationen Anbieter ](../api/nuget-exe-credential-providers.md) und konfigurieren Sie die NuGet Clients zur Verwendung finden Sie auf der NuGet Docs.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-108">[Instructions on how to install the Visual Studio Team Services credential provider ](../api/nuget-exe-credential-providers.md) and configure the NuGet clients to use it are available on NuGet Docs.</span></span>

## <a name="new-user-interface-features"></a><span data-ttu-id="fe9b7-109">Neue Features der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="fe9b7-109">New User Interface Features</span></span>

* <span data-ttu-id="fe9b7-110">Registerkarten für separate durchsuchen, installiert und Updates verfügbar</span><span class="sxs-lookup"><span data-stu-id="fe9b7-110">Separate Browse, Installed, and Updates Available tabs</span></span>
* <span data-ttu-id="fe9b7-111">Verfügbare Badge, der angibt, der Anzahl der Pakete mit verfügbaren Updates aktualisiert</span><span class="sxs-lookup"><span data-stu-id="fe9b7-111">Updates Available badge indicating the number of packages with available updates</span></span>
* <span data-ttu-id="fe9b7-112">Paket Signale in der Liste der Pakete an, wenn das Paket installiert ist, oder ein Update verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="fe9b7-112">Package badges in the package list to indicate if the package is installed or has an update available</span></span>
* <span data-ttu-id="fe9b7-113">Herunterladen Sie Anzahl und der Autor hinzugefügt wird, um die Liste der Pakete</span><span class="sxs-lookup"><span data-stu-id="fe9b7-113">Download count and author added to the package list</span></span>
* <span data-ttu-id="fe9b7-114">Höchste verfügbare Versionsnummer und der derzeit installierten Version Zahl auf die Paketliste</span><span class="sxs-lookup"><span data-stu-id="fe9b7-114">Highest available version number and currently installed version number on the package list</span></span>
* <span data-ttu-id="fe9b7-115">Aktionsschaltflächen schnelle Installation zu aktualisieren und Deinstallieren von aus der Liste der Pakete</span><span class="sxs-lookup"><span data-stu-id="fe9b7-115">Action buttons to allow quick install, update, and uninstall from the package list</span></span>
* <span data-ttu-id="fe9b7-116">Klarer Aktionsschaltflächen im Paket-Detail-Bereich</span><span class="sxs-lookup"><span data-stu-id="fe9b7-116">Clearer action buttons on the package detail panel</span></span>
* <span data-ttu-id="fe9b7-117">Paket Aktualisierungsdatum im Paket-Detail-Bereich</span><span class="sxs-lookup"><span data-stu-id="fe9b7-117">Package update date on the package detail panel</span></span>
* <span data-ttu-id="fe9b7-118">Konsolidieren Sie Bereich im Projektmappen-Ansicht</span><span class="sxs-lookup"><span data-stu-id="fe9b7-118">Consolidate panel in Solution view</span></span>
* <span data-ttu-id="fe9b7-119">Sortierbares Raster von Projekten und installierten Versionsnummern für die Lösung-Sicht</span><span class="sxs-lookup"><span data-stu-id="fe9b7-119">Sortable grid of projects and installed version numbers on the solution view</span></span>

## <a name="new-command-line-features"></a><span data-ttu-id="fe9b7-120">Neue Befehlszeilen-Funktionen</span><span class="sxs-lookup"><span data-stu-id="fe9b7-120">New Command-line Features</span></span>

<span data-ttu-id="fe9b7-121">In dieser Version eingeführten wir die `add` und `init` Befehle aus, um die Ordner-basierte Repositorys zu initialisieren, wie beschrieben in der [nuget.exe Verweis](../tools/nuget-exe-cli-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b7-121">In this version we introduced the `add` and `init` commands to initialize folder-based repositories as described in the [nuget.exe reference](../tools/nuget-exe-cli-reference.md).</span></span> <span data-ttu-id="fe9b7-122">Repositorys, die erstellt und verwaltet, die mit diesem Ordner-Struktur wird [bieten Sie beachtliche Leistungsvorteile](http://blog.nuget.org/20150922/Accelerate-Package-Source.html) wie beschrieben in unserem Blog.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-122">Repositories that are constructed and maintained with this folder structure will [deliver significant performance benefits](http://blog.nuget.org/20150922/Accelerate-Package-Source.html) as outlined on our blog.</span></span>

## <a name="contentfiles"></a><span data-ttu-id="fe9b7-123">ContentFiles</span><span class="sxs-lookup"><span data-stu-id="fe9b7-123">ContentFiles</span></span>

<span data-ttu-id="fe9b7-124">Inhalt wird jetzt unterstützt `project.json` verwaltete Projekte über die neue `contentFiles` Ordner und `.nuspec` `contentFiles` Element Notation.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-124">Content is now supported in `project.json` managed projects through the new `contentFiles` folder and `.nuspec` `contentFiles` element notation.</span></span>  <span data-ttu-id="fe9b7-125">Dieser Inhalt kann direkt vom Paketersteller für Interaktionen mit Projektsystemen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-125">This content can be more directly specified by the package author for interactions with project systems.</span></span>  <span data-ttu-id="fe9b7-126">Weitere Informationen zum Konfigurieren der Inhaltsdateien in einem `.nuspec` Dokument befindet sich der [.nuspec Verweis](../reference/nuspec.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b7-126">More information about how to configure contentFiles in a `.nuspec` document can be found in the [.nuspec Reference](../reference/nuspec.md).</span></span>

## <a name="nuget-locals-cache-management"></a><span data-ttu-id="fe9b7-127">NuGet "lokal" Cache-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="fe9b7-127">NuGet Locals Cache Management</span></span>

<span data-ttu-id="fe9b7-128">Die NuGet-Befehlszeile wurde aktualisiert, um Informationen zum Verwalten des lokalen Caches auf einer Arbeitsstation enthalten.</span><span class="sxs-lookup"><span data-stu-id="fe9b7-128">The NuGet command-line has been updated to include information about how to manage the local caches on a workstation.</span></span>  <span data-ttu-id="fe9b7-129">Weitere Informationen zum Befehl "lokal" steht in der [NuGet-Befehlszeilenreferenz](../tools/cli-ref-locals.md).</span><span class="sxs-lookup"><span data-stu-id="fe9b7-129">More information about the locals command is available in the [NuGet command-line reference](../tools/cli-ref-locals.md).</span></span>

## <a name="fixed-issues"></a><span data-ttu-id="fe9b7-130">Behobene Probleme</span><span class="sxs-lookup"><span data-stu-id="fe9b7-130">Fixed Issues</span></span>

<span data-ttu-id="fe9b7-131">**Relevante Probleme**</span><span class="sxs-lookup"><span data-stu-id="fe9b7-131">**Notable Issues**</span></span>

* <span data-ttu-id="fe9b7-132">NuGet-Befehlszeilen wiederhergestellten-Unterstützung für die Wiederherstellung-Paketen mit einer Projektmappendatei auf Mono - [1543](https://github.com/NuGet/Home/issues/1543)</span><span class="sxs-lookup"><span data-stu-id="fe9b7-132">NuGet command-line restored support for restoring packages with a solution file on Mono - [1543](https://github.com/NuGet/Home/issues/1543)</span></span>

<span data-ttu-id="fe9b7-133">Die vollständige Liste der in der 3.3-Version behobene Probleme finden Sie auf GitHub unter der [3.3 Meilenstein](https://github.com/NuGet/Home/issues?q=is%3Aissue+milestone%3A3.3.0+is%3Aclosed).</span><span class="sxs-lookup"><span data-stu-id="fe9b7-133">The complete list of issues that were addressed in the 3.3 release can be found on GitHub under the [3.3 milestone](https://github.com/NuGet/Home/issues?q=is%3Aissue+milestone%3A3.3.0+is%3Aclosed).</span></span>

<span data-ttu-id="fe9b7-134">Die Liste der in der Befehlszeile 3.3-Version behobene Probleme werden aufgezeichnet, der [3.3 Befehlszeilen Meilenstein](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A3.3.0-commandline).</span><span class="sxs-lookup"><span data-stu-id="fe9b7-134">The list of issues fixed in the 3.3 command-line release are recorded in the [3.3 Command-Line milestone](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A3.3.0-commandline).</span></span>

## <a name="known-issues"></a><span data-ttu-id="fe9b7-135">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="fe9b7-135">Known Issues</span></span>

<span data-ttu-id="fe9b7-136">Wir weiterhin Probleme auf unserer GitHub-Problemliste zu verfolgen, die sich am befinden: [http://github.com/nuget/home/issues](http://github.com/nuget/home/issues)</span><span class="sxs-lookup"><span data-stu-id="fe9b7-136">We continue to track issues on our GitHub issues list which can be found at: [http://github.com/nuget/home/issues](http://github.com/nuget/home/issues)</span></span>