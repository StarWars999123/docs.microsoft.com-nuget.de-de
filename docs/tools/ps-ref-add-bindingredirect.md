---
title: Hinzufügen von NuGet-BindingRedirect-PowerShell-Referenz
description: Referenz für die Add-BindingRedirect-PowerShell-Befehl in der NuGet-Paket-Manager-Konsole in Visual Studio.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 12/07/2017
ms.topic: reference
ms.openlocfilehash: f3addd95b64d78eac201deeb2c64915ea935cd71
ms.sourcegitcommit: 2a6d200012cdb4cbf5ab1264f12fecf9ae12d769
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34817622"
---
# <a name="add-bindingredirect-package-manager-console-in-visual-studio"></a>Add-BindingRedirect (Paket-Manager-Konsole in Visual Studio)

*Verfügbar nur innerhalb der [NuGet Package Manager Console](package-manager-console.md) in Visual Studio unter Windows.*

Untersucht alle Assemblys im Ausgabepfad auf ein Projekt, und der Anwendungs- oder Webkonfigurationsdatei Konfigurationsdatei umleitungen für Bindungen hinzugefügt, bei Bedarf. Mit diesem Befehl wird automatisch ausgeführt, wenn Sie ein Paket zu installieren.

Ausführliche Informationen zu binden, leitet und warum sie verwendet werden, finden Sie unter [Umleiten von Assemblyversionen](/dotnet/framework/configure-apps/redirect-assembly-versions) in der Dokumentation zu .NET.

## <a name="syntax"></a>Syntax

```ps
Add-BindingRedirect [-ProjectName] <string> [<CommonParameters>]
```

## <a name="parameters"></a>Parameter

| Parameter | Beschreibung |
| --- | --- |
| ProjektName | (Erforderlich) Das Projekt, dem umleitungen für Bindungen hinzugefügt. Der Projektname - Schalter ist optional. |

Keines dieser Parameter akzeptieren Pipeline Eingabe- oder Platzhalter-Zeichen.

## <a name="common-parameters"></a>Allgemeine Parameter

`Add-BindingRedirect` unterstützt die folgenden [allgemeine PowerShell-Parameter](http://go.microsoft.com/fwlink/?LinkID=113216): Debug, Fehleraktion, ErrorVariable, -OutBuffer, OutVariable, mit "pipelinevariable", ausführlich, WarningAction und WarningVariable.

## <a name="examples"></a>Beispiele

```ps
Add-BindingRedirect MyProject

Add-BindingRedirect -ProjectName MyProject
```