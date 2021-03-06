---
title: Qual &apos; è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?
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
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle differenze tra la posta indesiderata (posta indesiderata) e la posta elettronica in blocco (Gray mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826730"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco in EOP?

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, i clienti a volte chiedono: "Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?" In questo argomento viene illustrata la differenza e vengono descritti i controlli disponibili in EOP.

- La **posta** indesiderata è posta indesiderata, ovvero messaggi non richiesti e universalmente non necessari (se identificati correttamente). Per impostazione predefinita, il EOP respinge la posta indesiderata in base alla reputazione del server di posta elettronica di origine. Se un messaggio passa il controllo IP di origine, viene inviato al filtro per la posta indesiderata. Se il messaggio viene classificato come posta indesiderata dal filtro posta indesiderata, il messaggio viene (per impostazione predefinita) recapitato ai destinatari previsti e spostato nella cartella posta indesiderata.

  - È possibile configurare le azioni da intraprendere sui verdetti del filtro della posta indesiderata. Per istruzioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

  - Se non si è d'accordo con il verdetto del filtro della posta indesiderata, è possibile segnalare i messaggi che si considerano come posta indesiderata o non indesiderata a Microsoft in diversi modi, come descritto in [messaggi e file di report a Microsoft](report-junk-email-messages-to-microsoft.md)

- La posta **elettronica in blocco** (nota anche come _posta grigia_) è più difficile da classificare. Se la posta indesiderata è una minaccia costante, la posta elettronica in blocco è spesso una pubblicità o un messaggio di marketing. Alcuni utenti desiderano messaggi di posta elettronica in blocco (e, in effetti, hanno deliberatamente iscritto per riceverli), mentre altri utenti considerano la posta elettronica in blocco come posta indesiderata. Ad esempio, alcuni utenti desiderano ricevere messaggi pubblicitari dalla Contoso Corporation o inviti a una conferenza imminente sulla sicurezza cibernetica, mentre altri utenti considerano gli stessi messaggi come posta indesiderata.

  Per ulteriori informazioni sul modo in cui è stato identificato il messaggio di posta elettronica in blocco, vedere [bulk lamentel Level (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Come gestire la posta elettronica in blocco

A causa della reazione mista al messaggio di posta elettronica in blocco, non vi sono indicazioni universali valide per ogni organizzazione.

I criteri di protezione dalla posta indesiderata hanno una soglia BCL predefinita utilizzata per identificare la posta elettronica in blocco come posta indesiderata. Gli amministratori possono aumentare o diminuire la soglia. Per ulteriori informazioni, vedere i seguenti argomenti:

- [Configurazione dei criteri di protezione da posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- [Impostazioni dei criteri di protezione da posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Un'altra opzione facilmente trascurabile: se un utente si lamenta della ricezione di posta elettronica in blocco, ma i messaggi vengono inviati da mittenti affidabili che passano il filtro per la posta indesiderata in EOP, fare in modo che l'utente verifichi un'opzione di annullamento della sottoscrizione nel messaggio di posta elettronica in blocco.
