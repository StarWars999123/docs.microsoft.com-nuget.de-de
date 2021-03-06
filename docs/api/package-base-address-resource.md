---
title: Paketinhalt, NuGet-API
description: Die Basisadresse des Pakets ist eine einfache Schnittstelle zum Abrufen der des Pakets selbst.
author: joelverhagen
ms.author: jver
manager: skofman
ms.date: 10/26/2017
ms.topic: reference
ms.reviewer: kraigb
ms.openlocfilehash: a6ac40368f30d33f35d4ca0b6cc18ce4bd6efee5
ms.sourcegitcommit: 3eab9c4dd41ea7ccd2c28bb5ab16f6fbbec13708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31819176"
---
# <a name="package-content"></a>Paketinhalt

Es ist möglich, generieren eine URL für ein beliebiges Paket Inhalte (der .nupkg-Datei) mithilfe der V3-API abgerufen werden sollen. Die Ressource für das Abrufen von Paketinhalt verwendet die `PackageBaseAddress` Ressource gefunden, der [Dienst Index](service-index.md). Diese Ressource ermöglicht auch die Ermittlung aller Versionen eines Pakets aufgeführt oder nicht aufgeführte.

Diese Ressource wird häufig als entweder die "Paket Basisadresse" oder "Flatfile-Container" bezeichnet.

## <a name="versioning"></a>Versionskontrolle

Die folgenden `@type` Wert wird verwendet:

@type-Wert              | Hinweise
------------------------ | -----
PackageBaseAddress/3.0.0 | Die erste Version

## <a name="base-url"></a>Basis-URL

Die base-URL für die folgenden APIs ist der Wert der `@id` Eigenschaft, die zuvor erwähnten zur Ressource zugeordnete `@type` Wert. Im folgenden Dokument Platzhalter für die Basis-URL `{@id}` verwendet werden.

## <a name="http-methods"></a>HTTP-Methoden

Alle URLs, die bei der Unterstützung der Registrierung-Ressource gefunden, die HTTP-Methoden `GET` und `HEAD`.

## <a name="enumerate-package-versions"></a>Auflisten von Paketversionen

Wenn der Client bekannt eine Paket-ID ist und möchte Ermitteln der Paket-Versionen des Pakets die Quelle verfügbar ist, der Client eine vorhersagbare URL zum Aufzählen aller Paketversionen erstellen kann. Diese Liste ist dafür vorgesehen, "Verzeichnisliste" werden für die unten aufgeführten Content Paket-API.

> [!Note]
> Diese Liste enthält beide Paketversionen aufgeführt und nicht aufgeführte.

    GET {@id}/{LOWER_ID}/index.json

### <a name="request-parameters"></a>Anforderungsparameter

name     | In     | Typ    | Erforderlich | Hinweise
-------- | ------ | ------- | -------- | -----
LOWER_ID | URL    | Zeichenfolge  | ja      | Die Paket-ID Kleinbuchstaben

