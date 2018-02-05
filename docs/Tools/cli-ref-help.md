---
title: NuGet-CLI-Befehl "Hilfe" | Microsoft Docs
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 01/18/2018
ms.topic: reference
ms.prod: nuget
ms.technology: 
description: "Referenz für den Befehl \"nuget.exe Help\""
keywords: Referenz zur Hilfe von NuGet, Befehl "Hilfe"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 97f72e1be0df6e97f8b06696b2b3861800e4ea08
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="help-or--command-nuget-cli"></a><span data-ttu-id="5f25b-104">Hilfe oder?</span><span class="sxs-lookup"><span data-stu-id="5f25b-104">help or ?</span></span> <span data-ttu-id="5f25b-105">Befehl (NuGet CLI)</span><span class="sxs-lookup"><span data-stu-id="5f25b-105">command (NuGet CLI)</span></span>

<span data-ttu-id="5f25b-106">**Gilt für:** alle &bullet; **unterstützten Versionen**: alle</span><span class="sxs-lookup"><span data-stu-id="5f25b-106">**Applies to:** all &bullet; **Supported versions**: all</span></span>

<span data-ttu-id="5f25b-107">Zeigt allgemeine Hilfe-Informationen und Hilfe-Informationen zu bestimmten Befehlen.</span><span class="sxs-lookup"><span data-stu-id="5f25b-107">Displays general help information and help information about specific commands.</span></span>

## <a name="usage"></a><span data-ttu-id="5f25b-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="5f25b-108">Usage</span></span>

```cli
nuget help [command] [options]
nuget ? [command] [options]
```

<span data-ttu-id="5f25b-109">[Befehl] identifiziert, in einen bestimmten Befehl für die Hilfe angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5f25b-109">where [command] identifies a specific command for which to display help.</span></span>

> [!Warning]
> <span data-ttu-id="5f25b-110">Einige Befehle werden an laufen *Hilfe* ersten, als mit `nuget help install`, da ein Paket mit dem Namen "help" auf nuget.org vorhanden ist. Wenn Sie den Befehl geben `nuget install help`, erhalten Sie keine Hilfe zum Befehl "Install", aber das Paket mit dem Namen Hilfe wird stattdessen installieren.</span><span class="sxs-lookup"><span data-stu-id="5f25b-110">With some commands, be mindful to specify *help* first, as with `nuget help install`, because there is a package named "help" on nuget.org. If you give the command `nuget install help`, you'll not get help on the install command but will instead install the package named help.</span></span>

## <a name="options"></a><span data-ttu-id="5f25b-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="5f25b-111">Options</span></span>

| <span data-ttu-id="5f25b-112">Option</span><span class="sxs-lookup"><span data-stu-id="5f25b-112">Option</span></span> | <span data-ttu-id="5f25b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f25b-113">Description</span></span> |
| --- | --- |
| <span data-ttu-id="5f25b-114">Alle</span><span class="sxs-lookup"><span data-stu-id="5f25b-114">All</span></span> | <span data-ttu-id="5f25b-115">Drucken von ausführlichen Hilfeinformationen für alle verfügbaren Befehle; ignoriert, wenn Sie ein bestimmten Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f25b-115">Print detailed help for all available commands; ignored if a specific command is given.</span></span> |
| <span data-ttu-id="5f25b-116">ConfigFile</span><span class="sxs-lookup"><span data-stu-id="5f25b-116">ConfigFile</span></span> | <span data-ttu-id="5f25b-117">Die NuGet-Konfigurationsdatei angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f25b-117">The NuGet configuration file to apply.</span></span> <span data-ttu-id="5f25b-118">Wenn nicht angegeben, *%AppData%\NuGet\NuGet.Config* verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f25b-118">If not specified, *%AppData%\NuGet\NuGet.Config* is used.</span></span> |
| <span data-ttu-id="5f25b-119">ForceEnglishOutput</span><span class="sxs-lookup"><span data-stu-id="5f25b-119">ForceEnglishOutput</span></span> | <span data-ttu-id="5f25b-120">*(3.5 +)*  Erzwingt nuget.exe über eine invariante Kultur Englisch-basierte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5f25b-120">*(3.5+)* Forces nuget.exe to run using an invariant, English-based culture.</span></span> |
| <span data-ttu-id="5f25b-121">Hilfe</span><span class="sxs-lookup"><span data-stu-id="5f25b-121">Help</span></span> | <span data-ttu-id="5f25b-122">Zeigt die Hilfe Informationen für den Befehl "Help" selbst.</span><span class="sxs-lookup"><span data-stu-id="5f25b-122">Displays help information for the help command itself.</span></span> |
| <span data-ttu-id="5f25b-123">Markdown</span><span class="sxs-lookup"><span data-stu-id="5f25b-123">Markdown</span></span> | <span data-ttu-id="5f25b-124">Drucken von ausführlichen Hilfeinformationen in Markdown-Format bei Verwendung mit `-All`.</span><span class="sxs-lookup"><span data-stu-id="5f25b-124">Print detailed help in markdown format when used with `-All`.</span></span> <span data-ttu-id="5f25b-125">Andernfalls ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5f25b-125">Ignored otherwise.</span></span> |
| <span data-ttu-id="5f25b-126">NonInteractive</span><span class="sxs-lookup"><span data-stu-id="5f25b-126">NonInteractive</span></span> | <span data-ttu-id="5f25b-127">Unterdrückt aufforderungen für Benutzereingaben oder Bestätigungen an.</span><span class="sxs-lookup"><span data-stu-id="5f25b-127">Suppresses prompts for user input or confirmations.</span></span> |
| <span data-ttu-id="5f25b-128">Ausführlichkeit</span><span class="sxs-lookup"><span data-stu-id="5f25b-128">Verbosity</span></span> | <span data-ttu-id="5f25b-129">Gibt die Anzahl der Details in der Ausgabe angezeigt: *normalen*, *stillen*, *ausführliche*.</span><span class="sxs-lookup"><span data-stu-id="5f25b-129">Specifies the amount of detail displayed in the output: *normal*, *quiet*, *detailed*.</span></span> |

<span data-ttu-id="5f25b-130">Siehe auch [Umgebungsvariablen](cli-ref-environment-variables.md)</span><span class="sxs-lookup"><span data-stu-id="5f25b-130">Also see [Environment variables](cli-ref-environment-variables.md)</span></span>

## <a name="examples"></a><span data-ttu-id="5f25b-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5f25b-131">Examples</span></span>

```cli
nuget help
nuget help push
nuget ?
nuget push -?
nuget help -All -Markdown
```