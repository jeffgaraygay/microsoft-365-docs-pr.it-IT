---
title: Configurare Teams con tre livelli di protezione
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-overview
- m365solution-securecollab
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: Suggerimenti di configurazione per proteggere i file in Microsoft Teams.
ms.openlocfilehash: d0c3d065da912c37ca21e6ea4300a30c5e7195b8
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527803"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Configurare Teams con tre livelli di protezione

Gli articoli in questa serie offrono suggerimenti per configurare i team in Microsoft Teams e i siti di SharePoint associati per la protezione dei file in modo da bilanciare la sicurezza con la facilità di collaborazione.

L'articolo definisce quattro diverse configurazioni, a partire da un team pubblico con i criteri di condivisione più aperti. Ogni configurazione aggiuntiva rappresenta un miglioramento significativo in termini di protezione, ma la possibilità di accedere e collaborare ai file archiviati nei si riduce al gruppo di membri dei team interessati. 

Le configurazioni descritte in questo articolo sono allineate alle raccomandazioni di Microsoft per i tre livelli di protezione per dati, identità e dispositivi:

- Protezione di base

- Protezione dati sensibili

- Protezione dati altamente sensibili

Per altre informazioni su questi livelli e sulle funzionalità consigliate per ogni livello, vedere le risorse seguenti.