Die `LOWER_ID` Wert ist die gewünschte Paket-ID, die klein gemäß den Vergleichsregeln von implementiert. NET [ `System.String.ToLowerInvariant()` ](/dotnet/api/system.string.tolowerinvariant?view=netstandard-2.0#System_String_ToLowerInvariant) Methode.

### <a name="response"></a>Antwort

Wenn die Paketquelle keine Versionen der bereitgestellte Paket-ID verfügt, wird ein Statuscode "404" zurückgegeben.

Wenn die Paketquelle an eine oder mehrere Versionen verfügbar sind, wird ein Statuscode "200" zurückgegeben. Der Antworttext ist ein JSON-Objekt, wenn Sie die folgende Eigenschaft:

name     | Typ             | Erforderlich | Hinweise
-------- | ---------------- | -------- | -----
Versionen | Array von Zeichenfolgen | ja      | Die Paket-IDs verfügbar

Die Zeichenfolgen in die `versions` Array sind alle klein, [normalisiert NuGet Versionszeichenfolgen](../reference/package-versioning.md#normalized-version-numbers). Die Versionszeichenfolgen enthalten keine Metadaten Build SemVer 2.0.0.

Das Ziel ist, dass Versionszeichenfolgen, die in diesem Array gefunden wörtlich können, können Sie für verwendet werden die `LOWER_VERSION` Token in die folgenden Endpunkte gefunden.

### <a name="sample-request"></a>Beispielanforderung

    GET https://api.nuget.org/v3-flatcontainer/owin/index.json

### <a name="sample-response"></a>Beispielantwort

[!code-JSON [package-base-address-index.json](./_data/package-base-address-index.json)]

## <a name="download-package-content-nupkg"></a>Herunterladen von Paketinhalt (.nupkg)

Wenn der Client bekannt, ein Paket-ID und eine Version ist und den Paketinhalt herunterladen möchte, müssen sie nur so erstellen Sie die folgende URL:

    GET {@id}/{LOWER_ID}/{LOWER_VERSION}/{LOWER_ID}.{LOWER_VERSION}.nupkg

### <a name="request-parameters"></a>Anforderungsparameter

name          | In     | Typ   | Erforderlich | Hinweise
------------- | ------ | ------ | -------- | -----
LOWER_ID      | URL    | Zeichenfolge | ja      | Die Paket-ID Kleinbuchstaben
LOWER_VERSION | URL    | Zeichenfolge | ja      | Die Paketversion normalisiert und klein

Beide `LOWER_ID` und `LOWER_VERSION` sind klein gemäß den Vergleichsregeln von implementiert. NET [ `System.String.ToLowerInvariant()` ](/dotnet/api/system.string.tolowerinvariant?view=netstandard-2.0#System_String_ToLowerInvariant) Methode.

Die `LOWER_VERSION` ist die gewünschte Paketversion normalisiert mithilfe des NuGet-Version [Normalisierungsregeln](../reference/package-versioning.md#normalized-version-numbers). Dies bedeutet, dass dieser Build-Metadaten, die die SemVer 2.0.0-Spezifikation nicht zulässig ist in diesem Fall ausgeschlossen werden sollen.

### <a name="response-body"></a>Antworttext

Wenn das Paket auf die Paketquelle vorhanden ist, wird ein Statuscode "200" zurückgegeben. Der Antworttext wird der Inhalt des Pakets selbst sein.

Wenn das Paket auf die Paketquelle nicht vorhanden ist, wird ein Statuscode "404" zurückgegeben.

### <a name="sample-request"></a>Beispielanforderung

    GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg

### <a name="sample-response"></a>Beispielantwort

Der binäre Datenstrom, der NUPKG für Newtonsoft.Json 9.0.1 darstellt.

## <a name="download-package-manifest-nuspec"></a>Paketmanifest (.nuspec) herunterladen

Wenn der Client bekannt, ein Paket-ID und eine Version ist und das Paketmanifest herunterladen möchte, müssen sie nur so erstellen Sie die folgende URL:

    GET {@id}/{LOWER_ID}/{LOWER_VERSION}/{LOWER_ID}.nuspec

### <a name="request-parameters"></a>Anforderungsparameter

name          | In     | Typ    | Erforderlich | Hinweise
------------- | ------ | ------- | -------- | -----
LOWER_ID      | URL    | Zeichenfolge  | ja      | Die Paket-ID Kleinbuchstaben
LOWER_VERSION | URL    | Ganze Zahl | ja      | Die Paketversion normalisiert und klein

Beide `LOWER_ID` und `LOWER_VERSION` sind klein gemäß den Vergleichsregeln von implementiert. NET [ `System.String.ToLowerInvariant()` ](/dotnet/api/system.string.tolowerinvariant?view=netstandard-2.0#System_String_ToLowerInvariant) Methode.

Die `LOWER_VERSION` ist die gewünschte Paketversion normalisiert mithilfe des NuGet-Version [Normalisierungsregeln](../reference/package-versioning.md#normalized-version-numbers). Dies bedeutet, dass dieser Build-Metadaten, die die SemVer 2.0.0-Spezifikation nicht zulässig ist in diesem Fall ausgeschlossen werden sollen.

### <a name="response-body"></a>Antworttext

Wenn das Paket auf die Paketquelle vorhanden ist, wird ein Statuscode "200" zurückgegeben. Der Antworttext werden Paketmanifest, also die .nuspec in die entsprechende .nupkg enthalten sind. Die .nuspec ist ein XML-Dokument.

Wenn das Paket auf die Paketquelle nicht vorhanden ist, wird ein Statuscode "404" zurückgegeben.

### <a name="sample-request"></a>Beispielanforderung

    GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/6.0.4/newtonsoft.json.nuspec

### <a name="sample-response"></a>Beispielantwort

[!code-XML [newtonsoft.json.6.0.4.xml](./_data/newtonsoft.json.6.0.4.xml)]
