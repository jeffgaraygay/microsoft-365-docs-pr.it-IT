---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-report attività gruppi di Yammer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Ottenere il report attività dei gruppi di Yammer per conoscere il numero di gruppi di Yammer creati e utilizzati nell'organizzazione e la loro attività.
ms.openlocfilehash: a5a9d3d8820241cc3d99a4a08e647bd05dafd5ef
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387442"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-report attività gruppi di Yammer

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md). Nel report Attività dei gruppi di Yammer, è possibile ottenere informazioni approfondite sull'attività dei gruppi di Yammer nell'organizzazione e vedere quanti gruppi di Yammer vengono creati e usati.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Come accedere al report Attività dei gruppi di Yammer

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **Yammer** \> **attività gruppi**di Yammer.
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretare il report Attività dei gruppi di Yammer

Per avere una visuale delle attività dei gruppi di Yammer, è possibile osservare i grafici **Gruppi** e **Attività**.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |Il report **Attività dei gruppi di Yammer** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore. <br/> |
|3.  <br/> |La visualizzazione **Gruppi** mostra il numero totale di gruppi esistenti e quanti di essi hanno eseguito attività di conversazione di gruppo.  <br/> |
|4.  <br/> |La visualizzazione **Attività** mostra il numero di messaggi di Yammer pubblicati, letti e con Mi piace nei gruppi.  <br/> |
|5.  <br/> | Nel grafico **Gruppi** l'asse Y rappresenta il numero dei gruppi totali o attivi.  <br/>  Nel grafico **Attività** l'asse Y rappresenta il numero delle attività specificate per i gruppi di Yammer.  <br/>  L'asse X in tutti e tre i grafici rappresenta l'intervallo di date selezionato per il report specifico.  <br/> |
|6.  <br/> |È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **gruppi** selezionare Icone totali **o** **attive** ![ complessive e attive ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) per visualizzare solo le informazioni relative a ognuna di esse.   La modifica di questa selezione non modifica le informazioni nella tabella della griglia.  <br/> |
|7.  <br/> | L'elenco dei gruppi da mostrare dipende dal set di tutti i gruppi che erano presenti (che non sono stati eliminati) nel periodo della relazione più ampio (180 giorni). Il numero di attività (i messaggi ricevuti) varia in base alla data selezionata.  <br/> Nota: è possibile che non vengano visualizzati tutti gli elementi nell'elenco in basso nelle colonne finché non vengono aggiunti.<br/>**Nome gruppo** è il nome del gruppo.  <br/> **Amministratore gruppo** è il nome dell'amministratore del gruppo o del proprietario.  <br/> **Eliminati** è il numero di gruppi di Yammer eliminati. Se il gruppo viene eliminato, ma c'è stata attività nel periodo della relazione, verrà visualizzato nella griglia con questo flag impostato su true.  <br/> **Tipo** indica il tipo di gruppo, ad esempio pubblico o privato.  <br/> **Connesso a Office 365** indica se il gruppo Yammer è anche un gruppo di Microsoft 365.  <br/> **Data ultima attività** è la data più recente in cui un messaggio è stato letto, pubblicato o apprezzato dal gruppo.  <br/> **Membri** è il numero di membri del gruppo.  <br/> **Pubblicati** è il numero dei messaggi pubblicati nel gruppo di Yammer nel periodo di riferimento.  <br/> **Letti** è il numero delle conversazioni lette nel gruppo di Yammer nel periodo di riferimento.  <br/> **Apprezzati** è il numero dei messaggi con Mi piace nel gruppo di Yammer nel periodo di riferimento.  <br/>  Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** in [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Selezionare **colonne** per aggiungere o rimuovere colonne dal report.  <br/> ![Yammer groups activity - choose columns](../../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati.  <br/> |
|||
   

