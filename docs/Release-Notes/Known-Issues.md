---
title: Bekannte Probleme mit NuGet | Microsoft-Dokumentation
author: karann-msft
ms.author: karann-msft
manager: ghogen
ms.date: 11/11/2016
ms.topic: article
ms.prod: nuget
ms.technology: 
description: Bekannte Probleme mit NuGet, z.B. mit der Authentifizierung, der Installation von Paketen und mit Tools.
keywords: Bekannte Probleme mit NuGet, Probleme mit NuGet
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 2b9190c058215d9e63894de45c0c55c8ddae0e0f
ms.sourcegitcommit: b0af28d1c809c7e951b0817d306643fcc162a030
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="known-issues-with-nuget"></a><span data-ttu-id="993f5-104">Bekannte Probleme mit NuGet</span><span class="sxs-lookup"><span data-stu-id="993f5-104">Known Issues with NuGet</span></span>

<span data-ttu-id="993f5-105">Im Folgenden finden Sie die häufigsten bekannten Probleme mit NuGet, die wiederholt gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="993f5-105">These are the most common known issues with NuGet that are repeatedly reported.</span></span> <span data-ttu-id="993f5-106">Wenn Sie Probleme beim Installieren von NuGet oder dem Verwalten von Paketen haben, lesen Sie sich diese bekannten Probleme und ihre Lösungen durch.</span><span class="sxs-lookup"><span data-stu-id="993f5-106">If you are having trouble installing NuGet or managing packages, please take a look through these known issues and their resolutions.</span></span>

> [!Note]
> <span data-ttu-id="993f5-107">Ab NuGet 4.0 sind bekannte Probleme Teil der Anmerkungen zur jeweiligen Version.</span><span class="sxs-lookup"><span data-stu-id="993f5-107">Starting with NuGet 4.0, known issues are a part of the respective release notes.</span></span>

## <a name="authentication-issues-with-nuget-feeds-in-vsts-with-nugetexe-v343"></a><span data-ttu-id="993f5-108">Authentifizierungsprobleme mit NuGet-Feeds in VSTS mit „nuget.exe“ (Version 3.4.3)</span><span class="sxs-lookup"><span data-stu-id="993f5-108">Authentication issues with NuGet feeds in VSTS with nuget.exe v3.4.3</span></span>

<span data-ttu-id="993f5-109">**Problem:**</span><span class="sxs-lookup"><span data-stu-id="993f5-109">**Problem:**</span></span>

<span data-ttu-id="993f5-110">Wenn der folgende Befehl verwendet wird, um die Anmeldeinformationen zu speichern, wird das persönliche Zugriffstoken doppelt verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="993f5-110">When we use the following command to store the credentials, we end up double encrypting the Personal Access Token.</span></span>

<span data-ttu-id="993f5-111">$PAT = "Ihr persönliches Zugriffstoken" $Feed = "Ihre URL" .\nuget.exe sources add -Name Test -Source $Feed -UserName $UserName -Password $PAT</span><span class="sxs-lookup"><span data-stu-id="993f5-111">$PAT = "Your personal access token" $Feed = "Your url" .\nuget.exe sources add -Name Test -Source $Feed -UserName $UserName -Password $PAT</span></span>

<span data-ttu-id="993f5-112">**Problemumgehung:**</span><span class="sxs-lookup"><span data-stu-id="993f5-112">**Workaround:**</span></span>

<span data-ttu-id="993f5-113">Speichern Sie Kennwörter in Klartext mithilfe der Option [-StorePasswordInClearText](../tools/cli-ref-sources.md).</span><span class="sxs-lookup"><span data-stu-id="993f5-113">Store passwords in clear text using the [-StorePasswordInClearText](../tools/cli-ref-sources.md) option.</span></span>

## <a name="error-installing-packages-with-nuget-34-341"></a><span data-ttu-id="993f5-114">Fehler beim Installieren von Paketen mit NuGet 3.4 und 3.4.1</span><span class="sxs-lookup"><span data-stu-id="993f5-114">Error installing packages with NuGet 3.4, 3.4.1</span></span>

<span data-ttu-id="993f5-115">**Problem:**</span><span class="sxs-lookup"><span data-stu-id="993f5-115">**Problem:**</span></span>

<span data-ttu-id="993f5-116">In NuGet 3.4 und 3.4.1 werden keine Quellen als verfügbar gemeldet, wenn das NuGet-Add-In verwendet wird, und es ist nicht möglich, neue Quellen im Konfigurationsfenster hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="993f5-116">In NuGet 3.4 and 3.4.1, when using the NuGet add-in, no sources are reported as available and you are unable to add new sources in the configuration window.</span></span> <span data-ttu-id="993f5-117">Das Ergebnis ähnelt der folgenden Abbildung:</span><span class="sxs-lookup"><span data-stu-id="993f5-117">The result is similar to the image below:</span></span>

![NuGet-Konfigurationsfenster ohne Quellen](./media/knownIssue-34-NoSources.PNG)

