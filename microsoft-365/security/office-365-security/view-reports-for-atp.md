---
title: Visualizzare i report per Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro &amp; sicurezza e conformità.
ms.openlocfilehash: d5f0958d199684a9d6ca6bfe4ed01c0ab9102a2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084916"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualizzare i report per Office 365 Advanced Threat Protection

Se l'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) ed è necessario disporre delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile utilizzare diversi rapporti ATP nel &amp; Centro sicurezza e conformità. (Andare al **** \> **Dashboard**di report).
  
![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I report ATP includono quanto segue:
- [Rapporto sullo stato della protezione dalle minacce](#threat-protection-status-report)
- [Rapporto tipi di file ATP](#atp-file-types-report)
- [Rapporto di disposizione del messaggio ATP](#atp-message-disposition-report)
- [rilevamenti o esploratori in tempo reale](threat-explorer.md) (a seconda che si disponga di Office 365 ATP piano 1 o 2)
- ... [e altro ancora](#additional-reports-to-view). 

Leggere questo articolo per ottenere una panoramica dei rapporti ATP e su come usarli.
  
## <a name="threat-protection-status-report"></a>Rapporto sullo stato della protezione dalle minacce

Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e [Office 365 ATP](office-365-atp.md). Questo report è utile per la visualizzazione di rilevamenti nel tempo (fino a 90 giorni) e consente agli amministratori della sicurezza di identificare le tendenze o determinare se i criteri devono essere adattati. 

Il rapporto sullo stato di protezione di minacce fornisce un numero aggregato di messaggi di posta elettronica univoci con contenuti dannosi, ad esempio i file o gli indirizzi del sito Web (URL) bloccati dal motore anti-malware, [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e le caratteristiche di ATP come [Collegamenti sicuri ATP](atp-safe-links.md), [allegati sicuri di ATP](atp-safe-attachments.md)e [funzionalità di anti-phishing ATP](atp-anti-phishing.md). 

> [!NOTE]
> Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP. Ad esempio, il rapporto sullo stato della protezione dalle minacce per i clienti ATP conterrà informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md). Tali informazioni sono specifiche di ATP, quindi i clienti che hanno EOP ma non ATP non vedranno tali dettagli nella loro relazione sullo stato di protezione dalle minacce.
  
Per visualizzare il rapporto sullo stato di protezione dalle minacce, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> **** \> **lo stato di protezione delle minacce**del dashboard.
  
![Rapporto sullo stato di protezione ATP con minacce](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Per ottenere lo stato dettagliato per un giorno, posizionare il puntatore del mouse sul grafico.
  
![Dati sullo stato della protezione da ATP per un giorno](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
Per impostazione predefinita, il rapporto sullo stato della protezione dalle minacce Visualizza i dati negli ultimi sette giorni. Tuttavia, è possibile scegliere **filtri** e modificare l'intervallo di date per visualizzare i dati fino a 90 giorni. Se si utilizza un abbonamento di valutazione, potrebbe essere limitato a 30 giorni di dati.
  
![Filtri di stato di protezione da minacce ATP](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
È inoltre possibile utilizzare il menu **Visualizza dati in base** a per modificare le informazioni visualizzate nel report. 
  
![Opzioni di visualizzazione per il rapporto sullo stato della protezione da ATP](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Rapporto tipi di file ATP

Il rapporto **tipi di file ATP** Visualizza il tipo di file rilevati come dannosi dagli [allegati sicuri di ATP](atp-safe-attachments.md).
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **ATP types**.
  
![Rapporto tipi di file ATP](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Quando si posiziona il puntatore del mouse su un determinato giorno, è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri ATP](atp-safe-attachments.md) e dalla [protezione anti-malware antispamming &amp; in Office 365](anti-spam-and-anti-malware-protection.md).
  
![I tipi di file ATP riportano i dati per un giorno](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Rapporto di disposizione del messaggio ATP

Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **disposizione dei messaggi**per il **Dashboard** \> dei **report** \> ATP.
  
![Rapporto di disposizione del messaggio ATP](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Quando si posiziona il puntatore del mouse su una barra del grafico, è possibile vedere quali azioni sono state eseguite per il messaggio di posta elettronica rilevato per quel giorno.
  
![Dati del rapporto disposizione dei messaggi ATP per un giorno](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Report aggiuntivi da visualizzare

Oltre ai report ATP descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:

|Report (s)  |Dettagli  |
|---------|---------|
|**Esploratori** o **rilevamenti in tempo reale** (i clienti di Office 365 trifosfato di adenosina piano 2 hanno esploratori; I clienti di Office 365 ATP Plan 1 dispongono di rilevamenti in tempo reale.| [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md)       |
|Report di **protezione della posta elettronica**, ad esempio un report mittenti e destinatari principali, un report di posta indesiderata e un report di rilevamenti di spam. | [Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità](../../compliance/view-email-security-reports.md)        |
|**Traccia URL collegamenti sicuri ATP** (Si tratta di un report generato tramite PowerShell). Questo rapporto illustra i risultati delle azioni di collegamenti sicuri ATP negli ultimi sette (7) giorni. |[Informazioni di riferimento sui cmdlet Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|**Risultati di EOP e ATP** (Si tratta di un report personalizzato generato tramite PowerShell). Questo report contiene informazioni, ad esempio dominio, data, tipo di evento, direzione, azione e numero di messaggi.  | [Informazioni di riferimento sui cmdlet Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**Rilevamenti di EOP e ATP** (Si tratta di un report personalizzato generato tramite PowerShell). Questo report contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.   | [Informazioni di riferimento sui cmdlet Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Quali autorizzazioni sono necessarie per visualizzare i report ATP?

Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.

- Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:
    - Gestione organizzazione
    - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ())
    - Lettore di sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i rapporti non mostrano dati?

Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente. L'organizzazione deve disporre di [criteri dei collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) e di criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione da ATP sia sul posto. Vedere anche [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nel centro sicurezza &amp; e conformità](create-a-schedule-for-a-report.md)
  
[Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità](set-up-and-download-a-custom-report.md)
  
