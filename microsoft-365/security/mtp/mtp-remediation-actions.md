---
title: Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection
description: Ottenere una panoramica delle azioni correttive che seguono le indagini automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502938"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Azioni di correzione che seguono indagini automatizzate in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Azioni correttive

Durante e dopo un'analisi automatizzata in Microsoft Threat Protection, le azioni di correzione vengono identificate per gli elementi dannosi o sospetti. Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint. Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica. Indagini automatizzate complete dopo che sono state apportate, approvate o rifiutate le azioni di correzione.

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection: 

|Azioni di correzione del dispositivo (endpoint)  |Azioni correttive della posta elettronica  |
|---------|---------|
|-Raccogliere il pacchetto di indagine <br/>-Isolate Device (questa azione può essere annullata)<br/>-Trasferisce Machine <br/>-Esecuzione del codice di rilascio <br/>-Rilascio dalla quarantena <br/>-Esempio di richiesta <br/>-Limitare l'esecuzione del codice (questa azione può essere annullata) <br/>-Eseguire l'analisi antivirus <br/>-Arrestare e mettere in quarantena      |-Blocca URL (tempo di clic)<br/>-Eliminare i messaggi di posta elettronica o i cluster<br/>-Posta in quarantena<br/>-Mettere in quarantena un allegato di posta elettronica<br/>-Disattivare l'inoltro della posta esterna          |

Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Le azioni correttive seguono indagini automatizzate

Una volta completata un'indagine automatizzata, viene emesso un verdetto per ogni prova inclusa e vengono identificate le azioni correttive. In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle. Nella tabella seguente sono elencati i possibili verdetti e i risultati:

|Verdetto    |Area    |Risultati|
|------|------|------|
|Dannosa    |Dispositivi (endpoint)    |Le azioni correttive vengono eseguite automaticamente|
|Dannosa    |Contenuto della posta elettronica (URL o allegati) | Le azioni correttive consigliate sono in attesa di approvazione|
|Sospetta    |Dispositivi o contenuto della posta elettronica |Le azioni correttive consigliate sono in attesa di approvazione|
|Non sono state trovate minacce    |Dispositivi o contenuto della posta elettronica    |Non sono necessarie azioni correttive|

[Rivedere un'azione in sospeso nel centro notifiche](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere! [Segnala falsi positivi/negativi](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Passaggi successivi

- [Approva o rifiuta azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Altre informazioni sul centro notifiche](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
