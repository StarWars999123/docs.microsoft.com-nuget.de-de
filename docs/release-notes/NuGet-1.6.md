---
title: 1.6 NuGet-Versionshinweise
description: Versionshinweise für NuGet 1.6 einschließlich bekannte Probleme, Fehlerbehebungen, Funktionen und Archivierung von dcrs Design.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 11/11/2016
ms.topic: conceptual
ms.openlocfilehash: 0345e180893a56302385d27792c4e15ba5d96989
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
 # <a name="nuget-16-release-notes"></a><span data-ttu-id="121b9-103">1.6 NuGet-Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="121b9-103">NuGet 1.6 Release Notes</span></span>

<span data-ttu-id="121b9-104">[Anmerkungen zur Version des NuGet-1.5](../release-notes/nuget-1.5.md) | [NuGet 1.7-Versionshinweise](../release-notes/nuget-1.7.md)</span><span class="sxs-lookup"><span data-stu-id="121b9-104">[NuGet 1.5 Release Notes](../release-notes/nuget-1.5.md) | [NuGet 1.7 Release Notes](../release-notes/nuget-1.7.md)</span></span>

<span data-ttu-id="121b9-105">NuGet-1.6 wurde 13 Dezember 2011 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="121b9-105">NuGet 1.6 was released on December 13, 2011.</span></span>

## <a name="known-installation-issue"></a><span data-ttu-id="121b9-106">Bekannte Problem</span><span class="sxs-lookup"><span data-stu-id="121b9-106">Known Installation Issue</span></span>
<span data-ttu-id="121b9-107">Wenn Sie Visual Studio 2010 SP1 ausführen, kann ein Installationsfehler auftreten beim Upgrade von NuGet ausführen, wenn Sie eine ältere Version installiert haben.</span><span class="sxs-lookup"><span data-stu-id="121b9-107">If you are running VS 2010 SP1, you might run into an installation error when attempting to upgrade NuGet if you have an older version installed.</span></span>

