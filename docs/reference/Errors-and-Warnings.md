---
title: NuGet-Fehler und Warnungen-Referenz
description: Vollständige Referenz für Warnungen und Fehler, die aus NuGet während der verschiedenen NuGet-Vorgänge ausgegeben.
author: karann-msft
ms.author: karann
manager: unnir
ms.date: 05/18/2018
ms.topic: reference
ms.reviewer: anangaur
ms.openlocfilehash: df6ed51e182829ecef441f3a0b467f034e92415b
ms.sourcegitcommit: c643dd2c44e085601551ff7079d696bcc3ad2b49
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42793241"
---
# <a name="errors-and-warnings"></a>Fehler und Warnungen

In NuGet 4.3.0 Fehler und Warnungen sind nummeriert, wie in diesem Thema beschrieben und enthalten ausführliche Informationen zum Beheben der Probleme im Zusammenhang mit beitragen.

Die Fehler und Warnungen, die hier aufgeführten stehen nur mit [PackageReference-basierte](../consume-packages/package-references-in-project-files.md) Projekte und NuGet 4.3.0. NuGet berücksichtigt auch MSBuild-Eigenschaften, um Warnungen unterdrücken oder diese zu Fehlern heraufstufen. Weitere Informationen finden Sie unter [wie: Unterdrücken von Compilerwarnungen](/visualstudio/ide/how-to-suppress-compiler-warnings) in Visual Studio-Dokumentation.

**Fehler**

| Gruppieren | Fehlernummern |
| --- | --- |
| Ungültige Eingabefehler | [NU1001](./errors-and-warnings/NU1001.md), [NU1002](./errors-and-warnings/NU1002.md), [NU1003](./errors-and-warnings/NU1003.md) |
| Fehler aufgrund fehlender Paket- und | [NU1100](./errors-and-warnings/NU1100.md), [NU1101](./errors-and-warnings/NU1101.md), [NU1102](./errors-and-warnings/NU1102.md), [NU1103](./errors-and-warnings/NU1103.md), [NU1104](./errors-and-warnings/NU1104.md), [NU1105](./errors-and-warnings/NU1105.md), [NU1106](./errors-and-warnings/NU1106.md), [NU1107](./errors-and-warnings/NU1107.md), [NU1108](./errors-and-warnings/NU1108.md) |
| Kompatibilitätsfehler | [NU1201](./errors-and-warnings/NU1201.md), [NU1202](./errors-and-warnings/NU1202.md), [NU1203](./errors-and-warnings/NU1203.md), [NU1401](./errors-and-warnings/NU1401.md) |
| Interner Fehler von NuGet | [NU1000](./errors-and-warnings/NU1000.md) |
| Signierte Pakete-Fehler (Erstellung und Überprüfung) | [NU3001](./errors-and-warnings/NU3001.md), [NU3004](./errors-and-warnings/NU3004.md), [NU3005](./errors-and-warnings/NU3005.md), [NU3008](./errors-and-warnings/NU3008.md), [NU3012](./errors-and-warnings/NU3012.md), [NU3028](./errors-and-warnings/NU3028.md) |
| Pack-Fehler | [NU5000](./errors-and-warnings/NU5000.md), [NU5001](./errors-and-warnings/NU5001.md), [NU5002](./errors-and-warnings/NU5002.md), [NU5003](./errors-and-warnings/NU5003.md), [NU5004](./errors-and-warnings/NU5004.md), [NU5005](./errors-and-warnings/NU5005.md), [NU5007](./errors-and-warnings/NU5007.md), [NU5008](./errors-and-warnings/NU5008.md), [NU5009](./errors-and-warnings/NU5009.md), [NU5010](./errors-and-warnings/NU5010.md), [NU5011](./errors-and-warnings/NU5011.md), [NU5012](./errors-and-warnings/NU5012.md), [NU5013](./errors-and-warnings/NU5013.md), [NU5014](./errors-and-warnings/NU5014.md), [NU5015](./errors-and-warnings/NU5015.md), [NU5016](./errors-and-warnings/NU5016.md), [NU5017](./errors-and-warnings/NU5017.md), [ NU5018](./errors-and-warnings/NU5018.md), [NU5019](./errors-and-warnings/NU5019.md), [NU5020](./errors-and-warnings/NU5020.md), [NU5021](./errors-and-warnings/NU5021.md), [NU5022](./errors-and-warnings/NU5022.md), [NU5023](./errors-and-warnings/NU5023.md), [NU5024](./errors-and-warnings/NU5024.md), [NU5025](./errors-and-warnings/NU5025.md), [NU5026](./errors-and-warnings/NU5026.md), [NU5027](./errors-and-warnings/NU5027.md), [NU5028](./errors-and-warnings/NU5028.md), [NU5029](./errors-and-warnings/NU5029.md)