<span data-ttu-id="993f5-119">Die `NuGet.Config`-Datei in Ihrem `%AppData%\NuGet\`-Ordner wurde versehentlich geleert.</span><span class="sxs-lookup"><span data-stu-id="993f5-119">The `NuGet.Config` file in your `%AppData%\NuGet\` folder has accidentally been emptied.</span></span> <span data-ttu-id="993f5-120">Behebung des Problems: Schließen Sie Visual Studio 2015, löschen Sie die `NuGet.Config`-Datei im `%AppData%\NuGet\`-Ordner, und starten Sie Visual Studio neu.</span><span class="sxs-lookup"><span data-stu-id="993f5-120">To fix this: Close Visual Studio 2015, delete the `NuGet.Config` file in the `%AppData%\NuGet\` folder and restart Visual Studio.</span></span>  <span data-ttu-id="993f5-121">Eine neue `NuGet.Config`-Datei wird generiert, und Sie können den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="993f5-121">A new `NuGet.Config` file will be generated and you are able to proceed.</span></span>

## <a name="error-installing-packages-with-nuget-27"></a><span data-ttu-id="993f5-122">Fehler beim Installieren von Paketen mit NuGet 2.7</span><span class="sxs-lookup"><span data-stu-id="993f5-122">Error installing packages with NuGet 2.7</span></span>

<span data-ttu-id="993f5-123">**Problem:**</span><span class="sxs-lookup"><span data-stu-id="993f5-123">**Problem:**</span></span>

<span data-ttu-id="993f5-124">In NuGet 2.7 wird beim Installieren eines Pakets, das Assemblyverweise enthält, wie im Folgenden dargestellt möglicherweise die Fehlermeldung **„Die Eingabezeichenfolge hat das falsche Format.“** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="993f5-124">In NuGet 2.7 or above, when you attempt to install any package which contains assembly references, you may receive the error message **"Input string was not in a correct format."**, like below:</span></span>

```ps
install-package log4net
    Installing 'log4net 2.0.0'.
    Successfully installed 'log4net 2.0.0'.
    Adding 'log4net 2.0.0' to Tyson.OperatorUpload.
    Install failed. Rolling back...
    install-package : Input string was not in a correct format.
    At line:1 char:1
        install-package log4net
        ~~~~~~~~~~~~~~~~~~~~~~~
        CategoryInfo : NotSpecified: (:) [Install-Package], FormatException
        FullyQualifiedErrorId : NuGetCmdletUnhandledException,NuGet.PowerShell.Commands.InstallPackageCommand
