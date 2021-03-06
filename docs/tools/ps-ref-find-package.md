---
title: NuGet-Find-Package-PowerShell-Referenz
description: Referenz für Find-Package-PowerShell-Befehl in der NuGet-Paket-Manager-Konsole in Visual Studio.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 6/1/2017
ms.topic: reference
ms.openlocfilehash: ebecb3818c063d11a2d613a85e2b7baef649dee6
ms.sourcegitcommit: 2a6d200012cdb4cbf5ab1264f12fecf9ae12d769
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34816918"
---
# <a name="find-package-package-manager-console-in-visual-studio"></a>Find-Package (Paket-Manager-Konsole in Visual Studio)

*Version 3.0 +; In diesem Thema wird beschrieben, den Befehl innerhalb der [NuGet Package Manager Console](package-manager-console.md) in Visual Studio unter Windows. Der generische PowerShell Find-Package-Befehl finden Sie unter der [PowerShell PackageManagement-Verweis](/powershell/module/packagemanagement/?view=powershell-6).*

Ruft die Sammlung der remotepakete mit der angegebenen ID oder Schlüsselwörter aus der Paketquelle ab.

## <a name="syntax"></a>Syntax

```ps
Find-Package [-Id] <keywords> -Source <string> [-AllVersions] [-First [<int>]]
    [-Skip <int>] [-IncludePrerelease] [-ExactMatch] [-StartWith] [<CommonParameters>]
```

## <a name="parameters"></a>Parameter

| Parameter | Beschreibung |
| --- | --- |
| ID &lt;Schlüsselwörter&gt; | (Erforderlich) Schlüsselwörter verwenden, wenn die Paketquelle zu suchen. Verwenden Sie-"exactMatch", um nur die Pakete zurück, dessen Paket-ID der Schlüsselwörter übereinstimmt. Wenn keine Schlüsselwörter angegeben sind, `Find-Package` -Rückgaben eine Liste der Top-20-Pakete von Downloads oder die Anzahl von - zuerst. Beachten Sie, dass - Id optional ist und nicht ausgeführt. |
| Quelle | Die URL oder einen Ordnerpfad für die Paketquelle, gesucht werden soll. Lokale Ordnerpfaden kann absolut oder relativ zum aktuellen Ordner. Wenn nicht angegeben, `Find-Package` die aktuell ausgewählten Paketquelle durchsucht. |
| AllVersions | Zeigt alle verfügbaren Versionen der einzelnen Pakete, anstatt nur die neueste Version. |
| First | Die Anzahl der Pakete an, ab dem Anfang der Liste zurückgegeben werden soll; Der Standardwert ist 20. |
| Skip | Lässt die erste &lt;Int&gt; Pakete aus der angezeigten Liste.  |
| IncludePrerelease | Enthält Vorabversionen von Paketen in den Ergebnissen an. |
| "ExactMatch" | Mit angegebenen &lt;Schlüsselwörter&gt; als Groß-/Kleinschreibung Paket-ID |
| StartWith | Gibt Pakete, deren ID beginnt mit Paket &lt;Schlüsselwörter&gt;. |

Keines dieser Parameter akzeptieren Pipeline Eingabe- oder Platzhalter-Zeichen.

## <a name="common-parameters"></a>Allgemeine Parameter

`Find-Package` unterstützt die folgenden [allgemeine PowerShell-Parameter](http://go.microsoft.com/fwlink/?LinkID=113216): Debug, Fehleraktion, ErrorVariable, -OutBuffer, OutVariable, mit "pipelinevariable", ausführlich, WarningAction und WarningVariable.

## <a name="examples"></a>Beispiele

```ps
# Find packages containing keywords
Find-Package elmah
Find-Package logging

# List packages whose ID begins with Elmah
Find-Package Elmah -StartWith

# By default, Get-Package returns a list of 20 packages; use -First to show more
Find-Package logging -First 100

# List all versions of the package with the ID of "jquery"
Find-Package jquery -AllVersions -ExactMatch
```