**Warnungen**

| Gruppieren | Warnungsnummern |
| --- | --- |
| Ungültige Eingabe-Warnungen | [NU1501](./errors-and-warnings/NU1501.md), [NU1502](./errors-and-warnings/NU1502.md), [NU1503](./errors-and-warnings/NU1503.md) |
| Unerwarteter Paket Version Warnungen | [NU1601](./errors-and-warnings/NU1601.md), [NU1602](./errors-and-warnings/NU1602.md), [NU1603](./errors-and-warnings/NU1603.md), [NU1604](./errors-and-warnings/NU1604.md), [NU1605](./errors-and-warnings/NU1605.md), [NU1606](./errors-and-warnings/NU1108.md), [NU1607](./errors-and-warnings/NU1107.md) |
| Warnungen der Resolver-Konflikt | [NU1608](./errors-and-warnings/NU1608.md) |
| Paket-fallback-Warnungen | [NU1701](./errors-and-warnings/NU1701.md) |
| Feed-Warnungen | [NU1801](./errors-and-warnings/NU1801.md) |
| Interne NuGet-Warnungen | [NU1500](./errors-and-warnings/NU1500.md) |
| Signierte Pakete Warnungen (Erstellung und Überprüfung) | [NU3000](./errors-and-warnings/NU3000.md), [NU3002](./errors-and-warnings/NU3002.md), [NU3003](./errors-and-warnings/NU3003.md), [NU3006](./errors-and-warnings/NU3006.md), [NU3007](./errors-and-warnings/NU3007.md), [NU3009](./errors-and-warnings/NU3009.md), [NU3010](./errors-and-warnings/NU3010.md), [NU3011](./errors-and-warnings/NU3011.md), [NU3013](./errors-and-warnings/NU3013.md), [NU3014](./errors-and-warnings/NU3014.md), [NU3015](./errors-and-warnings/NU3015.md), [NU3016](./errors-and-warnings/NU3016.md), [NU3017](./errors-and-warnings/NU3017.md), [NU3018](./errors-and-warnings/NU3018.md), [NU3019](./errors-and-warnings/NU3019.md), [NU3020](./errors-and-warnings/NU3020.md), [NU3021](./errors-and-warnings/NU3021.md), [ NU3022](./errors-and-warnings/NU3022.md), [NU3023](./errors-and-warnings/NU3023.md), [NU3025](./errors-and-warnings/NU3025.md), [NU3027](./errors-and-warnings/NU3027.md) |
| Warnungen | [NU5100](./errors-and-warnings/NU5100.md), [NU5101](./errors-and-warnings/NU5101.md), [NU5102](./errors-and-warnings/NU5102.md), [NU5103](./errors-and-warnings/NU5103.md), [NU5104](./errors-and-warnings/NU5104.md), [NU5105](./errors-and-warnings/NU5105.md), [NU5106](./errors-and-warnings/NU5106.md), [NU5107](./errors-and-warnings/NU5107.md), [NU5108](./errors-and-warnings/NU5108.md), [NU5109](./errors-and-warnings/NU5109.md), [NU5110](./errors-and-warnings/NU5110.md), [NU5111](./errors-and-warnings/NU5111.md), [NU5112](./errors-and-warnings/NU5112.md), [NU5114](./errors-and-warnings/NU5114.md), [NU5115](./errors-and-warnings/NU5115.md), [NU5116](./errors-and-warnings/NU5116.md), [NU5117](./errors-and-warnings/NU5117.md), [ NU5118](./errors-and-warnings/NU5118.md), [NU5119](./errors-and-warnings/NU5119.md), [NU5120](./errors-and-warnings/NU5120.md), [NU5121](./errors-and-warnings/NU5121.md), [NU5122](./errors-and-warnings/NU5122.md), [NU5123](./errors-and-warnings/NU5123.md), [NU5500](./errors-and-warnings/NU5500.md)
