---
title: Infrastruttura IT ed esigenze di business di Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo le esigenze aziendali sono state soddisfatte da Microsoft 365 per Enterprise.
ms.openlocfilehash: 3dd744a8d936307c61303bf8ba0f2f198af59d91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685831"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Infrastruttura IT ed esigenze di business di Contoso

Contoso sta cambiando la propria infrastruttura IT da un modello centralizzato locale a un'infrastruttura comprensiva di cloud che gestisce carichi di lavoro di produttività personale e applicazioni basati sul cloud.

## <a name="contosos-existing-it-infrastructure"></a>Infrastruttura IT esistente di Contoso

Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.

La Figura 1 mostra l'ufficio di una sede con centri dati delle applicazioni, una rete perimetrale e Internet.

![Infrastruttura IT esistente di Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Figura 1: Infrastruttura IT esistente di Contoso**
 
I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi: 

- Applicazioni line of business personalizzate che utilizzano SQL Server e altri database Linux.
- Un set di server SharePoint legacy.
- Server a livello di organizzazione e di team per l'archiviazione dei file.

Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo. Questi server sono sotto il controllo dei reparti IT regionali.

La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.

Nella rete perimetrale degli uffici di Contoso, gruppi di server forniscono quanto segue:

- Hosting del sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, materiali o assistenza.
- Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.
- Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.

## <a name="contosos-business-needs"></a>Esigenze di business di Contoso

Le esigenze di business di Contoso rientrano in cinque categorie principali.

Produttività:

- Semplificare la collaborazione

  Sostituire il modello di collaborazione basato su posta elettronica e scambio di file con un modello online che consente di apportare modifiche in tempo reale ai documenti, partecipare a riunioni online e tenere traccia delle conversazioni.
- Migliorare la produttività per utenti remoti e mobili

  Dato il numero elevato di utenti che lavorano da casa o sul campo, è preferibile sostituire la soluzione VPN caratterizzata da colli di bottiglia con un accesso ai dati e alle risorse di Contoso nel cloud che sia in grado di garantire prestazioni migliori.
- Favorire la creatività e l'innovazione

  Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.

Sicurezza:

- Gestione di identità e accesso

  Applicare l'autenticazione a più fattori e altre forme di autenticazione e proteggere le credenziali dell'account di utenti e amministratori.

- Protezione dalle minacce

  Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.

- Protezione delle informazioni

  Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.

- Gestione della sicurezza

  Monitorare la postura di sicurezza ed essere in grado di rilevare le minacce in tempo reale ed intervenire tempestivamente.

Accesso remoto e mobile e partner commerciali:

- Migliorare la sicurezza per lavoratori remoti e mobili

  Introdurre il BYOD e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto delle applicazioni e protezione dei dati aziendali.

- Ridurre l'infrastruttura di accesso remoto per i dipendenti

  Ridurre i costi relativi a manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando sul cloud le risorse a cui si accede normalmente.

- Fornire migliore connettività e ridurre le spese per le transazioni Business-to-Business (B2B)

  Sostituire l’extranet per i partner obsoleta e costosa con una soluzione basata su cloud che utilizzi l'autenticazione federata.

Conformità:

- Rispettare i requisiti normativi applicabili

  Essere conformi alle normative applicabili per la conservazione dei dati, la crittografia, la tutela della privacy dei dati e alle normative relative al trattamento dei dati personali, ad esempio il Regolamento generale sulla protezione dei dati (GDPR) per l'Unione Europea.

Gestione:

- Ridurre la spesa IT per la gestione del software dei computer e dei dispositivi client

  Automatizzare l'installazione degli aggiornamenti del sistema operativo Windows e Microsoft 365 Apps for enterprise nell'organizzazione.

## <a name="mapping-contosos-business-needs-to-microsoft-365-for-enterprise"></a>Mapping delle esigenze aziendali di Contoso a Microsoft 365 per Enterprise

Il reparto IT di Contoso ha associato le esigenze di business alle funzionalità di Microsoft 365 E5 prima dell'implementazione in questa tabella:


| Category | Esigenze aziendali | Microsoft 365 per prodotti o funzionalità aziendali |
|:-------|:-----|:-----|
| Produttività |  |  |
|  | Semplificare la collaborazione | Microsoft Teams, SharePoint, OneDrive |
|  | Migliorare la produttività per lavoratori remoti e mobili | Carichi di lavoro e dati basati sul cloud di Microsoft 365 |
|  | Favorire la creatività e l'innovazione | Windows Ink, Cortana at Work, PowerPoint |
| Sicurezza |  |  |
|  | Gestione di identità e accesso | Account di amministratore globali dedicati con Azure Multi-Factor Authentication (MFA) e Azure AD Privileged Identity Management (PIM) <BR> MFA per tutti gli account utente <BR> Accesso condizionale <BR> Windows Hello <BR> Windows Credential Guard |
|  | Protezione dalle minacce | Advanced Threat Analytics <BR> Windows Defender <BR> Protezione avanzata dalle minacce <BR> Office 365 Advanced Threat Protection <BR> Analisi e risposta alle minacce di Microsoft 365 <BR> |
|  | Protezione delle informazioni | Azure Information Protection <BR> Prevenzione della perdita dei dati (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Gestione della sicurezza | Centro sicurezza di Azure  <BR> Windows Defender Security Center |
| Accesso remoto e mobile e partner commerciali |  |  |
|  | Migliorare la sicurezza per lavoratori remoti e mobili | Microsoft Intune |
|  | Ridurre l'infrastruttura di accesso remoto per i dipendenti | Carichi di lavoro e dati basati sul cloud di Microsoft 365 |
|  | Fornire migliore connettività e ridurre le spese per le transazioni B2B | Autenticazione federata e risorse basate su cloud |
| Conformità |  |  |
|  | Rispettare i requisiti normativi applicabili | Funzionalità di GDPR in Microsoft 365 |
| Gestione |  |  |
|  | Ridurre la spesa IT per installare gli aggiornamenti del client | Anelli di distribuzione <BR> Aggiornamenti di Windows 10 Enterprise <BR> Aggiornamenti di App Microsoft 365 per grandi imprese |
||||

## <a name="next-step"></a>Passaggio successivo

[Informazioni](contoso-networking.md) sulla rete locale dell'azienda Contoso e come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud Microsoft 365.

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