<span data-ttu-id="121b9-108">Die problemumgehung besteht darin, einfach NuGet deinstallieren und installieren Sie es aus dem Katalog der VS-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="121b9-108">The workaround is to simply uninstall NuGet and then install it from the VS Extension Gallery.</span></span>  <span data-ttu-id="121b9-109">Weitere Informationen finden Sie unter [http://support.microsoft.com/kb/2581019](http://support.microsoft.com/kb/2581019).</span><span class="sxs-lookup"><span data-stu-id="121b9-109">See [http://support.microsoft.com/kb/2581019](http://support.microsoft.com/kb/2581019) for more information.</span></span>

<span data-ttu-id="121b9-110">Hinweis: Wenn Visual Studio lässt Sie beim Deinstallieren der Erweiterung (die Schaltfläche "Deinstallieren" deaktiviert ist), müssen Sie wahrscheinlich zum Neustart von Visual Studio, die mit "Als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="121b9-110">Note: If Visual Studio won't allow you to uninstall the extension (the Uninstall button is disabled), then you likely need to restart Visual Studio using "Run as Administrator."</span></span>

## <a name="features"></a><span data-ttu-id="121b9-111">Features</span><span class="sxs-lookup"><span data-stu-id="121b9-111">Features</span></span>

### <a name="support-for-semantic-versioning-and-prerelease-packages"></a><span data-ttu-id="121b9-112">Unterstützung für semantische Versionsverwaltung und Vorabversionen von Paketen</span><span class="sxs-lookup"><span data-stu-id="121b9-112">Support for Semantic Versioning and Prerelease Packages</span></span>
<span data-ttu-id="121b9-113">NuGet-1.6 wird Unterstützung für semantische Versionsverwaltung (SemVer) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="121b9-113">NuGet 1.6 introduces support for Semantic Versioning (SemVer).</span></span> <span data-ttu-id="121b9-114">Weitere Informationen dazu, wie sie SemVer verwendet, finden Sie unter der [Versionsverwaltung Dokumentation](../create-packages/prerelease-packages.md).</span><span class="sxs-lookup"><span data-stu-id="121b9-114">For more details on how it uses SemVer, read the [Versioning documentation](../create-packages/prerelease-packages.md).</span></span>

### <a name="using-nuget-without-checking-in-packages-package-restore"></a><span data-ttu-id="121b9-115">Mithilfe von NuGet ohne Überprüfung der In Paketen (Paketwiederherstellung)</span><span class="sxs-lookup"><span data-stu-id="121b9-115">Using NuGet Without Checking In Packages (Package Restore)</span></span>
<span data-ttu-id="121b9-116">NuGet-1.6 hat jetzt erstklassige Unterstützung für den Workflow, in welche, den, den NuGet Pakete werden nicht zur quellcodeverwaltung hinzugefügt, stattdessen werden jedoch wiederhergestellt zur Buildzeit sofern noch nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="121b9-116">NuGet 1.6 now has first class support for the workflow in which NuGet packages are not added to source control, but instead are restored at build time if missing.</span></span> <span data-ttu-id="121b9-117">Weitere Informationen finden Sie unter der [NuGet verwenden, ohne dass Pakete, Datenquellen-Steuerelements](../consume-packages/packages-and-source-control.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="121b9-117">For more details, read the [Using NuGet without committing packages to source control](../consume-packages/packages-and-source-control.md) topic.</span></span>

### <a name="item-templates-that-install-nuget-packages"></a><span data-ttu-id="121b9-118">Elementvorlagen, die NuGet-Pakete installieren</span><span class="sxs-lookup"><span data-stu-id="121b9-118">Item Templates That Install NuGet Packages</span></span>
<span data-ttu-id="121b9-119">Erstellen auf der Arbeit vorinstallierte NuGet-Paket zu Visual Studio-Projektvorlagen unterstützen, fügt 1.6 NuGet-Unterstützung für Visual Studio-Elementvorlagen.</span><span class="sxs-lookup"><span data-stu-id="121b9-119">Building on the work to support preinstalled NuGet package to Visual Studio project templates, NuGet 1.6 also adds support for Visual Studio item templates.</span></span> <span data-ttu-id="121b9-120">Elementvorlagen können NuGet-Pakete zugeordnet, die installiert werden, wenn die Vorlage in aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="121b9-120">Item templates can have associated NuGet packages that are installed when the template in invoked.</span></span>

<span data-ttu-id="121b9-121">Details dazu, wie ein Projektelement/Vorlage zum Installieren von NuGet-Pakete zu ändern, finden Sie unter der [Pakete in Visual Studio-Vorlagen](../visual-studio-extensibility/visual-studio-templates.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="121b9-121">For more details on how to change a project/item template to install NuGet packages, read the [Packages in Visual Studio Templates](../visual-studio-extensibility/visual-studio-templates.md) topic.</span></span>

### <a name="support-for-disabling-package-sources"></a><span data-ttu-id="121b9-122">Unterstützung für Paketquellen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="121b9-122">Support for disabling package sources</span></span>
<span data-ttu-id="121b9-123">Wenn mehrere Paketquellen konfiguriert sind, sieht NuGet während der Installation eines Paketes und seiner Abhängigkeiten in jeder Kategorie für Pakete.</span><span class="sxs-lookup"><span data-stu-id="121b9-123">When multiple package sources are configured, NuGet will look in each one for packages during installation of a package and its dependencies.</span></span> <span data-ttu-id="121b9-124">Eine Paketquelle, die für Sie aus irgendeinem Grund eine schwerwiegende Beschädigung NuGet verlangsamt kann nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="121b9-124">A package source that is down for some reason can severely slow down NuGet.</span></span>

<span data-ttu-id="121b9-125">Vor dem NuGet-1.6 könnten Sie die Paketquelle entfernen, müssen dann aber zu merken, wieder die Details für, wenn Sie ihn hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="121b9-125">Prior to NuGet 1.6, you could remove the package source, but then you have to remember the details for when you want to add it back in.</span></span>

<span data-ttu-id="121b9-126">NuGet-1.6 ermöglicht eine Paketquelle zum deaktivieren, halten Sie es aber deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="121b9-126">NuGet 1.6 allows unchecking a package source to disable it, but keep it around.</span></span>

![Deaktivieren ein Paket](./media/package-source-with-disabled-source.png)

## <a name="bug-fixes"></a><span data-ttu-id="121b9-128">Fehlerkorrekturen</span><span class="sxs-lookup"><span data-stu-id="121b9-128">Bug Fixes</span></span>
<span data-ttu-id="121b9-129">NuGet-1.6 mussten insgesamt 106 Arbeitsaufgaben behoben.</span><span class="sxs-lookup"><span data-stu-id="121b9-129">NuGet 1.6 had a total of 106 work items fixed.</span></span> <span data-ttu-id="121b9-130">95 dieser wurden als Fehler eingestuft, und 10 dieser Waren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="121b9-130">95 of those were classified as bugs and 10 of those were features.</span></span>

<span data-ttu-id="121b9-131">Eine vollständige Liste der Arbeit Elemente in behoben NuGet 1.6, bitte Ansicht der [NuGet Issue Tracker für diese Version](http://nuget.codeplex.com/workitem/list/advanced?keyword=&status=Closed&type=All&priority=All&release=NuGet%201.6&assignedTo=All&component=All&sortField=Votes&sortDirection=Descending&page=0).</span><span class="sxs-lookup"><span data-stu-id="121b9-131">For a full list of work items fixed in NuGet 1.6, please view the [NuGet Issue Tracker for this release](http://nuget.codeplex.com/workitem/list/advanced?keyword=&status=Closed&type=All&priority=All&release=NuGet%201.6&assignedTo=All&component=All&sortField=Votes&sortDirection=Descending&page=0).</span></span>