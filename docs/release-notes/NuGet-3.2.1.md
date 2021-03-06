---
title: Anmerkungen zur Version von NuGet 3.2.1
description: Versionshinweise für NuGet 3.2.1 einschließlich bekannte Probleme, Fehlerbehebungen, Funktionen und Archivierung von dcrs Design.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 11/11/2016
ms.topic: conceptual
ms.openlocfilehash: 039fabaaacfdffd76fa88ff8183548e97cd4719b
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31820143"
---
# <a name="nuget-321-release-notes"></a>Anmerkungen zur Version von NuGet 3.2.1

[Anmerkungen zur Version des NuGet-3.2](../release-notes/nuget-3.2.md) | [NuGet 3.3-Versionshinweise](../release-notes/nuget-3.3.md)

NuGet 3.2.1 für die Befehlszeile am 12. Oktober 2015 veröffentlicht wurde, eine Handvoll Optimierungen und Fehlerbehebungen für die Version 3.2 und steht über [dist.nuget.org](http://dist.nuget.org/index.html).

## <a name="improvements"></a>Verbesserungen

* NuGet verwendet nun die Konfigurationsdatei mit dem ursprünglichen Groß-/Kleinschreibung von `NuGet.Config`.  Dies ist wichtig, auf die Groß-/Kleinschreibung Betriebssysteme [1427](https://github.com/NuGet/Home/issues/1427)
* Wiederherstellen von NuGet ignoriert nun Dnx-Projekten (`*.xproj`), die verarbeitet werden soll, mit `dnu` [1227](https://github.com/NuGet/Home/issues/1227)
* Netzwerkauslastung optimiert, bei der Arbeit mit `index.json` und Packen Sie die Registrierungsdaten [1426](https://github.com/NuGet/Home/issues/1426)
* Verbesserte Ressource Download behandeln, damit eine robustere mit v2-Diensten werden [1448](https://github.com/NuGet/Home/issues/1448)

## <a name="fixes"></a>Fehlerbehebungen

* NuGet-Update ordnungsgemäß aktualisiert `.csproj` / `.vcxproj` Verweise [1483](https://github.com/NuGet/Home/issues/1483)
* Jetzt verhindert, dass ein Ordner "Lokaler .nuget" erstellt werden, wenn eine SpecialFolders.UserProfile kann nicht gefunden werden [1531](https://github.com/NuGet/Home/issues/1531)
* Verbesserte Behandlung von Paketen im lokalen Cache, die während des Herunterladens beschädigt sind [1405](https://github.com/NuGet/Home/issues/1405) [1157](https://github.com/NuGet/Home/issues/1157)

Eine vollständige Liste der Probleme für die Befehlszeile und Visual Studio-Erweiterung Sie in der NuGet-GitHub finden [3.2.1 Meilenstein](https://github.com/NuGet/Home/issues?q=milestone%3A3.2.1+is%3Aclosed)

## <a name="known-issues"></a>Bekannte Probleme

Wir weiterhin Probleme auf unserer GitHub-Problemliste zu verfolgen, die sich am befinden: [http://github.com/nuget/home/issues](http://github.com/nuget/home/issues)