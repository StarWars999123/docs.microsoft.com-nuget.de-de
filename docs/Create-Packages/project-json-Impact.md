---
title: "Auswirkungen von „project.json“ auf das Erstellen von NuGet-Paketen | Microsoft-Dokumentation"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 1/9/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 983485df-9375-4827-b58b-70065320ee37
description: "Informationen darüber, was die Implementierung von „project.json“ in NuGet 3.x für Paketersteller bedeutet, z.B. nicht unterstützte Features und Paketformate sowie nicht unterstützter Inhalt."
keywords: "NuGet und „project.json“, Auswirkungen von „project.json“, Überlegungen zur Paketerstellung, Features von „project.json“"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 69a6bbbe1c96b06dbba7ac787b836b8b62c438ec
ms.sourcegitcommit: a40c1c1cc05a46410f317a72f695ad1d80f39fa2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="impact-of-projectjson-when-creating-packages"></a><span data-ttu-id="e656a-104">Auswirkungen von „project.json“ auf das Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="e656a-104">Impact of project.json when creating packages</span></span>

<span data-ttu-id="e656a-105">Das in NuGet 3 und höher verwendete System `project.json` wirkt sich, wie in den folgenden Abschnitten beschrieben, für Paketersteller auf verschiedene Arten aus.</span><span class="sxs-lookup"><span data-stu-id="e656a-105">The `project.json` system used in NuGet 3+ affects package authors in several ways as described in the following sections.</span></span>

## <a name="changes-affecting-existing-packages-usage"></a><span data-ttu-id="e656a-106">Änderungen, die das Verwenden vorhandener Pakete betreffen</span><span class="sxs-lookup"><span data-stu-id="e656a-106">Changes affecting existing packages usage</span></span>

<span data-ttu-id="e656a-107">NuGet-Pakete unterstützen üblicherweise einige Features, die nicht in die transitive Welt übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e656a-107">Traditional NuGet packages support a set of features that are not carried over to the transitive world.</span></span>

### <a name="install-and-uninstall-scripts-are-ignored"></a><span data-ttu-id="e656a-108">Installations- und Deinstallationsskripts werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e656a-108">Install and uninstall scripts are ignored</span></span>

