---
title: 3.3 NuGet-Versionshinweise
description: Versionshinweise für NuGet 3.3 einschließlich bekannte Probleme, Fehlerbehebungen, Funktionen und Archivierung von dcrs Design.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 11/11/2016
ms.topic: conceptual
ms.openlocfilehash: adf193437de237ed32da481e627552a8dba6f656
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31821563"
---
# <a name="nuget-33-release-notes"></a>3.3 NuGet-Versionshinweise

[Anmerkungen zur Version des NuGet-3.2.1](../release-notes/nuget-3.2.1.md) | [NuGet 3.4-RC-Versionsanmerkungen](../release-notes/nuget-3.4-RC.md)

NuGet-3.3 wurde am 30. November 2015 mit einer erheblichen Anzahl von benutzerschnittstellenupdates und Befehlszeilen-Funktionen sowie eine Auflistung von nützlich Korrekturen für den NuGet-Clients freigegeben.

## <a name="new-features"></a>Neue Funktionen

* Anmeldeinformationsanbieter wurden eingeführt, die NuGet-Befehlszeilen-Clients in der Lage, um die nahtlose Zusammenarbeit mit einem authentifizierten Feed sein können. [Anweisungen zum Installieren der Visual Studio Team Services-Anmeldeinformationen Anbieter ](../api/nuget-exe-credential-providers.md) und konfigurieren Sie die NuGet Clients zur Verwendung finden Sie auf der NuGet Docs.

## <a name="new-user-interface-features"></a>Neue Features der Benutzeroberfläche

* Registerkarten für separate durchsuchen, installiert und Updates verfügbar
* Verfügbare Badge, der angibt, der Anzahl der Pakete mit verfügbaren Updates aktualisiert
* Paket Signale in der Liste der Pakete an, wenn das Paket installiert ist, oder ein Update verfügbar ist
* Herunterladen Sie Anzahl und der Autor hinzugefügt wird, um die Liste der Pakete
* Höchste verfügbare Versionsnummer und der derzeit installierten Version Zahl auf die Paketliste
* Aktionsschaltflächen schnelle Installation zu aktualisieren und Deinstallieren von aus der Liste der Pakete
* Klarer Aktionsschaltflächen im Paket-Detail-Bereich
* Paket Aktualisierungsdatum im Paket-Detail-Bereich
* Konsolidieren Sie Bereich im Projektmappen-Ansicht
* Sortierbares Raster von Projekten und installierten Versionsnummern für die Lösung-Sicht

## <a name="new-command-line-features"></a>Neue Befehlszeilen-Funktionen

In dieser Version eingeführten wir die `add` und `init` Befehle aus, um die Ordner-basierte Repositorys zu initialisieren, wie beschrieben in der [nuget.exe Verweis](../tools/nuget-exe-cli-reference.md). Repositorys, die erstellt und verwaltet, die mit diesem Ordner-Struktur wird [bieten Sie beachtliche Leistungsvorteile](http://blog.nuget.org/20150922/Accelerate-Package-Source.html) wie beschrieben in unserem Blog.

## <a name="contentfiles"></a>ContentFiles

Inhalt wird jetzt unterstützt `project.json` verwaltete Projekte über die neue `contentFiles` Ordner und `.nuspec` `contentFiles` Element Notation.  Dieser Inhalt kann direkt vom Paketersteller für Interaktionen mit Projektsystemen angegeben werden.  Weitere Informationen zum Konfigurieren der Inhaltsdateien in einem `.nuspec` Dokument befindet sich der [.nuspec Verweis](../reference/nuspec.md).

## <a name="nuget-locals-cache-management"></a>NuGet "lokal" Cache-Verwaltung

Die NuGet-Befehlszeile wurde aktualisiert, um Informationen zum Verwalten des lokalen Caches auf einer Arbeitsstation enthalten.  Weitere Informationen zum Befehl "lokal" steht in der [NuGet-Befehlszeilenreferenz](../tools/cli-ref-locals.md).

## <a name="fixed-issues"></a>Behobene Probleme

**Relevante Probleme**

* NuGet-Befehlszeilen wiederhergestellten-Unterstützung für die Wiederherstellung-Paketen mit einer Projektmappendatei auf Mono - [1543](https://github.com/NuGet/Home/issues/1543)

Die vollständige Liste der in der 3.3-Version behobene Probleme finden Sie auf GitHub unter der [3.3 Meilenstein](https://github.com/NuGet/Home/issues?q=is%3Aissue+milestone%3A3.3.0+is%3Aclosed).

Die Liste der in der Befehlszeile 3.3-Version behobene Probleme werden aufgezeichnet, der [3.3 Befehlszeilen Meilenstein](https://github.com/NuGet/Home/issues?q=is%3Aissue+is%3Aclosed+milestone%3A3.3.0-commandline).

## <a name="known-issues"></a>Bekannte Probleme

Wir weiterhin Probleme auf unserer GitHub-Problemliste zu verfolgen, die sich am befinden: [http://github.com/nuget/home/issues](http://github.com/nuget/home/issues)