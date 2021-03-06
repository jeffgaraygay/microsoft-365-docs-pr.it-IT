---
title: Correggere informazioni dettagliate sulle regole del flusso di posta lento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare le & regole del flusso di posta indesiderata per identificare e correggere le regole del flusso di posta inefficienti o interrotte (note anche come regole di trasporto) nell'organizzazione.
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826882"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Fix Slow Mail Flow Rules Insight nel centro sicurezza & Compliance

Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione. Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione. Di seguito sono riportati alcuni esempi di questi tipi di regole:

- Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.
- Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.
- Condizioni che utilizzano il controllo del contenuto negli allegati.

La **correzione delle regole del flusso di posta lenta** nell'area **consigliata per l'utente** del [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel centro sicurezza & conformità informa quando una regola del flusso di posta richiede troppo tempo per essere completata. Questa intuizione viene visualizzata solo dopo che è stata rilevata la condizione (se non si dispone di alcun loop di posta elettronica, non si vedrà l'Insight).

È possibile utilizzare questa notifica per identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.

![Fix Slow Mail Flow Rules Insight nelle aree consigliate per l'area del dashboard del flusso di posta](../../media/mfi-fix-slow-mail-flow-rules.png)

Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:

- **Regola**: è possibile posizionare il puntatore del mouse sul riepilogo per visualizzare tutte le condizioni, le eccezioni e le azioni della regola. È possibile fare clic sul riepilogo per modificare la regola nell'interfaccia di amministrazione di Exchange (EAC).
- **Numero di messaggi valutati**: è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati di [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi che sono stati interessati dalla regola.
- **Tempo medio impiegato per ogni messaggio**
- **Tempo mediano dedicato a un messaggio**: il valore medio che separa la metà superiore dalla metà inferiore dei dati temporali.

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli nell'Insight delle regole del flusso di posta lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Per ulteriori informazioni sulle condizioni e le eccezioni nelle regole del flusso di posta in Exchange Online, vedere [Mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