<span data-ttu-id="e656a-109">Dem Modell zur transitiven Wiederherstellung, das in einem anderen Artikel im Abschnitt zum Thema [Abhängigkeitsauflösung](../consume-packages/dependency-resolution.md#dependency-resolution-with-packagereference-and-projectjson) beschrieben wird, ist das Konzept der „Paketinstallationszeit“ nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="e656a-109">The transitive restore model, described in [Dependency resolution](../consume-packages/dependency-resolution.md#dependency-resolution-with-packagereference-and-projectjson), does not have a concept of "package install time".</span></span> <span data-ttu-id="e656a-110">Ein Paket ist entweder vorhanden oder nicht vorhanden. Es existiert also kein einheitlicher Prozess, der beim Installieren eines Pakets abläuft.</span><span class="sxs-lookup"><span data-stu-id="e656a-110">A package is either present or not present, but there is no consistent process that occurs when a package is installed.</span></span>

<span data-ttu-id="e656a-111">Des Weiteren wurden Installationsskripts nur in Visual Studio unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e656a-111">Also, install scripts were supported only in Visual Studio.</span></span> <span data-ttu-id="e656a-112">Andere integrierte Entwicklungsumgebungen konnten nur durch Modellieren der Visual Studio-Erweiterbarkeits-API versuchen, solche Skripts zu unterstützen. In üblichen Editoren und Befehlszeilentools war dagegen keine Unterstützung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e656a-112">Other IDEs had to mock the Visual Studio extensibility API to attempt to support such scripts, and no support was available in common editors and command-line tools.</span></span>

### <a name="content-transforms-are-not-supported"></a><span data-ttu-id="e656a-113">Transformationen von Inhalten werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e656a-113">Content transforms are not supported.</span></span>

<span data-ttu-id="e656a-114">Transformationen werden, ähnlich wie Installationsskripts, mithilfe des Prozesses der Paketinstallation ausgeführt und sind in der Regel nicht idempotent.</span><span class="sxs-lookup"><span data-stu-id="e656a-114">Similar to install scripts, transforms run on package install and are typically not idempotent.</span></span> <span data-ttu-id="e656a-115">Da das Konzept der „Installationszeit“ nicht mehr vorhanden ist, werden XDT Transform und ähnliche Features nicht unterstützt. Diese werden ignoriert, wenn ein entsprechendes Paket in einem transitiven Szenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e656a-115">Since there is no install time anymore, XDT Transform and similar features are not supported, and are ignored if such a package is used in a transitive scenario.</span></span>


### <a name="content"></a><span data-ttu-id="e656a-116">Inhalt</span><span class="sxs-lookup"><span data-stu-id="e656a-116">Content</span></span>

<span data-ttu-id="e656a-117">NuGet-Pakete transportieren üblicherweise Inhaltsdateien, z.B. Quellcode- und Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="e656a-117">Traditional NuGet packages are shipping content files such as source code and configuration files.</span></span> <span data-ttu-id="e656a-118">Diese werden in der Regel in zwei Szenarios verwendet:</span><span class="sxs-lookup"><span data-stu-id="e656a-118">There are used typically in two scenarios:</span></span>

1. <span data-ttu-id="e656a-119">Als Startdateien, die im Projekt abgelegt werden, damit der Benutzer diese zu einem späteren Zeitpunkt bearbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e656a-119">Initial files dropped into the project so the user can edit them at a later time.</span></span> <span data-ttu-id="e656a-120">Ein gängiges Beispiel dafür sind Standardkonfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="e656a-120">The common example is default configuration files.</span></span>

2. <span data-ttu-id="e656a-121">Inhaltsdateien, die als Ergänzung zu den im Projekt installierten Assemblys verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e656a-121">Content files used as companions to the assemblies installed in the project.</span></span> <span data-ttu-id="e656a-122">Ein Beispiel dafür wäre ein Logobild, das von einer Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e656a-122">The example here would be a logo image used by an assembly.</span></span>

<span data-ttu-id="e656a-123">Die Unterstützung von Inhaltsdateien ist derzeit aus ähnlichen Gründen deaktiviert, wie der für Skripts und Transformationen. Wir arbeiten jedoch bereits an deren Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e656a-123">Support for content is currently disabled for similar reasons for scripts and transforms, but we are in the process of designing support for content.</span></span>

<span data-ttu-id="e656a-124">Inhaltsdateien können weiterhin in Pakete übertragen werden, werden aber derzeit ignoriert. Benutzer können diese dennoch an die richtige Stelle kopieren.</span><span class="sxs-lookup"><span data-stu-id="e656a-124">Content files can still be carried inside the packages, and are ignored currently, however the end user can still copy them into the right spot.</span></span>

<span data-ttu-id="e656a-125">Sie können einen der Vorschläge, wie Inhaltsdateien wieder eingebunden werden könnten, hier einsehen und seinen Fortschritt verfolgen: [https://github.com/NuGet/Home/issues/627](https://github.com/NuGet/Home/issues/627).</span><span class="sxs-lookup"><span data-stu-id="e656a-125">You can see one of the proposals for bringing back content files, and follow its progress, here: [https://github.com/NuGet/Home/issues/627](https://github.com/NuGet/Home/issues/627).</span></span>

## <a name="impact-for-package-authors"></a><span data-ttu-id="e656a-126">Auswirkungen für Paketersteller</span><span class="sxs-lookup"><span data-stu-id="e656a-126">Impact for package authors</span></span>

<span data-ttu-id="e656a-127">Pakete, die auf die oben genannten Features zurückgreifen, müssen einen anderen Mechanismus verwenden.</span><span class="sxs-lookup"><span data-stu-id="e656a-127">Packages using the above features would have to use a different mechanism.</span></span> <span data-ttu-id="e656a-128">Der in den meisten Fällen für diesen Zweck geeignete Mechanismus wäre „MSBuild-Ziele und -Eigenschaften“, da dieser weiterhin vollständig unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e656a-128">The most commonly useful mechanism for this would be the MSBuild targets/props that continues to get fully supported.</span></span> <span data-ttu-id="e656a-129">Das Buildsystem kann auch andere Konventionen aus dem Paket übernehmen.</span><span class="sxs-lookup"><span data-stu-id="e656a-129">The build system can choose to pick up other conventions in the package.</span></span> <span data-ttu-id="e656a-130">Auf diese Weise werden MSBuild-Ziele sowie Roslyn-Analysetools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e656a-130">This is how MSBuild targets are supported as well as Roslyn analyzers.</span></span> <span data-ttu-id="e656a-131">Es ist möglich, Pakete zu erstellen, die Ziele und Analysetools für die Szenarios `packages.config` und `project.json` unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e656a-131">It is possible to build packages that supports targets and analyzers for `packages.config` and `project.json` scenarios.</span></span>

<span data-ttu-id="e656a-132">Pakete, die darauf abzielen, das Projekt zum Erleichtern des Starts zu verändern, können meist nur in wenigen Szenarios verwendet werden. Daher sollten die Pakete stattdessen eine Infodatei oder Richtlinien zum Verwenden des Pakets bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e656a-132">Packages that attempt to modify the project to ease startup typically work in a very limited set of scenarios, and should instead provide a readme, or guidance on how to use the package.</span></span>

<span data-ttu-id="e656a-133">Bei den meisten vorhandenen Paketen ist das Verwenden des unten beschriebenen Paketformats nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e656a-133">Most existing packages should not need to use the package format described below.</span></span>

<span data-ttu-id="e656a-134">Das Format ermöglicht, dass nativer Inhalt in einem erstklassigen Szenario verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e656a-134">The format enables native content as a first class scenario.</span></span> <span data-ttu-id="e656a-135">Dies bedeutet, dass verwaltete Assemblys davon abhängig sind, dass hardwaregebundene Implementierungen binäre Implementierungen neben verwalteten Assemblys auf Grundlage der Zielplattform liefern.</span><span class="sxs-lookup"><span data-stu-id="e656a-135">This means that managed assemblies depending on close to hardware implementations to ship binary implementations alongside the managed assemblies based on the target platform.</span></span> <span data-ttu-id="e656a-136">Das Paket „System.IO.Compression“ nutzt diese Technologie beispielsweise.</span><span class="sxs-lookup"><span data-stu-id="e656a-136">For example System.IO.Compression package is utilizing this technology.</span></span> [<span data-ttu-id="e656a-137">https://www.nuget.org/packages/System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="e656a-137">https://www.nuget.org/packages/System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)

<span data-ttu-id="e656a-138">Falls die oben genannte Funktionalität nicht unbedingt erforderlich ist, empfiehlt es sich also, bei dem bestehenden Paketformat zu bleiben, da das hier beschriebene Format nur von NuGet 3.x und höher unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e656a-138">In summary if the functionality above is not absolutely necessary, we recommend sticking with the existing package format, as the format described here is supported only by NuGet 3.x+.</span></span>

<span data-ttu-id="e656a-139">Mithilfe von Shims ist es möglich, Pakete zu erstellen, die sowohl in `packages.config`- als auch in `project.json`-Szenarios funktionieren. Jedoch ist es oft leichter, die Pakete auf herkömmliche Weise zu strukturieren – ohne die oben erwähnten veralteten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e656a-139">It would be possible to build packages to work for both `packages.config` and `project.json` scenarios through shimming, however it's often simpler to just structure the packages the traditional way, without the deprecated features mentioned above.</span></span>


## <a name="3x-package-format"></a><span data-ttu-id="e656a-140">Paketformat „3.x“</span><span class="sxs-lookup"><span data-stu-id="e656a-140">3.x package format</span></span>  ##

<span data-ttu-id="e656a-141">Das Paketformat „3.x“ lässt mehrere zusätzliche Funktionen zu, die NuGet 2.x nicht zulässt:</span><span class="sxs-lookup"><span data-stu-id="e656a-141">The 3.x package format allows for several additional features beyond NuGet 2.x:</span></span>

1. <span data-ttu-id="e656a-142">Definieren einer Referenzassembly, die für die Kompilierung verwendet wird und mehrerer Implementierungsassemblys, die für die Laufzeit auf verschiedenen Plattformen bzw. Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e656a-142">Defining a reference assembly used for compilation and a set of implementation assemblies used for runtime on different platforms/devices.</span></span> <span data-ttu-id="e656a-143">Dies ermöglicht es Ihnen, plattformspezifische APIs zu verwenden und zeitgleich für Ihre Benutzer eine gemeinsam genutzte Oberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e656a-143">Which allows you to take advantage of platform specific APIs while providing a common surface area for your consumers.</span></span> <span data-ttu-id="e656a-144">Dadurch wird Ihnen insbesondere das Schreiben von portablen Zwischenbibliotheken erleichtert.</span><span class="sxs-lookup"><span data-stu-id="e656a-144">Specifically this makes writing intermediate portable libraries easier.</span></span>

2. <span data-ttu-id="e656a-145">Ermöglicht Paketen, auf Plattformen, z.B. Betriebssystemen oder CPU-Architektur, zu pivotieren</span><span class="sxs-lookup"><span data-stu-id="e656a-145">Allows packages to pivot on platforms e.g. operating systems or CPU architecture.</span></span>

3. <span data-ttu-id="e656a-146">Ermöglicht das Trennen von plattformspezifischen Implementierungen, um Pakete in Ergänzungen zu verwandeln</span><span class="sxs-lookup"><span data-stu-id="e656a-146">Allows for separation of platform specific implementations to companion packages.</span></span>

4. <span data-ttu-id="e656a-147">Unterstützen nativer Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="e656a-147">Support Native dependencies as a first class citizen.</span></span>