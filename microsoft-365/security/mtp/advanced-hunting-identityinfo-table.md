---
title: Tabella IdentityInfo nello schema di caccia avanzato
description: Informazioni sugli account utente nella tabella IdentityInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3d59f987ae4d670e3d7c6f1638f8090ffc3ba7fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649308"
---
# <a name="identityinfo"></a>IdentityInfo

**Si applica a:**
- Microsoft Threat Protection

La `IdentityInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!NOTE]
>La tabella è stata rinominata da `AccountInfo` . Durante la ridenominazione, tutte le query salvate nel portale vengono aggiornate automaticamente. Controllare le query salvate altrove.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `OnPremSid` | stringa | ID di sicurezza locale (SID) dell'account |
| `CloudSid` | stringa | Identificatore di sicurezza cloud dell'account |
| `GivenName` | stringa | Nome o nome specificato dell'utente dell'account |
| `Surname` | stringa | Cognome, nome della famiglia o cognome dell'utente dell'account |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `Department` | stringa | Nome del reparto a cui appartiene l'utente dell'account |
| `JobTitle` | stringa | Titolo del processo dell'utente dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `EmailAddress` | stringa | Indirizzo SMTP dell'account |
| `SipProxyAddress` | stringa | Indirizzo SIP (Voice over IP (VOIP) Session Initiation Protocol) dell'account |
| `City` | stringa | Città in cui si trova l'utente dell'account |
| `Country` | stringa | Paese/area geografica in cui si trova l'account utente |
| `IsAccountEnabled` | boolean | Indica se l'account è abilitato o meno. |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra i dispositivi, i messaggi di posta elettronica, le app e le identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
