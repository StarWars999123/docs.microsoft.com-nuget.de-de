---
title: Anmerkungen dieser Version von NuGet 3.0 RC
description: Versionshinweise für NuGet 3.0 RC einschließlich bekannte Probleme, Fehlerbehebungen, Funktionen und Archivierung von dcrs Design.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 11/11/2016
ms.topic: conceptual
ms.openlocfilehash: 28ac49d9e9071d16d20b24808abb0acaab214ffd
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="nuget-30-rc-release-notes"></a><span data-ttu-id="c58c0-103">Anmerkungen dieser Version von NuGet 3.0 RC</span><span class="sxs-lookup"><span data-stu-id="c58c0-103">NuGet 3.0 RC Release Notes</span></span>

<span data-ttu-id="c58c0-104">[Anmerkungen zur Version von NuGet 3.0 Beta](../release-notes/nuget-3.0-beta.md) | [NuGet 3.0 RC2-Anmerkungen zu dieser Version](../release-notes/nuget-3.0-RC2.md)</span><span class="sxs-lookup"><span data-stu-id="c58c0-104">[NuGet 3.0 Beta Release Notes](../release-notes/nuget-3.0-beta.md) | [NuGet 3.0 RC2 Release Notes](../release-notes/nuget-3.0-RC2.md)</span></span>

<span data-ttu-id="c58c0-105">NuGet 3.0 RC wurde mit der Version von Visual Studio 2015 RC am 29. April 2015 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c58c0-105">NuGet 3.0 RC was released on April 29, 2015 with the Visual Studio 2015 RC release.</span></span> <span data-ttu-id="c58c0-106">Diese Version enthält eine Reihe von wichtiger Programmfehlerbehebungen, leistungsverbesserungen und Upgrades zur Unterstützung der neuen Frameworks.</span><span class="sxs-lookup"><span data-stu-id="c58c0-106">This release has a number of important bug fixes, performance improvements and updates to support the new frameworks.</span></span>  <span data-ttu-id="c58c0-107">Es ist nur für Visual Studio 2015 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c58c0-107">It is only available for Visual Studio 2015.</span></span>

### <a name="continued-focus-on-performance"></a><span data-ttu-id="c58c0-108">Kontinuierliche den Fokus auf die Leistung</span><span class="sxs-lookup"><span data-stu-id="c58c0-108">Continued Focus on Performance</span></span>

<span data-ttu-id="c58c0-109">Stabilität und Leistung von NuGet-Abfragen weiterhin ein im laufenden Systembetrieb Thema sein, dem wir auf konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="c58c0-109">Stability and performance of NuGet queries continue to be a hot topic that we are focusing on.</span></span>  <span data-ttu-id="c58c0-110">Mit dieser Version sollte gestartet werden, sehr schnelle Suchvorgänge in der Website und NuGet UI finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c58c0-110">With this release, you should start to see very quick search operations in the NuGet UI and website.</span></span>  <span data-ttu-id="c58c0-111">Es wird überwacht, den Dienst und wie Sie den Dienst verwenden, sodass wir fortfahren können, um diese Vorgänge zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="c58c0-111">We're monitoring the service and how you use the service so that we can continue to tune these operations.</span></span>

## <a name="significant-issues-resolved"></a><span data-ttu-id="c58c0-112">Erhebliche Probleme gelöst wurden</span><span class="sxs-lookup"><span data-stu-id="c58c0-112">Significant Issues Resolved</span></span>

<span data-ttu-id="c58c0-113">Um die NuGet-Clients zu stabilisieren aufgelöst wir viele Probleme, die als Teil dieser Version.</span><span class="sxs-lookup"><span data-stu-id="c58c0-113">In order to stabilize the NuGet clients, we resolved many issues as part of this release.</span></span>  <span data-ttu-id="c58c0-114">Hier wird nur eine kurze Liste der einiger wichtiger Probleme behoben:</span><span class="sxs-lookup"><span data-stu-id="c58c0-114">Here is just a brief list of some of the more important issues resolved:</span></span>

