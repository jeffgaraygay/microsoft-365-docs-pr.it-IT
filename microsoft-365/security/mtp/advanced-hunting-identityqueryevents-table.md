---
title: Tabella IdentityQueryEvents nello schema di caccia avanzato
description: Informazioni sugli eventi di query di Active Directory nella tabella IdentityQueryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identità, query LDAP
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929274"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Si applica a:**
- Microsoft Threat Protection

La `IdentityQueryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle query eseguite su oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `Query` | stringa | Tipo di query: QueryGroup, QueryUser o EnumerateUsers |
| `QueryObject` | stringa | Nome dell'utente, del gruppo, del dispositivo, del dominio o di qualsiasi altro tipo di entità su cui viene eseguita la query |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) dell'endpoint |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `Location` | stringa | Città, paese o altra località geografica associata all'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)