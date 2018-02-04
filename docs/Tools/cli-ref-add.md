---
title: "NuGet CLI hinzufügen (Befehl) | Microsoft Docs"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 01/18/2018
ms.topic: reference
ms.prod: nuget
ms.technology: 
description: "Referenz für die nuget.exe Befehl hinzufügen."
keywords: "NuGet Verweis hinzufügen, fügen Sie Paket-Befehl"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 70c86f8d240bd308224f6b7887b630cc1e953bf8
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="add-command-nuget-cli"></a>Fügen Sie hinzu (Befehl) (NuGet CLI)

**Gilt für**: Verpacken Sie die Publishing &bullet; **unterstützten Versionen**: 3.3 +

Fügt ein angegebenes Paket auf einem nicht-HTTP-Paketquelle (ein Ordner oder eine UNC-Pfad) in hierarchischer Anordnung dargestellt, bei dem Ordner, für die Paket-ID und die Version erstellt werden an. Zum Beispiel:

    \\myserver\packages
      └─<packageID>
        └─<version>
          ├─<packageID>.<version>.nupkg
          ├─<packageID>.<version>.nupkg.sha512
          └─<packageID>.nuspec

Beim Wiederherstellen, oder für die Paketquelle aktualisieren, stellt hierarchischer Anordnung dargestellt deutlichen Leistungssteigerung führen.

Um alle Dateien im Paket für die Paketquelle Ziel zu erweitern, verwenden die `-Expand` wechseln. Dies führt in der Regel zusätzliche Unterordner, der in das Ziel, z. B. `tools` und `lib`.

## <a name="usage"></a>Verwendung

```cli
nuget add <packagePath> -Source <sourcePath> [options]
```

wobei `<packagePath>` der Pfadname für das Paket zum Hinzufügen, und `<sourcePath>` gibt an, die Ordner-basierte Paketquelle an, der das Paket hinzugefügt werden. HTTP-Datenquellen werden nicht unterstützt.

## <a name="options"></a>Optionen

| Option | Beschreibung |
| --- | --- |
| ConfigFile | Die NuGet-Konfigurationsdatei angewendet werden soll. Wenn nicht angegeben, *%AppData%\NuGet\NuGet.Config* verwendet wird.| 
| Expand | Fügt alle Dateien im Paket für die Paketquelle. |
| ForceEnglishOutput | *(3.5 +)*  Erzwingt nuget.exe über eine invariante Kultur Englisch-basierte ausgeführt werden. |
| Hilfe | Zeigt die Hilfe Informationen für den Befehl. |
| NonInteractive | Unterdrückt aufforderungen für Benutzereingaben oder Bestätigungen an. |
| Ausführlichkeit | Gibt die Anzahl der Details in der Ausgabe angezeigt: *normalen*, *stillen*, *ausführliche*. |

Siehe auch [Umgebungsvariablen](cli-ref-environment-variables.md)

## <a name="examples"></a>Beispiele

```cli
nuget add foo.nupkg -Source c:\bar\

nuget add foo.nupkg -Source \\bar\packages\
```