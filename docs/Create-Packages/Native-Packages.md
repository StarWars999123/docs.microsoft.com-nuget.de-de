---
title: Erstellen von nativen NuGet-Paketen | Microsoft-Dokumentation
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 1/9/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 7a70d748-efe2-4f8f-a3fd-67ddb0f6214e
description: "Informationen über das Erstellen von nativen NuGet-Paketen, die C++-Code statt verwaltetem Code enthalten und in C++-Projekten verwendet werden können."
keywords: "Native NuGet-Pakete, C++-Pakete für NuGet, native Codepakete, C++-Zielprojekte"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: fa5baaa6ecbad0f5f6dd85d657679ffbbbc8a47a
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="creating-native-packages"></a><span data-ttu-id="aee82-104">Erstellen von nativen Paketen</span><span class="sxs-lookup"><span data-stu-id="aee82-104">Creating native packages</span></span>

<span data-ttu-id="aee82-105">Ein natives Paket enthält nativen C++-Code anstelle von verwaltetem Code, sodass es innerhalb von C++-Projekten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="aee82-105">A native package contains native C++ code instead of managed code, allowing it to be used within C++ projects.</span></span> <span data-ttu-id="aee82-106">(Lesen Sie hierzu den Absatz zum Thema [Native C++-Pakete](../consume-packages/finding-and-choosing-packages.md#native-cpp-packages) im Abschnitt zum Thema „Verwenden“.)</span><span class="sxs-lookup"><span data-stu-id="aee82-106">(See [Native C++ Packages](../consume-packages/finding-and-choosing-packages.md#native-cpp-packages) in the Consume section.)</span></span>

<span data-ttu-id="aee82-107">Ein Paket muss das Framework `native` als Ziel haben, damit Sie dieses in einem C++-Projekt verwenden können.</span><span class="sxs-lookup"><span data-stu-id="aee82-107">To be consumable in a C++ project, a package must target the `native` framework.</span></span> <span data-ttu-id="aee82-108">Derzeit sind diesem Framework keine Versionsnummern zugeordnet, da NuGet alle C++-Projekte gleich behandelt.</span><span class="sxs-lookup"><span data-stu-id="aee82-108">At present there are not any version numbers associated with this framework as NuGet treats all C++ projects the same.</span></span>

> [!Note]
> <span data-ttu-id="aee82-109">Schließen Sie im Abschnitt `<tags>` Ihrer `.nuspec`-Datei unbedingt *native* ein, damit andere Entwickler das Paket finden können, indem sie nach diesem Tag suchen.</span><span class="sxs-lookup"><span data-stu-id="aee82-109">Be sure to include *native* in the `<tags>` section of your `.nuspec` to help other developers find your package by searching on that tag.</span></span>

<span data-ttu-id="aee82-110">Native NuGet-Pakete mit dem Ziel `native` stellen dann in den Ordnern `\build`, `\content` und `\tools` Dateien bereit; `\lib` wird in diesem Fall nicht verwendet, da NuGet keine direkten Verweise auf C++-Projekte hinzufügen kann.</span><span class="sxs-lookup"><span data-stu-id="aee82-110">Native NuGet packages targeting `native` then provide files in `\build`, `\content`, and `\tools` folders; `\lib` is not used in this case (NuGet cannot directly add references to a C++ project).</span></span> <span data-ttu-id="aee82-111">Ein Paket kann im Ordner `\build` auch Zieldateien und Eigenschaftendateien enthalten, die NuGet automatisch in die Projekte importiert, die das Paket verwenden.</span><span class="sxs-lookup"><span data-stu-id="aee82-111">A package may also include targets and props files in `\build` that NuGet will automatically import into projects that consume the package.</span></span> <span data-ttu-id="aee82-112">Diese Dateien müssen den gleichen Namen wie die Paket-IDs mit den Erweiterungen `.targets` und/oder `.props` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="aee82-112">Those files must be named the same as the package ID with the `.targets` and/or `.props` extensions.</span></span> <span data-ttu-id="aee82-113">Beispielsweise enthält das Paket [cpprestsdk](https://nuget.org/packages/cpprestsdk/) im Ordner `\build` eine Datei des Typs `cpprestsdk.targets`.</span><span class="sxs-lookup"><span data-stu-id="aee82-113">For example, the [cpprestsdk](https://nuget.org/packages/cpprestsdk/) package includes a `cpprestsdk.targets` file in its `\build` folder.</span></span>

<span data-ttu-id="aee82-114">Der Ordner `\build` kann für alle NuGet-Pakete und nicht nur für native Pakete verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aee82-114">The `\build` folder can be used for all NuGet packages and not just native packages.</span></span> <span data-ttu-id="aee82-115">Der Ordner `\build` berücksichtigt Zielframeworks ebenso wie die Ordner `\content`, `\lib` und `\tools`.</span><span class="sxs-lookup"><span data-stu-id="aee82-115">The `\build` folder respects target frameworks just like the `\content`, `\lib`, and `\tools` folders.</span></span> <span data-ttu-id="aee82-116">Dies bedeutet, dass Sie einen Ordner namens `\build\net40` und einen namens `\build\net45` erstellen können und NuGet die entsprechenden Eigenschaftendateien und Zieldateien dann in das Projekt importiert.</span><span class="sxs-lookup"><span data-stu-id="aee82-116">This means you can create a `\build\net40` folder and a `\build\net45` folder and NuGet will import the appropriate props and targets files into the project.</span></span> <span data-ttu-id="aee82-117">(PowerShell-Skripts sind zum Importieren von MSBuild-Zielen nicht erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="aee82-117">(Use of PowerShell scripts to import MSBuild targets is not needed.)</span></span>