- [Protezione di dispositivi e identità per Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Soluzioni per la protezione dei file in Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="three-tiers-at-a-glance"></a>I tre livelli a colpo d'occhio

La tabella seguente riepiloga le configurazioni per ogni livello. Usare queste configurazioni come punto di partenza e modificarle in base alle esigenze della propria organizzazione. Potrebbe non essere necessario implementare tutti i livelli.

||Di base (pubblico)|Di base (privato)|Dati sensibili|Altamente sensibili|
|:-----|:-----|:-----|:-----|:-----|
|Team privato o pubblico|Pubblico|Private|Private|Private|
|Chi può accedere?|Tutti gli utenti dell'organizzazione, inclusi gli utenti B2B.|Solo i membri del team. Altri utenti possono richiedere l'accesso al sito associato.|Solo i membri del team.|Solo i membri del team.|
|Canali privati|I proprietari e i membri possono creare canali privati|I proprietari e i membri possono creare canali privati|Solo i proprietari possono creare canali privati|Solo i proprietari possono creare canali privati|
|Accesso guest a livello di sito|**Utenti guest nuovi ed esistenti** (impostazione predefinita).|**Utenti guest nuovi ed esistenti** (impostazione predefinita).|**Utenti guest nuovi ed esistenti** o **Solo persone nell'organizzazione** in base alle esigenze del team.|**Utenti guest nuovi ed esistenti** o **Solo persone nell'organizzazione** in base alle esigenze del team.|
|Impostazioni di condivisione del sito|**I proprietari e i membri del sito e gli utenti con autorizzazioni di modifica possono condividere file e cartelle, ma solo i proprietari del sito possono condividere il sito**.|**I proprietari e i membri del sito e gli utenti con autorizzazioni di modifica possono condividere file e cartelle, ma solo i proprietari del sito possono condividere il sito**.|**I proprietari e i membri del sito e gli utenti con autorizzazioni di modifica possono condividere file e cartelle, ma solo i proprietari del sito possono condividere il sito**.|**Solo i proprietari del sito possono condividere file, cartelle e il sito**.<br>Richieste di accesso **disattivate**.|
|Accesso ai dispositivi non gestiti a livello di sito|**Consenti l'accesso completo dalle app desktop, dalle app per dispositivi mobili e dal Web** (impostazione predefinita).|**Consenti l'accesso completo dalle app desktop, dalle app per dispositivi mobili e dal Web** (impostazione predefinita).|**Consenti l'accesso limitato, solo sul Web**.|**Blocca accesso**.|
|Tipo di collegamento di condivisione predefinito|**Solo gli utenti dell’organizzazione**|**Solo gli utenti dell’organizzazione**|**Persone specifiche**|**Persone con accesso esistente**|
|Etichette di riservatezza|Nessuno|Nessuno|Etichetta di riservatezza usata per classificare il team e controllare la condivisione guest e l'accesso ai dispositivi non gestiti.|Etichetta di riservatezza usata per classificare il team e controllare la condivisione guest e l'accesso ai dispositivi non gestiti. L'etichetta può essere usata anche sui file per crittografare i file.|

Una variante dell'opzione Altamente sensibili, i [Team con isolamento di sicurezza](secure-teams-security-isolation.md), usa un'etichetta di riservatezza univoca per team, che fornisce ulteriore sicurezza. È possibile usare questa etichetta per crittografare i file e solo i membri del team potranno leggerli.

La protezione di base include team pubblici e privati. I team pubblici possono essere individuati e usati da chiunque nell'organizzazione. I team privati possono essere individuati e usati solo dai membri del team. Entrambe le configurazioni limitano la condivisione del sito di SharePoint associato ai proprietari del team, per facilitare la gestione delle autorizzazioni.

I team per la protezione dei dati sensibili e altamente sensibili sono team privati, in cui la condivisione e le richieste di accesso per il sito associato sono limitate e vengono usate etichette di riservatezza per impostare i criteri relativi alla condivisione guest, all'accesso ai dispositivi e alla crittografia del contenuto.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Nei livelli dei dati sensibili e altamente sensibili vengono usate etichette di riservatezza per proteggere il team e i file associati. Per implementare questi livelli, è necessario abilitare le [etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Office 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Anche se il livello di base non richiede l'uso di etichette di riservatezza, è consigliabile creare un'etichetta "generale" e quindi richiedere che tutti i team vengano etichettati. Questo contribuirà a garantire che gli utenti facciano una scelta consapevole in merito alla riservatezza quando creano un team. Se si prevede di distribuire il livello dei dati sensibili o altamente sensibili, è consigliabile creare un'etichetta "generale" che possa essere usata per i team di base e per i file non riservati.

Se non si ha familiarità con le etichette di riservatezza, è consigliabile leggere [Iniziare a usare le etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) per iniziare. 

Se nell'organizzazione sono già state distribuite etichette di riservatezza, valutare il modo in cui le etichette usate nei livelli dei dati sensibili e altamente sensibili si inseriscono nella strategia di etichettatura complessiva. 

## <a name="sharing-the-sharepoint-site"></a>Condivisione del sito di SharePoint

Ogni team ha un sito di SharePoint associato in cui sono archiviati i documenti. In un canale di Teams, corrisponde alla scheda **File**. Il sito di SharePoint conserva una gestione delle autorizzazioni autonoma, ma è collegato alle autorizzazioni del team. I proprietari del team sono inclusi come proprietari del sito e i membri del team sono inclusi come membri del sito nel sito associato.

Le autorizzazioni risultanti consentono:

- Ai proprietari del team di amministrare il sito e avere il controllo completo sul contenuto del sito.
- Ai membri del team di creare e modificare i file nel sito. 

Per impostazione predefinita, i proprietari e i membri del team possono condividere il sito con utenti esterni al team senza aggiungerli al team. Questo è sconsigliato perché complica la gestione degli utenti, inoltre utenti che non sono membri del team potrebbero accedere ai file del team senza che i proprietari ne siano consapevoli. Per evitarlo, a partire dal livello protezione di base, è consigliabile permettere solo ai proprietari di condividere direttamente il sito.

Mentre non è disponibile un'opzione di autorizzazione di sola lettura per i team, lo è per il sito di SharePoint. Se sono presenti stakeholder o gruppi di partner che devono essere in grado di visualizzare i file del team, ma non di modificarli, può essere utile aggiungerli direttamente al sito di SharePoint con autorizzazioni di lettura.

## <a name="sharing-files-and-folders"></a>Condivisione di file e cartelle

Per impostazione predefinita, sia i proprietari che i membri del team possono condividere file e cartelle con persone esterne al team. Questo può includere persone esterne all'organizzazione, se si è consentita la condivisione guest. In tutti e tre i livelli, il tipo di collegamento di condivisione predefinito viene aggiornato per evitare la condivisione accidentale. Nel livello dei dati altamente sensibili, la condivisione è limitata ai soli proprietari del team.

## <a name="guest-sharing"></a>Condivisione con gli utenti guest

Se è necessario collaborare con persone esterne all'organizzazione, si consiglia di configurare l'[integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) per un'esperienza di condivisione e amministrazione ottimale.

La condivisione con gli utenti guest in Teams è disattivata per impostazione predefinita, anche se la condivisione per i gruppi di Office 365 (in cui è archiviato l'appartenenza al team) e SharePoint è attivata. Nel livello di base la condivisione di Teams viene attivata. Se necessario, è possibile disattivarla nei livelli dei dati sensibili e altamente sensibili usando un'etichetta di riservatezza.

L'etichetta di riservatezza influisce solo sulla condivisione guest per il team. Le impostazioni di condivisione guest per il sito di SharePoint associato sono controllate separatamente ed è necessario allineare le due impostazioni per i livelli dei dati sensibili e altamente sensibili.

Nel livello dei dati altamente sensibili, l'etichetta di riservatezza viene configurata in modo da crittografare i file a cui è applicata. Se si vuole che gli utenti guest abbiano accesso a questi file, è necessario assegnare loro le autorizzazioni quando si crea l'etichetta.

È consigliabile lasciare attivata la condivisione guest per il livello di previsione e per i livelli dei dati sensibili e altamente sensibili se occorre collaborare con persone esterne all'organizzazione. Le funzionalità di condivisione guest di Microsoft 365 offrono un'esperienza di condivisione più sicura e regolamentabile rispetto all'invio di file come allegati nei messaggi di posta elettronica. Inoltre, riduce il rischio di casi di "shadow IT" in cui gli utenti usano prodotti consumer non gestiti per la condivisione con collaboratori esterni legittimi.

Vedere i riferimenti seguenti per creare un ambiente di condivisione guest sicuro e produttivo per l'organizzazione:

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)
- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](share-limit-accidental-exposure.md)
- [Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Accesso da dispositivi non gestiti

Per i livelli dei dati sensibili e altamente sensibili, l'accesso al contenuto di SharePoint viene limitato mediante l'applicazione di etichette di riservatezza. L'accesso condizionale di Azure Active Directory offre numerose opzioni per determinare il modo in cui gli utenti accedono a Microsoft 365, incluse limitazioni basate su luogo, rischio, conformità dei dispositivi e altri fattori. Si consiglia di leggere l'articolo [Informazioni sull'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) e valutare quali altri criteri potrebbero essere appropriati per l'organizzazione.

## <a name="next-step"></a>Passaggio successivo

Per iniziare, [configurare il livello di protezione di base](configure-teams-baseline-protection.md). Se necessario, è possibile aggiungere la [protezione dei dati sensibili](configure-teams-sensitive-protection.md) e la [protezione dei dati altamente sensibili](configure-teams-highly-sensitive-protection.md) al livello di protezione di base.

## <a name="see-also"></a>Vedere anche

[Sicurezza e conformità in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Criteri di avviso nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