* <span data-ttu-id="c58c0-115">Als Teil der Umbenennung von K-Framework für ASP.NET 5, frameworkMoniker zur Behandlung von Dnx und Dnxcore aktualisiert wurden [Link](https://github.com/NuGet/Home/issues/215)</span><span class="sxs-lookup"><span data-stu-id="c58c0-115">As part of the rename of the K framework for ASP.NET 5, framework monikers have been updated to handle dnx and dnxcore [link](https://github.com/NuGet/Home/issues/215)</span></span>
* <span data-ttu-id="c58c0-116">Hilfe-Dokumentation über Links in der Visual Studio-Benutzeroberfläche hinzugefügt [Link](https://github.com/NuGet/Home/issues/232)</span><span class="sxs-lookup"><span data-stu-id="c58c0-116">Added help documentation from links in the Visual Studio UI [link](https://github.com/NuGet/Home/issues/232)</span></span>
* <span data-ttu-id="c58c0-117">Eine bessere Behandlung von komplexen Verweise in `.nuspec` mit durch Trennzeichen getrennte Framework verweisen [Link](https://github.com/NuGet/Home/issues/276)</span><span class="sxs-lookup"><span data-stu-id="c58c0-117">Better handling of complex references in `.nuspec` with comma-delimited framework references [link](https://github.com/NuGet/Home/issues/276)</span></span>
* <span data-ttu-id="c58c0-118">Unterstützung für Japanisch Kulturen festen [Link](https://github.com/NuGet/Home/issues/253)</span><span class="sxs-lookup"><span data-stu-id="c58c0-118">Fixed support for Japanese cultures [link](https://github.com/NuGet/Home/issues/253)</span></span>
* <span data-ttu-id="c58c0-119">Aktualisierte Client neue v3-Endpunkte verwenden, die ASP.NET 5-Projekte ermöglichen es [Link](https://github.com/NuGet/Home/issues/219)</span><span class="sxs-lookup"><span data-stu-id="c58c0-119">Updated client to allow ASP.NET 5 projects to use new v3 endpoints [link](https://github.com/NuGet/Home/issues/219)</span></span>
* <span data-ttu-id="c58c0-120">Aktualisierte besser Handle Pakete (Ordner) mit der quellcodeverwaltung [Link](https://github.com/NuGet/Home/issues/56)</span><span class="sxs-lookup"><span data-stu-id="c58c0-120">Updated to better handle packages folder with source control [link](https://github.com/NuGet/Home/issues/56)</span></span>
* <span data-ttu-id="c58c0-121">Unterstützung für Satelliten-Paketen behoben [Link](https://github.com/NuGet/Home/issues/17)</span><span class="sxs-lookup"><span data-stu-id="c58c0-121">Fixed support for satellite packages [link](https://github.com/NuGet/Home/issues/17)</span></span>
* <span data-ttu-id="c58c0-122">Unterstützung für frameworkspezifische Inhaltsdateien korrigiert [Link](https://github.com/NuGet/Home/issues/18)</span><span class="sxs-lookup"><span data-stu-id="c58c0-122">Corrected support for framework-specific content files [link](https://github.com/NuGet/Home/issues/18)</span></span>

## <a name="github-presence-overhaul"></a><span data-ttu-id="c58c0-123">GitHub Vorhandensein Überarbeitung</span><span class="sxs-lookup"><span data-stu-id="c58c0-123">GitHub presence overhaul</span></span>

<span data-ttu-id="c58c0-124">Wir haben einige Änderungen vorgenommen unsere [source in GitHub-Repositorys](http://github.com/nuget/home).</span><span class="sxs-lookup"><span data-stu-id="c58c0-124">We've made some changes to our [source code repositories on GitHub](http://github.com/nuget/home).</span></span>  <span data-ttu-id="c58c0-125">Haben Probleme mit der Visual Studio NuGet-Clients, die Powershell-Befehle oder der Befehlszeile ausführbare Sie können diese Probleme melden und überwachen ihren Fortschritt auf unserer [Home GitHub-Repository Problemliste](http://github.com/nuget/home/issues).</span><span class="sxs-lookup"><span data-stu-id="c58c0-125">If you have any issues with the NuGet Visual Studio client, the Powershell commands, or the command-line executable you can log those issues and monitor their progress on our [GitHub Home repository issues list](http://github.com/nuget/home/issues).</span></span>  <span data-ttu-id="c58c0-126">Verfolgen wir Probleme für den Katalog in unserer [GitHub NuGetGallery-Repository](http://github.com/nuget/NuGetGallery/issues).</span><span class="sxs-lookup"><span data-stu-id="c58c0-126">We are tracking issues for the gallery in our [GitHub NuGetGallery repository](http://github.com/nuget/NuGetGallery/issues).</span></span>


## <a name="stay-tuned"></a><span data-ttu-id="c58c0-127">Bleiben Sie dran</span><span class="sxs-lookup"><span data-stu-id="c58c0-127">Stay Tuned</span></span>

<span data-ttu-id="c58c0-128">Bitte achten Sie auf [unserem Blog](http://blog.nuget.org) weitere Bearbeitung und Ankündigungen für NuGet 3.0!</span><span class="sxs-lookup"><span data-stu-id="c58c0-128">Please keep an eye on [our blog](http://blog.nuget.org) for more progress and announcements for NuGet 3.0!</span></span>