```

<span data-ttu-id="993f5-125">Dies wird durch die Typbibliothek für die COM-Komponente `VSLangProj.dll` verursacht, deren Registrierung auf Ihrem System aufgehoben wurde.</span><span class="sxs-lookup"><span data-stu-id="993f5-125">This is caused by the type library for the `VSLangProj.dll` COM component being unregistered on your system.</span></span> <span data-ttu-id="993f5-126">Dies kann beispielsweise vorkommen, wenn Sie zwei Versionen von Visual Studio parallel installiert haben und die ältere Version deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-126">This can happen, for example, when you have two versions of Visual Studio installed side-by-side and you then uninstall the older version.</span></span> <span data-ttu-id="993f5-127">Dadurch kann die Registrierung der oben genannten COM-Bibliothek versehentlich aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="993f5-127">Doing so may inadvertently unregister the above COM library.</span></span>

<span data-ttu-id="993f5-128">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="993f5-128">**Solution:**:</span></span>

<span data-ttu-id="993f5-129">Führen Sie diesen Befehl für eine **Eingabeaufforderung mit erhöhten Rechten** aus, um die Typbibliothek für `VSLangProj.dll` erneut zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-129">Run this command from an **elevated prompt** to re-register the type library for `VSLangProj.dll`</span></span>

    regsvr32 "C:\Program Files (x86)\Common Files\microsoft shared\MSEnv\VsLangproj.olb"

<span data-ttu-id="993f5-130">Wenn der Befehl fehlschlägt, überprüfen Sie, ob die Datei an diesem Speicherort vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-130">If the command fails, check to see if the file exists in that location.</span></span>

<span data-ttu-id="993f5-131">Weitere Informationen zu diesem Fehler finden Sie in dieser [Arbeitsaufgabe](https://nuget.codeplex.com/workitem/3609 "Arbeitsaufgabe 3609").</span><span class="sxs-lookup"><span data-stu-id="993f5-131">For more information about this error, see this [work item](https://nuget.codeplex.com/workitem/3609 "Work item 3609").</span></span>

## <a name="build-failure-after-package-update-in-vs-2012"></a><span data-ttu-id="993f5-132">Buildfehler nach dem Aktualisieren des Pakets in Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="993f5-132">Build failure after package update in VS 2012</span></span>

<span data-ttu-id="993f5-133">Das Problem: Sie verwenden Visual Studio 2012 RTM.</span><span class="sxs-lookup"><span data-stu-id="993f5-133">The problem: You are using VS 2012 RTM.</span></span> <span data-ttu-id="993f5-134">Wenn Sie NuGet-Pakete aktualisieren, wird Ihnen folgende Meldung angezeigt: „Mindestens ein Paket konnte nicht vollständig deinstalliert werden.“</span><span class="sxs-lookup"><span data-stu-id="993f5-134">When updating NuGet packages, you get this message: "One or more packages could not be completed uninstalled."</span></span> <span data-ttu-id="993f5-135">Sie werden außerdem dazu aufgefordert, Visual Studio neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="993f5-135">and you are prompted to restart Visual Studio.</span></span> <span data-ttu-id="993f5-136">Nach dem Neustart von Visual Studio erhalten Sie merkwürdige Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="993f5-136">After VS restart, you get weird build errors.</span></span>

<span data-ttu-id="993f5-137">Dies wird durch bestimmte Dateien in alten Paketen verursacht, die durch einen MSBuild-Hintergrundprozess gesperrt sind.</span><span class="sxs-lookup"><span data-stu-id="993f5-137">The cause is that certain files in the old packages are locked by a background MSBuild process.</span></span> <span data-ttu-id="993f5-138">Auch nach dem Neustart von Visual Studio verwendet der MSBuild-Hintergrundprozess diese Dateien noch in den alten Paketen, wodurch die Buildfehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="993f5-138">Even after VS restart, the background MSBuild process still uses the files in the old packages, causing the build failures.</span></span>

<span data-ttu-id="993f5-139">Dieses Problem kann durch die Installation eines Updates für Visual Studio 2012 behoben werden (z.B. Update 2 für Visual Studio 2012).</span><span class="sxs-lookup"><span data-stu-id="993f5-139">The fix is to install VS 2012 Update, e.g. VS 2012 Update 2.</span></span>

## <a name="upgrading-to-latest-nuget-from-an-older-version-causes-a-signature-verification-error"></a><span data-ttu-id="993f5-140">Das Upgrade auf die aktuelle NuGet-Version von einer älteren Version verursacht einen Signaturüberprüfungsfehler</span><span class="sxs-lookup"><span data-stu-id="993f5-140">Upgrading to latest NuGet from an older version causes a signature verification error</span></span>

<span data-ttu-id="993f5-141">Wenn Sie Visual Studio 2010 SP1 ausführen, wird Ihnen möglicherweise folgende Fehlermeldung angezeigt, wenn Sie versuchen, ein Upgrade für NuGet durchzuführen und eine ältere Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-141">If you are running VS 2010 SP1, you might run into the following error message when attempting to upgrade NuGet if you have an older version installed.</span></span>

![Installer für Visual Studio-Erweiterungen](./media/Visual-Studio-Extension-Installer.png)

<span data-ttu-id="993f5-143">In den Protokollen wird möglicherweise `SignatureMismatchException` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="993f5-143">When viewing the logs, you might see a mention of a `SignatureMismatchException`.</span></span>

<span data-ttu-id="993f5-144">Es gibt einen [Visual Studio 2010 SP1 hotfix (Hotfix für Visual Studio 2010 SP1)](http://bit.ly/vsixcertfix), den Sie installieren können, um dies zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="993f5-144">To prevent this from occurring, there is a [Visual Studio 2010 SP1 hotfix](http://bit.ly/vsixcertfix) you can install.</span></span>
<span data-ttu-id="993f5-145">Alternativ können Sie das Problem einfach umgehen, indem Sie NuGet zuerst deinstallieren (während Visual Studio als Administrator ausgeführt wird) und dann über den Erweiterungskatalog von Visual Studio erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-145">Alternatively, the workaround is to simply uninstall NuGet (while running Visual Studio as Administrator) and then install it from the VS Extension Gallery.</span></span>  <span data-ttu-id="993f5-146">Weitere Informationen finden Sie unter [http://support.microsoft.com/kb/2581019](http://support.microsoft.com/kb/2581019).</span><span class="sxs-lookup"><span data-stu-id="993f5-146">See [http://support.microsoft.com/kb/2581019](http://support.microsoft.com/kb/2581019) for more information.</span></span>

## <a name="package-manager-console-throws-an-exception-when-the-reflector-visual-studio-add-in-is-also-installed"></a><span data-ttu-id="993f5-147">Die Konsole des Paket-Managers löst eine Ausnahme aus, wenn das Visual Studio-Add-In „Reflector“ ebenfalls installiert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-147">Package Manager Console throws an exception when the Reflector Visual Studio Add-In is also installed.</span></span>

<span data-ttu-id="993f5-148">Wenn Sie die Konsole des Paket-Managers ausführen, wird Ihnen möglicherweise folgende Fehlermeldung angezeigt, wenn das Visual Studio-Add-In „Reflector“ installiert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-148">When running the Package Manager console, you may run into the following exception message if you have the Reflector VS Add-in installed.</span></span>

    The following error occurred while loading the extended type data file:
    Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(2950) :
    Error in type "System.Security.AccessControl.ObjectSecurity":
    Exception: Cannot convert the "Microsoft.PowerShell.Commands.SecurityDescriptorCommandsBase"
    value of type "System.String" to type "System.Type".
    System.Management.Automation.ActionPreferenceStopException:
    Command execution stopped because the preference variable "ErrorActionPreference" or common parameter
    is set to Stop: Unable to find type

<span data-ttu-id="993f5-149">oder</span><span class="sxs-lookup"><span data-stu-id="993f5-149">or</span></span>

    System.Management.Automation.CmdletInvocationException: Could not load file or assembly 'Scripts\nuget.psm1' or one of its dependencies. <br />The parameter is incorrect. (Exception from HRESULT: 0x80070057 (E_INVALIDARG)) ---&gt; System.IO.FileLoadException: Could not load file or <br />assembly 'Scripts\nuget.psm1' or one of its dependencies. The parameter is incorrect. (Exception from HRESULT: 0x80070057 (E_INVALIDARG)) <br />---&gt; System.ArgumentException: Illegal characters in path.
       at System.IO.Path.CheckInvalidPathChars(String path)
       at System.IO.Path.Combine(String path1, String path2)
       at Microsoft.VisualStudio.Platform.VsAppDomainManager.<AssemblyPaths>d__1.MoveNext()
       at Microsoft.VisualStudio.Platform.VsAppDomainManager.InnerResolveHandler(String name)
       at Microsoft.VisualStudio.Platform.VsAppDomainManager.ResolveHandler(Object sender, ResolveEventArgs args)
       at System.AppDomain.OnAssemblyResolveEvent(RuntimeAssembly assembly, String assemblyFullName)
       --- End of inner exception stack trace ---
       at Microsoft.PowerShell.Commands.ModuleCmdletBase.LoadBinaryModule(Boolean trySnapInName, String moduleName, String fileName, <br />Assembly assemblyToLoad, String moduleBase, SessionState ss, String prefix, Boolean loadTypes, Boolean loadFormats, Boolean&amp; found)
       at Microsoft.PowerShell.Commands.ModuleCmdletBase.LoadModuleNamedInManifest(String moduleName, String moduleBase, <br />Boolean searchModulePath, <br />String prefix, SessionState ss, Boolean loadTypesFiles, Boolean loadFormatFiles, Boolean&amp; found)
       at Microsoft.PowerShell.Commands.ModuleCmdletBase.LoadModuleManifest(ExternalScriptInfo scriptInfo, ManifestProcessingFlags <br />manifestProcessingFlags, Version version)
       at Microsoft.PowerShell.Commands.ModuleCmdletBase.LoadModule(String fileName, String moduleBase, String prefix, SessionState ss, <br />Boolean&amp; found)
       at Microsoft.PowerShell.Commands.ImportModuleCommand.ProcessRecord()
       at System.Management.Automation.Cmdlet.DoProcessRecord()
       at System.Management.Automation.CommandProcessor.ProcessRecord()
       --- End of inner exception stack trace ---
       at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
       at System.Management.Automation.Runspaces.Pipeline.Invoke()
       at NuGetConsole.Host.PowerShell.Implementation.PowerShellHost.Invoke(String command, Object input, Boolean outputResults)
       at NuGetConsole.Host.PowerShell.Implementation.PowerShellHostExtensions.ImportModule(PowerShellHost host, String modulePath)
       at NuGetConsole.Host.PowerShell.Implementation.PowerShellHost.LoadStartupScripts()
       at NuGetConsole.Host.PowerShell.Implementation.PowerShellHost.Initialize()
       at NuGetConsole.Implementation.Console.ConsoleDispatcher.Start()
       at NuGetConsole.Implementation.PowerConsoleToolWindow.MoveFocus(FrameworkElement consolePane)

<span data-ttu-id="993f5-150">Der Autor des Add-Ins wurde in der Hoffnung kontaktiert, dass dieser eine Lösung dafür ausarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="993f5-150">We've contacted the author of the add-in in the hopes of working out a resolution.</span></span>

<p class="info"><span data-ttu-id="993f5-151">Update: Es wurde festgestellt, dass die aktuelle Version von Reflector (6.5) diese Ausnahme nicht mehr in der Konsole auslöst.</span><span class="sxs-lookup"><span data-stu-id="993f5-151">Update: We have verified that the latest version of Reflector, 6.5, no longer causes this exception in the console.</span></span></p>

## <a name="opening-package-manager-console-fails-with-objectsecurity-exception"></a><span data-ttu-id="993f5-152">Das Öffnen der Konsole des Paket-Managers schlägt mit der Ausnahme „ObjectSecurity“ fehl</span><span class="sxs-lookup"><span data-stu-id="993f5-152">Opening Package Manager Console fails with ObjectSecurity exception</span></span>

<span data-ttu-id="993f5-153">Möglicherweise werden Ihnen diese Fehler angezeigt, wenn Sie die Konsole des Paket-Managers öffnen:</span><span class="sxs-lookup"><span data-stu-id="993f5-153">You might see these errors when trying to open the Package Manager Console:</span></span>

    The following error occurred while loading the extended type data file: Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(2977) : Error in type "System.Security.AccessControl.ObjectSecurity": Exception: The getter method should be public, non void, static, and have one parameter of type PSObject.
    The following error occurred while loading the extended type data file: Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(2984) : Error in type "System.Security.AccessControl.ObjectSecurity": Exception: The getter method should be public, non void, static, and have one parameter of type PSObject.
    The following error occurred while loading the extended type data file: Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(2991) : Error in type "System.Security.AccessControl.ObjectSecurity": Exception: The getter method should be public, non void, static, and have one parameter of type PSObject.
    The following error occurred while loading the extended type data file: Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(2998) : Error in type "System.Security.AccessControl.ObjectSecurity": Exception: The getter method should be public, non void, static, and have one parameter of type PSObject.
    The following error occurred while loading the extended type data file: Microsoft.PowerShell.Core, C:\Windows\SysWOW64\WindowsPowerShell\v1.0\types.ps1xml(3005) : Error in type "System.Security.AccessControl.ObjectSecurity": Exception: The getter method should be public, non void, static, and have one parameter of type PSObject.
    The term 'Get-ExecutionPolicy' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.

<span data-ttu-id="993f5-154">Wenn dies der Fall ist, befolgen Sie die auf [StackOverflow](http://stackoverflow.com/questions/12638289/embedding-powershell-v2-0-in-net-app-on-windows-8-rtm) erläuterte Lösung, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="993f5-154">If so, follow the solution [discussed on StackOverflow](http://stackoverflow.com/questions/12638289/embedding-powershell-v2-0-in-net-app-on-windows-8-rtm) to fix them.</span></span>

## <a name="the-add-package-library-reference-dialog-throws-an-exception-if-the-solution-contains-installshield-limited-edition-project"></a><span data-ttu-id="993f5-155">Das Dialogfeld „Add Package Library Reference“ (Bibliotheksverweis zum Paket hinzufügen) löst eine Ausnahme aus, wenn die Projektmappe ein InstallShield Limited Edition-Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="993f5-155">The Add Package Library Reference dialog throws an exception if the solution contains InstallShield Limited Edition Project</span></span>

<span data-ttu-id="993f5-156">Wenn Ihre Projektmappe mindestens ein InstallShield Limited Edition-Projekt enthält, löst das Dialogfeld **Add Package Library Reference** (Bibliotheksverweis zum Paket hinzufügen) beim Öffnen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="993f5-156">We have identified that if your solution contains one or more InstallShield Limited Edition project, the **Add Package Library Reference** dialog will throw an exception when opened.</span></span> <span data-ttu-id="993f5-157">Es gibt derzeit keine Problemumgehung außer dem Entfernen und Entladen der InstallShield-Projekte.</span><span class="sxs-lookup"><span data-stu-id="993f5-157">There is currently no workaround yet except either removing InstallShield projects or unloading them.</span></span>

## <a name="uninstall-button-greyed-out-nuget-requires-admin-privileges-to-installuninstall"></a><span data-ttu-id="993f5-158">Ist die Schaltfläche „Deinstallieren“ abgeblendet?</span><span class="sxs-lookup"><span data-stu-id="993f5-158">Uninstall Button Greyed out?</span></span> <span data-ttu-id="993f5-159">NuGet erfordert Administratorrechte für die Installation/Deinstallation</span><span class="sxs-lookup"><span data-stu-id="993f5-159">NuGet Requires Admin Privileges to Install/Uninstall</span></span>

<span data-ttu-id="993f5-160">Wenn Sie versuchen, NuGet über den Erweiterungs-Manager in Visual Studio zu deinstallieren, werden Sie feststellen, dass die Schaltfläche „Deinstallieren“ deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-160">If you try to uninstall NuGet via the Visual Studio Extension Manager, you may notice that the Uninstall button is disabled.</span></span> <span data-ttu-id="993f5-161">NuGet erfordert Administratorrechte für die Installation und Deinstallation.</span><span class="sxs-lookup"><span data-stu-id="993f5-161">NuGet requires admin access to install and uninstall.</span></span> <span data-ttu-id="993f5-162">Starten Sie Visual Studio als Administrator erneut, um die Erweiterung zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-162">Relaunch Visual Studio as an administrator to uninstall the extension.</span></span> <span data-ttu-id="993f5-163">Das Verwenden von NuGet erfordert keinen Administratorzugriff.</span><span class="sxs-lookup"><span data-stu-id="993f5-163">NuGet does not require admin access to use it.</span></span>

## <a name="the-package-manager-console-crashes-when-i-open-it-in-windows-xp-whats-wrong"></a><span data-ttu-id="993f5-164">Die Konsole des Paket-Managers stürzt ab, wenn sie in Windows XP geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="993f5-164">The Package Manager Console crashes when I open it in Windows XP.</span></span> <span data-ttu-id="993f5-165">Wo liegt der Fehler?</span><span class="sxs-lookup"><span data-stu-id="993f5-165">What's wrong?</span></span>

<span data-ttu-id="993f5-166">NuGet erfordert die Runtime von PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="993f5-166">NuGet requires Powershell 2.0 runtime.</span></span> <span data-ttu-id="993f5-167">Windows XP verfügt standardmäßig nicht über PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="993f5-167">Windows XP, by default, doesn't have Powershell 2.0.</span></span> <span data-ttu-id="993f5-168">Sie können die Runtime von PowerShell 2.0 unter [http://support.microsoft.com/kb/968929](http://support.microsoft.com/kb/968929) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="993f5-168">You can download the Powershell 2.0 runtime from [http://support.microsoft.com/kb/968929](http://support.microsoft.com/kb/968929).</span></span> <span data-ttu-id="993f5-169">Starten Sie Visual Studio nach der Installation neu. Es sollte dann möglich sein, die Konsole des Paket-Managers zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="993f5-169">After you install it, restart Visual Studio and you should be able to open Package Manager Console.</span></span>

## <a name="visual-studio-2010-sp1-beta-crashes-on-exit-if-the-package-manager-console-is-open"></a><span data-ttu-id="993f5-170">Die Betaversion von Visual Studio 2010 SP1 stürzt beim Beenden ab, wenn die Konsole des Paket-Managers geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-170">Visual Studio 2010 SP1 Beta crashes on exit if the Package Manager Console is open.</span></span>

<span data-ttu-id="993f5-171">Wenn Sie die Betaversion von Visual Studio 2010 SP1 installiert haben, werden Sie möglicherweise feststellen, dass Visual Studio abstürzt, wenn Sie die Konsole des Paket-Managers geöffnet lassen und das Programm beenden.</span><span class="sxs-lookup"><span data-stu-id="993f5-171">If you have installed Visual Studio 2010 SP1 Beta, you may notice that if you leave the Package Manager Console open and close Visual Studio, it will crash.</span></span> <span data-ttu-id="993f5-172">Dabei handelt es sich um ein bekanntes Problem von Visual Studio, das im Release SP1 RTM behoben wird.</span><span class="sxs-lookup"><span data-stu-id="993f5-172">This is a known issue of Visual Studio and will be fixed in SP1 RTM release.</span></span> <span data-ttu-id="993f5-173">Ignorieren Sie den Absturz vorerst, oder deinstallieren Sie wenn möglich die Betaversion von SP1.</span><span class="sxs-lookup"><span data-stu-id="993f5-173">For now, just ignore the crash or uninstall SP1 Beta if you can.</span></span>

## <a name="the-element-metadata--has-invalid-child-element-exception-occurs"></a><span data-ttu-id="993f5-174">Die Ausnahme „Das Element ‚metadata‘ hat ein ungültiges untergeordnetes Element“ tritt auf</span><span class="sxs-lookup"><span data-stu-id="993f5-174">The element 'metadata' ... has invalid child element exception occurs</span></span>

<span data-ttu-id="993f5-175">Wenn Sie Pakete installiert haben, die mit einer Vorabversion von NuGet erstellt wurden, wird Ihnen möglicherweise die Fehlermeldung „Das Element ‚metadata‘ im Namespace ‚schemas.microsoft.com/packaging/2010/07/nuspec.xsd‘ hat ein ungültiges untergeordnetes Element“ angezeigt, wenn Sie die RTM-Version von NuGet mit diesem Projekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="993f5-175">If you installed packages built with a pre-release version of NuGet, you might encounter an error message stating "The element 'metadata' in namespace 'schemas.microsoft.com/packaging/2010/07/nuspec.xsd' has invalid child element" when running the RTM version of NuGet with that project.</span></span> <span data-ttu-id="993f5-176">Sie müssen jedes Paket, das die RTM-Version von NuGet verwendet, deinstallieren und erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-176">You need to uninstall and then re-install each package using the RTM version of NuGet.</span></span>

## <a name="attempting-to-install-or-uninstall-results-in-the-error-cannot-create-a-file-when-that-file-already-exists"></a><span data-ttu-id="993f5-177">Beim Versuch einer Installation oder Deinstallation wird die Fehlermeldung „Eine Datei kann nicht erstellt werden, wenn sie bereits vorhanden ist.“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="993f5-177">Attempting to install or uninstall results in the error "Cannot create a file when that file already exists."</span></span>

<span data-ttu-id="993f5-178">Aus unbekannten Gründen können Visual Studio-Erweiterungen einen merkwürdigen Status aufweisen, bei dem die Erweiterung für VSIX zwar deinstalliert wurde, aber einige Dateien verbleiben.</span><span class="sxs-lookup"><span data-stu-id="993f5-178">For some reason, Visual Studio extensions can get in a weird state where you've uninstalled the VSIX extension, but some files were left behind.</span></span> <span data-ttu-id="993f5-179">So umgehen Sie dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="993f5-179">To work around this issue:</span></span>

1. <span data-ttu-id="993f5-180">Visual Studio beenden</span><span class="sxs-lookup"><span data-stu-id="993f5-180">Exit Visual Studio</span></span>
1. <span data-ttu-id="993f5-181">Öffnen Sie folgenden Ordner (dieser könnte sich auf Ihrem Computer auf einem anderen Laufwerk befinden):</span><span class="sxs-lookup"><span data-stu-id="993f5-181">Open the following folder (it might be on a different drive on your machine)</span></span>

    <span data-ttu-id="993f5-182">C:\Programme (x86)\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft Corporation\NuGet Package Manager\<Version>\\</span><span class="sxs-lookup"><span data-stu-id="993f5-182">C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft Corporation\NuGet Package Manager\<version>\\</span></span>

1. <span data-ttu-id="993f5-183">Löschen Sie alle Dateien mit der Erweiterung *DELETEME*.</span><span class="sxs-lookup"><span data-stu-id="993f5-183">Delete all the files with the *.deleteme* extensions.</span></span>
1. <span data-ttu-id="993f5-184">Öffnen Sie Visual Studio erneut.</span><span class="sxs-lookup"><span data-stu-id="993f5-184">Re-open Visual Studio</span></span>

<span data-ttu-id="993f5-185">Nachdem Sie diese Schritte befolgt haben, sollten Sie den Vorgang fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="993f5-185">After following these steps, you should be able to continue.</span></span>

## <a name="in-rare-cases-compiling-with-code-analysis-turned-on-causes-error"></a><span data-ttu-id="993f5-186">In seltenen Fällen verursacht das Kompilieren mit aktivierter Codeanalyse Fehler.</span><span class="sxs-lookup"><span data-stu-id="993f5-186">In rare cases, compiling with Code Analysis turned on causes error.</span></span>

<span data-ttu-id="993f5-187">Ihnen wird möglicherweise folgende Fehlermeldung angezeigt, wenn Sie „FluentNHibernate“ über die Konsole des Paket-Managers installieren und Ihr Projekt anschließend mit aktivierter Codeanalyse kompilieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-187">You might get the following error if you installs FluentNHibernate with the Package Manager console and then compile your project with "Code Analysis" turned on.</span></span>

    Error 3 CA0058 : The referenced assembly
    'NHibernate, Version=3.0.0.2001, Culture=neutral, PublicKeyToken=aa95f207798dfdb4'
    could not be found. This assembly is required for analysis and was referenced by:
    C:\temp\Scratch\src\MyProject.UnitTests\bin\Debug\MyProject.UnitTests.dll.
    MyProject.UnitTests

<span data-ttu-id="993f5-188">Standardmäßig erfordert FluentNHibernate NHibernate 3.0.0.2001.</span><span class="sxs-lookup"><span data-stu-id="993f5-188">By default, FluentNHibernate requires NHibernate 3.0.0.2001.</span></span> <span data-ttu-id="993f5-189">Entwurfsbedingt installiert NuGet jedoch NHibernate 3.0.0.4000 in Ihrem Projekt und fügt die entsprechenden Bindungsumleitungen hinzu, sodass das Paket funktioniert.</span><span class="sxs-lookup"><span data-stu-id="993f5-189">However, by design NuGet will install NHibernate 3.0.0.4000 in your project and add the appropriate binding redirects so that it will work.</span></span> <span data-ttu-id="993f5-190">Ihr Projekt wird problemlos kompiliert, wenn die Codeanalyse deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-190">You project will compile just fine if code analysis is not turned on.</span></span> <span data-ttu-id="993f5-191">Im Gegensatz zum Compiler folgt das Codeanalysetool den Bindungsumleitungen, um 3.0.0.4000 statt 3.0.0.2001 zu verwenden, nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="993f5-191">In contrast to the compiler, code analysis tool doesn't properly follow the binding redirects to use 3.0.0.4000 instead of 3.0.0.2001.</span></span> <span data-ttu-id="993f5-192">Sie können dieses Problem umgehen, indem Sie entweder NHibernate 3.0.0.2001 installieren oder das Codeanalysetool folgendermaßen dafür konfigurieren, sich genau wie der Compiler zu verhalten:</span><span class="sxs-lookup"><span data-stu-id="993f5-192">You can work around the issue by either installing NHibernate 3.0.0.2001 or tell the code analysis tool to behave the same as the compiler by doing the following:</span></span>

1. <span data-ttu-id="993f5-193">Wechseln Sie zu *%PROGRAMFILES%\Microsoft Visual Studio 10.0\Team Tools\Static Analysis Tools\FxCop*.</span><span class="sxs-lookup"><span data-stu-id="993f5-193">Go to *%PROGRAMFILES%\Microsoft Visual Studio 10.0\Team Tools\Static Analysis Tools\FxCop*</span></span>
1. <span data-ttu-id="993f5-194">Öffnen Sie „FxCopCmd.exe.config“, und ändern Sie `AssemblyReferenceResolveMode` von `StrongName` in `StrongNameIgnoringVersion`.</span><span class="sxs-lookup"><span data-stu-id="993f5-194">Open FxCopCmd.exe.config and change `AssemblyReferenceResolveMode` from `StrongName` to `StrongNameIgnoringVersion`.</span></span>
1. <span data-ttu-id="993f5-195">Speichern Sie die Änderung, und erstellen Sie das Projekt erneut.</span><span class="sxs-lookup"><span data-stu-id="993f5-195">Save the change and rebuild your project.</span></span>

## <a name="write-error-command-doesnt-work-inside-installps1uninstallps1initps1"></a><span data-ttu-id="993f5-196">Der Befehl „Write-Error“ funktioniert innerhalb von „install.ps1/uninstall.ps1/init.ps1“ nicht</span><span class="sxs-lookup"><span data-stu-id="993f5-196">Write-Error command doesn't work inside install.ps1/uninstall.ps1/init.ps1</span></span>

<span data-ttu-id="993f5-197">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="993f5-197">This is a known issue.</span></span> <span data-ttu-id="993f5-198">Versuchen Sie, „throw“ statt „Write-Error“ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="993f5-198">Instead of calling Write-Error, try calling throw.</span></span>

    throw "My error message"

## <a name="installing-nuget-with-restricted-access-on-windows-2003-can-crash-visual-studio"></a><span data-ttu-id="993f5-199">Das Installieren von NuGet mit eingeschränktem Zugriff unter Windows 2003 kann zu einem Absturz von Visual Studio führen</span><span class="sxs-lookup"><span data-stu-id="993f5-199">Installing NuGet with restricted access on Windows 2003 can crash Visual Studio</span></span>

<span data-ttu-id="993f5-200">Wenn Sie versuchen, NuGet mithilfe des Erweiterungs-Managers von Visual Studio zu installieren und das Programm nicht als Administrator ausführen, wird das Dialogfeld „Ausführen als“ mit dem Kontrollkästchen „Programm mit eingeschränktem Zugriff ausführen“ angezeigt, das standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="993f5-200">When attempting to install NuGet using the Visual Studio Extension Manager and not running as an administrator, the &#8220;Run As&#8221; dialog is displayed with the checkbox labeled &#8220;Run this program with restricted access&#8221; checked by default.</span></span>

![Dialogfeld „Programm mit eingeschränktem Zugriff ausführen“](./media/RunAsRestricted.png)

<span data-ttu-id="993f5-202">Wenn dieses Kontrollkästchen aktiviert ist, und Sie auf OK klicken, stürzt Visual Studio ab.</span><span class="sxs-lookup"><span data-stu-id="993f5-202">Clicking OK with that checked crashes Visual Studio.</span></span> <span data-ttu-id="993f5-203">Stellen Sie sicher, dass Sie diese Option nicht deaktivieren, bevor Sie NuGet installieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-203">Make sure to uncheck that option before installing NuGet.</span></span>

## <a name="cannot-uninstall-nuget-for-windows-phone-tools"></a><span data-ttu-id="993f5-204">NuGet-Tools für Windows Phone können nicht deinstalliert werden</span><span class="sxs-lookup"><span data-stu-id="993f5-204">Cannot uninstall NuGet for Windows Phone Tools</span></span>

<span data-ttu-id="993f5-205">Windows Phone-Tools unterstützen den Erweiterungs-Manager für Visual Studio nicht.</span><span class="sxs-lookup"><span data-stu-id="993f5-205">Windows Phone Tools does not have support for the Visual Studio Extension Manager.</span></span> <span data-ttu-id="993f5-206">Führen Sie folgenden Befehl aus, um NuGet zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="993f5-206">In order to uninstall NuGet, run the following command.</span></span>

     vsixinstaller.exe /uninstall:NuPackToolsVsix.Microsoft.67e54e40-0ae3-42c5-a949-fddf5739e7a5

## <a name="changing-the-capitalization-of-nuget-package-ids-breaks-package-restore"></a><span data-ttu-id="993f5-207">Das Ändern der Groß-/Kleinschreibung von NuGet-Paket-IDs unterbricht die Paketwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="993f5-207">Changing the capitalization of NuGet package IDs breaks package restore</span></span>

<span data-ttu-id="993f5-208">Wie in diesem [GitHub-Problem](https://github.com/Particular/NServiceBus/issues/1271#issuecomment-20865932) ausführlich erläutert wird, kann eine Änderung der Groß-/Kleinschreibung von NuGet-Paketen vom NuGet-Support durchgeführt werden. Dies führt jedoch zu Komplikationen während der Paketwiederherstellung für Benutzer mit vorhandenen Paketen mit unterschiedlicher Groß-/Kleinschreibung im lokalen Paketcache.</span><span class="sxs-lookup"><span data-stu-id="993f5-208">As discussed at length on [this GitHub issue](https://github.com/Particular/NServiceBus/issues/1271#issuecomment-20865932), changing the capitalization of NuGet packages can be done by NuGet support, but causes complications during package restore for users who have existing, differently-cased, packages in their local package cache.</span></span> <span data-ttu-id="993f5-209">Es wird empfohlen, nur eine Änderung der Groß-/Kleinschreibung anzufordern, wenn Sie mit den Benutzern Ihrer Pakete kommunizieren können, um diese über die Unterbrechung zu informieren, die bei der Paketwiederherstellung zur Buildzeit auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="993f5-209">We recommend only requesting a case change when you have a way to communicate with existing users of your package about the break that may occur to their build-time package restore.</span></span>

## <a name="reporting-issues"></a><span data-ttu-id="993f5-210">Melden von Problemen</span><span class="sxs-lookup"><span data-stu-id="993f5-210">Reporting issues</span></span>

<span data-ttu-id="993f5-211">Melden Sie Probleme mit NuGet unter [https://github.com/nuget/home/issues](https://github.com/nuget/home/issues).</span><span class="sxs-lookup"><span data-stu-id="993f5-211">To report NuGet issues, visit [https://github.com/nuget/home/issues](https://github.com/nuget/home/issues).</span></span>