---
title: Bericht Missbrauch URL-Vorlage, NuGet-API | Microsoft Docs
author:
- joelverhagen
- kraigb
ms.author:
- joelverhagen
- kraigb
manager: skofman
ms.date: 10/26/2017
ms.topic: reference
ms.prod: nuget
ms.technology: 
description: "Der Bericht Missbrauch URL-Vorlage kann Clients einen Missbrauch Berichtslink in ihre Benutzeroberfläche anzeigen."
keywords: NuGet-API Melden des Missbrauchs, NuGet-API-Datei kompatibel, NuGet.org-Berichts-URL-Vorlage
ms.reviewer:
- karann
- unniravindranathan
ms.openlocfilehash: c12be294c71547fbce421c72aa091e0eee15aacd
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="report-abuse-url-template"></a>Berichtsvorlage Missbrauch-URL

Es ist möglich, dass ein Client eine URL zu erstellen, die vom Benutzer zum Melden des Missbrauchs zu einem bestimmten Paket verwendet werden kann. Dies ist hilfreich, wenn eine Paketquelle möchte, um alle Clients Erfahrungen (auch 3rd Party) Missbrauch Berichte für die Paketquelle delegieren zu erzielen.

Die Ressource für das Abrufen von Paketinhalt verwendet die `ReportAbuseUriTemplate` Ressource gefunden, der [Dienst Index](service-index.md).

## <a name="versioning"></a>Versionskontrolle

Die folgenden `@type` Werte werden verwendet:

@type-Wert                       | Hinweise
--------------------------------- | -----
ReportAbuseUriTemplate/3.0.0-beta | Die erste Version
ReportAbuseUriTemplate/3.0.0-rc   | Alias der`ReportAbuseUriTemplate/3.0.0-beta`

## <a name="url-template"></a>URL-Vorlage

Die URL für die folgende API wird der Wert von der `@id` mit einem der oben genannten Ressource verknüpfte Eigenschaft `@type` Werte.

## <a name="http-methods"></a>HTTP-Methoden

Obwohl der Client nicht vorgesehen ist, damit Anforderungen an die URL des Berichts Missbrauch im Namen des Benutzers zu senden, sollte die Webseite unterstützen die `GET` Methode, um eine URL geklickt wurde, problemlos in einem Webbrowser geöffnet werden zuzulassen.

## <a name="construct-the-url"></a>Die URL zu erstellen

Erteilt ein bekannter Paket-ID und eine Version, kann die Clientimplementierung eine URL verwendet, um eine Weboberfläche zugreifen zu erstellen. Die Clientimplementierung sollte diese erstellte URL (oder einen klickbaren Link) für den Benutzer, die sie zulassen, dass auf einen Webbrowser an die URL öffnen, und stellen alle erforderlichen Missbrauch Bericht anzeigen. Die Implementierung des Formulars Bericht Missbrauch richtet sich nach der Server-Implementierung.

Der Wert, der die `@id` ist eine URL-Zeichenfolge, die keines der folgenden Platzhalter-Token enthält:

### <a name="url-placeholders"></a>URL-Platzhalter

name        | Typ    | Erforderlich | Hinweise
----------- | ------- | -------- | -----
`{id}`      | Zeichenfolge  | Nein       | Die Paket-ID zum Melden des Missbrauchs für
`{version}` | Zeichenfolge  | Nein       | Die Paketversion zum Melden des Missbrauchs für

Die `{id}` und `{version}` Werte interpretiert werden, durch die Implementierung der Server muss die Groß-/Kleinschreibung bei, und gibt an, ob die Version normalisiert wird nicht beachtet.

Beispielsweise sieht sich der Nuget.org Missbrauch Berichtsvorlage wie folgt:

    https://www.nuget.org/packages/{id}/{version}/ReportAbuse

Wenn die Clientimplementierung einen Link zum Bericht Missbrauch Formular für NuGet.Versioning 4.3.0 anzuzeigen muss, würde es erzeugt die folgende URL und für den Benutzer bereitstellen:

    https://www.nuget.org/packages/NuGet.Versioning/4.3.0/ReportAbuse