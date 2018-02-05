---
title: 'Vorgehensweise: Erstellen von NuGet-Symbolpaketen | Microsoft-Dokumentation'
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 9/12/2017
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 4667a70d-5a17-4f1e-b2f2-b8d0c6af3882
description: "Vorgehensweise bei der Erstellung von NuGet-Paketen, die nur Symbole für die Unterstützung des Debuggings anderer NuGet-Pakete in Visual Studio enthalten."
keywords: "NuGet-Symbolpakete, Debugging von NuGet-Paketen, Unterstützung von NuGet-Debugging, Paketsymbole, Symbolpaketkonventionen"
ms.reviewer:
- anangaur
- karann-msft
- unniravindranathan
ms.openlocfilehash: 2bdb8a2c946618b0c297c70bf7fcf6a9038b2a02
ms.sourcegitcommit: a40c1c1cc05a46410f317a72f695ad1d80f39fa2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="creating-symbol-packages"></a><span data-ttu-id="56f78-104">Erstellen von Symbolpaketen</span><span class="sxs-lookup"><span data-stu-id="56f78-104">Creating symbol packages</span></span>

<span data-ttu-id="56f78-105">Neben der Erstellung von Paketen für nuget.org oder andere Quellen unterstützt NuGet auch die Erstellung zugehöriger Symbolpakete sowie die Veröffentlichung dieser Pakete im [SymbolSource-Repository](http://www.symbolsource.org/Public).</span><span class="sxs-lookup"><span data-stu-id="56f78-105">In addition to building packages for nuget.org or other sources, NuGet also supports creating associated symbol packages and publishing them to the [SymbolSource repository](http://www.symbolsource.org/Public).</span></span>

<span data-ttu-id="56f78-106">Paketverbraucher können anschließend `http://srv.symbolsource.org/pdb/Public` zu ihren Symbolquellen in Visual Studio hinzufügen, wodurch Paketcode im Visual Studio Debugger schrittweise verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="56f78-106">Package consumers can then add `http://srv.symbolsource.org/pdb/Public` to their symbol sources in Visual Studio, which allows stepping into package code in the Visual Studio debugger.</span></span> <span data-ttu-id="56f78-107">Weitere Einzelheiten zu diesem Prozess finden Sie unter [Angeben von Symbol- (PDB) und Quelldateien im Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span><span class="sxs-lookup"><span data-stu-id="56f78-107">See [Specify symbol (.pdb) and source files in the Visual Studio debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger) for details on that process.</span></span>


## <a name="creating-a-symbol-package"></a><span data-ttu-id="56f78-108">Erstellen eines Symbolpakets</span><span class="sxs-lookup"><span data-stu-id="56f78-108">Creating a symbol package</span></span>

<span data-ttu-id="56f78-109">Folgen Sie den folgenden Konventionen, um ein Symbolpaket zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="56f78-109">To create a symbol package, follow these conventions:</span></span>

- <span data-ttu-id="56f78-110">Geben Sie dem Primärpaket (mit Ihrem Code) den Namen `{identifier}.nupkg`, und schließen Sie alle Dateien außer `.pdb` ein.</span><span class="sxs-lookup"><span data-stu-id="56f78-110">Name the primary package (with your code) `{identifier}.nupkg` and include all your files except `.pdb` files.</span></span>
- <span data-ttu-id="56f78-111">Geben Sie dem Symbolpaket den Namen `{identifier}.symbols.nupkg`, und schließen Sie Ihre Assembly-DLL, `.pdb`-Dateien, XML DOC-Dateien und Quelldateien ein (siehe die folgenden Abschnitte).</span><span class="sxs-lookup"><span data-stu-id="56f78-111">Name the symbol package `{identifier}.symbols.nupkg` and include your assembly DLL, `.pdb` files, XMLDOC files, source files (see the sections that follow).</span></span>

<span data-ttu-id="56f78-112">Sie können beide Pakete mit der Option `-Symbols` aus einer `.nuspec`-Datei oder einer Projektdatei erstellen:</span><span class="sxs-lookup"><span data-stu-id="56f78-112">You can create both packages with the `-Symbols` option, either from a `.nuspec` file or a project file:</span></span>

```
nuget pack MyPackage.nuspec -Symbols

nuget pack MyProject.csproj -Symbols
```

<span data-ttu-id="56f78-113">Beachten Sie, dass für `pack` Mono 4.4.2 unter Mac OS X erforderlich ist und dass dieser Befehl auf Linux-Systemen nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="56f78-113">Note that `pack` requires Mono 4.4.2 on Mac OS X and does not work on Linux systems.</span></span> <span data-ttu-id="56f78-114">Auf einem Mac müssen Sie ebenfalls Windows-Pfadnamen in der `.nuspec`-Datei in Pfade im Unix-Format konvertieren.</span><span class="sxs-lookup"><span data-stu-id="56f78-114">On a Mac, you must also convert Windows pathnames in the `.nuspec` file to Unix-style paths.</span></span>

## <a name="symbol-package-structure"></a><span data-ttu-id="56f78-115">Symbolpaketstruktur</span><span class="sxs-lookup"><span data-stu-id="56f78-115">Symbol package structure</span></span>

<span data-ttu-id="56f78-116">Ein Symbolpaket kann auf die gleiche Weise wie ein Bibliothekspaket auf mehrere Zielframeworks abzielen. Die Struktur des Ordners `lib` müsste demnach mit dem Primärpaket identisch sein, darin inbegriffen sind neben der DLL lediglich `.pdb`-Dateien.</span><span class="sxs-lookup"><span data-stu-id="56f78-116">A symbol package can target multiple target frameworks in the same way that a library package does, so the structure of the `lib` folder should be exactly the same as the primary package, only including `.pdb` files alongside the DLL.</span></span>

<span data-ttu-id="56f78-117">Ein Symbolpaket, das .NET 4.0 und Silverlight 4 ansteuert, würde beispielsweise folgendes Layout aufweisen:</span><span class="sxs-lookup"><span data-stu-id="56f78-117">For example, a symbol package that targets .NET 4.0 and Silverlight 4 would have this layout:</span></span>

    \lib
        \net40
            \MyAssembly.dll
            \MyAssembly.pdb
        \sl40
            \MyAssembly.dll
            \MyAssembly.pdb

<span data-ttu-id="56f78-118">Quelldateien werden dann in einem separaten speziellen Ordner mit dem Namen `src` angeordnet. Dabei muss die relative Struktur Ihres Quellrepositorys eingehalten werden.</span><span class="sxs-lookup"><span data-stu-id="56f78-118">Source files are then placed in a separate special folder named `src`, which must follow the relative structure of your source repository.</span></span> <span data-ttu-id="56f78-119">Grund dafür ist, dass PDB-Dateien absolute Pfade zu Quelldateien für die Kompilierung der entsprechenden DLL enthalten und diese während des Veröffentlichungsprozesses gefunden werden müssen.</span><span class="sxs-lookup"><span data-stu-id="56f78-119">This is because PDBs contain absolute paths to source files used to compile the matching DLL, and they need to be found during the publishing process.</span></span> <span data-ttu-id="56f78-120">Ein Basispfad (allgemeine Pfadpräfix) kann entfernt werden. Angenommen beispielsweise, eine Bibliothek wird aus folgenden Dateien erstellt:</span><span class="sxs-lookup"><span data-stu-id="56f78-120">A base path (common path prefix) can be stripped out. For example, consider a library built from these files:</span></span>

    C:\Projects
        \MyProject
            \Common
                \MyClass.cs
            \Full
                \Properties
                    \AssemblyInfo.cs
                \MyAssembly.csproj (producing \lib\net40\MyAssembly.dll)
            \Silverlight
                \Properties
                    \AssemblyInfo.cs
                \MySilverlightExtensions.cs
                \MyAssembly.csproj (producing \lib\sl4\MyAssembly.dll)

<span data-ttu-id="56f78-121">Neben dem Ordner `lib` müsste ein Symbolpaket folgendes Layout enthalten:</span><span class="sxs-lookup"><span data-stu-id="56f78-121">Apart from the `lib` folder, a symbol package would need to contain this layout:</span></span>

    \src
        \Common
            \MyClass.cs
        \Full
            \Properties
                \AssemblyInfo.cs
        \Silverlight
            \Properties
                \AssemblyInfo.cs
            \MySilverlightExtensions.cs

## <a name="referring-to-files-in-the-nuspec"></a><span data-ttu-id="56f78-122">Verweisen auf Dateien in der NUSPEC-Datei</span><span class="sxs-lookup"><span data-stu-id="56f78-122">Referring to files in the nuspec</span></span>

<span data-ttu-id="56f78-123">Ein Symbolpaket kann, wie im vorherigen Abschnitt beschrieben, nach Konventionen aus einer Ordnerstruktur erstellt werden oder durch Angabe der zugehörigen Inhalte im Abschnitt `files` des Manifests.</span><span class="sxs-lookup"><span data-stu-id="56f78-123">A symbol package can be built by conventions, from a folder structure as described in the previous section, or by specifying its contents in the `files` section of the manifest.</span></span> <span data-ttu-id="56f78-124">Verwenden Sie für die Erstellung des im vorherigen Abschnitts angezeigten Pakets beispielsweise Folgendes in der `.nuspec`-Datei:</span><span class="sxs-lookup"><span data-stu-id="56f78-124">For example, to build the package shown in the previous section, use the following in the `.nuspec` file:</span></span>

```xml
<files>
    <file src="Full\bin\Debug\*.dll" target="lib\net40" />
    <file src="Full\bin\Debug\*.pdb" target="lib\net40" />
    <file src="Silverlight\bin\Debug\*.dll" target="lib\sl40" />
    <file src="Silverlight\bin\Debug\*.pdb" target="lib\sl40" />
    <file src="**\*.cs" target="src" />
</files>
```

## <a name="publishing-a-symbol-package"></a><span data-ttu-id="56f78-125">Veröffentlichen eines Symbolpakets</span><span class="sxs-lookup"><span data-stu-id="56f78-125">Publishing a symbol package</span></span>

> [!Important]
> <span data-ttu-id="56f78-126">Sie müssen [nuget.exe v4.1.0 oder höher](https://www.nuget.org/downloads) verwenden, um Pakete per Push an nuget.org übertragen zu können, da so die erforderlichen [NuGet-Protokolle](../api/nuget-protocols.md) implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="56f78-126">To push packages to nuget.org you must use [nuget.exe v4.1.0 or above](https://www.nuget.org/downloads), which implements the required [NuGet protocols](../api/nuget-protocols.md).</span></span>

1. <span data-ttu-id="56f78-127">Speichern Sie Ihren API-Schlüssel der Einfachheit halber zunächst mit NuGet (siehe [Paket veröffentlichen](../create-packages/publish-a-package.md)). Dieser gilt dann für nuget.org und symbolsource.org, da symbolsource.org mit nuget.org überprüft, ob Sie der Paketbesitzer sind.</span><span class="sxs-lookup"><span data-stu-id="56f78-127">For convenience, first save your API key with NuGet (see [publish a package](../create-packages/publish-a-package.md), which will apply to both nuget.org and symbolsource.org, because symbolsource.org will check with nuget.org to verify that you are the package owner.</span></span>

    ```
    nuget SetApiKey Your-API-Key
    ```

1. <span data-ttu-id="56f78-128">Nachdem Sie Ihr primäres Paket auf nuget.org veröffentlicht haben, übertragen Sie das Symbolpaket wie folgt mithilfe von Push, wobei symbolsource.org automatisch als Ziel verwendet wird, da `.symbols` im Dateinamen enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="56f78-128">After publishing your primary package to nuget.org, push the symbol package as follows, which will automatically use symbolsource.org as the target because of the `.symbols` in the filename:</span></span>

    ```
    nuget push MyPackage.symbols.nupkg
    ```
> [!Note]
> <span data-ttu-id="56f78-129">Bei nuget.exe 4.5.0 oder höher werden die Symbolpakete nicht automatisch mithilfe von Push auf symbolsource.org übertragen. Sie müssten die Symbolpakete separat mithilfe von Push übertragen, wie im nächsten Schritt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="56f78-129">With nuget.exe 4.5.0 or above, the symbols packages are not automatically pushed to symbolsource.org. You would need to push the symbols packages separately as explained in the next step.</span></span>

1. <span data-ttu-id="56f78-130">Verwenden Sie die Option `-Source`, um ein anderes Symbolrepository zu veröffentlichen oder um ein Symbolpaket per Push zu übertragen, das nicht den Namenskonventionen folgt:</span><span class="sxs-lookup"><span data-stu-id="56f78-130">To publish to a different symbol repository, or to push a symbol package that doesn't follow the naming convention, use the `-Source` option:</span></span>

    ```
    nuget push MyPackage.symbols.nupkg -source https://nuget.smbsrc.net/
    ```

1. <span data-ttu-id="56f78-131">Sie können auch das primäre Paket und Symbolpakete gleichzeitig mithilfe von Push in beide Repositorys übertragen, indem Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="56f78-131">You can also push both primary and symbol packages to both repositories at the same time using the following:</span></span>

    ```
    nuget push MyPackage.nupkg
    ```

<span data-ttu-id="56f78-132">In diesem Fall veröffentlicht NuGet `MyPackage.symbols.nupkg`, falls vorhanden, auf https://nuget.smbsrc.net/ (die Push-URL für symbolsource.org), nachdem das primäre Paket auf nuget.org veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="56f78-132">In this case, NuGet will publish `MyPackage.symbols.nupkg`, if present, to https://nuget.smbsrc.net/ (the push URL for symbolsource.org), after it publishes the primary package to nuget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="56f78-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56f78-133">See Also</span></span>

 - <span data-ttu-id="56f78-134"><a href="https://www.symbolsource.org/Public/Wiki/Using" target="_blank">Verwenden von SymbolSource</a> (symbolsource.org)</span><span class="sxs-lookup"><span data-stu-id="56f78-134"><a href="https://www.symbolsource.org/Public/Wiki/Using" target="_blank">Using SymbolSource</a> (symbolsource.org)</span></span>