---
title: Valori di livello di reclamo in blocco, messaggi di posta in blocco, livelli di BCL, come funziona BCL, valutazioni BCL, antispam, intestazione antispam, filtro posta in blocco, Interrompi posta in blocco
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione X-Microsoft-antispam di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere intestazioni dei messaggi di protezione da posta indesiderata.
ms.openlocfilehash: 9fa3549aab6f6c2a9f0c6efb0915a6a4f25eb810
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083866"
---
# <a name="bulk-complaint-level-values"></a>Valori di livello di reclamo in blocco

I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dell'elenco. Alcuni sono buoni mailer che inviano messaggi desiderati con contenuto pertinente ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. Per distinguere questi tipi di messaggi di posta elettronica in blocco, viene assegnato un punteggio di livello di reclamo in blocco da parte di un messaggio di posta elettronica in blocco. Le valutazioni BCL variano da 1 a 9 a seconda di quanto è probabile che il mailer di posta in blocco debba generare reclami. Un mittente che ha un punteggio di BCL 9 può generare molti reclami dai destinatari, mentre non è probabile che un punteggio di BCL 3 generi molti reclami. Microsoft utilizza origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata. Questa valutazione è esposta nell'intestazione **X-Microsoft-antispam** di ogni messaggio. Per ulteriori informazioni su questa intestazione del messaggio, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).

Poiché un mailer di posta in blocco con una valutazione pari a 9 rischia di generare reclami, la BCL predefinita è 7. Questo significa che i messaggi di posta in blocco verranno accettati fino a quando il livello di reclamo di 7 e la posta non verranno accettati successivamente. Minore è la classificazione, minore è l'accettazione della posta in blocco. Se gli utenti sono e il loro lavoro è sensibile alla posta in blocco e la BCL è impostata su 4, non verrà accettata la posta in blocco con una BCL superiore a 4.
  
È possibile utilizzare i valori BCL per impostare il livello di filtro di massa desiderato per l'organizzazione, attenendosi alla procedura descritta in [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).
  
Sono stati aggiunti altri valori BCL che verranno inclusi in futuro. Nella tabella seguente sono elencati e descritti i valori BCL attualmente in uso.
  
|||
|:-----|:-----|
|**Valore BCL** <br/> |**Descrizione** <br/> |
|0  <br/> |Il messaggio non viene da un mittente in blocco.  <br/> |
|1, 2, 3  <br/> |Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.  <br/> |
|4, 5, 6, 7  <br/> |Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.  <br/> |
|8, 9  <br/> |Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce  <br/> |
   
