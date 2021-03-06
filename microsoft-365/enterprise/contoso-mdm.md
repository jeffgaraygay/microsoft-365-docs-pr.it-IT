---
title: Gestione dispositivi mobili in Contoso
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
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sul modo in cui Contoso utilizza Microsoft Intune in Microsoft 365 per l'organizzazione per gestire i propri dispositivi e le app in esecuzione su di essi.
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685843"
---
# <a name="mobile-device-management-for-contoso"></a>Gestione dispositivi mobili in Contoso

Microsoft 365 per Enterprise include Intune e un set di servizi di Azure per supportare la gestione e la sicurezza di dispositivi mobili e applicazioni.

Contoso ha molti dipendenti autorizzati alla mobilità, di cui alcuni hanno uffici nelle sedi di Contoso e altri non hanno un ufficio. Contoso era alla ricerca di un modo per garantire la produttività dei dipendenti mantenendo sicuri i dispositivi, i dati di Contoso archiviati in quei dispositivi e il comportamento dell’applicazione.

## <a name="plan"></a>Piano

All'inizio dell'analisi della gestione dei dispositivi mobili per Microsoft 365 per Enterprise, Contoso ha identificato i seguenti casi di utilizzo di Intune:

- Proteggere i dati e la posta elettronica di Exchange Online in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili
- Implementare un programma Bring Your Own Device (BYOD) per i dipendenti di Contoso
- Distribuire ai dipendenti di Contoso telefoni di proprietà dell’organizzazione e tablet condivisi dall’uso limitato

Contoso non usa Intune per:

- Consentire ai dipendenti di accedere in modo sicuro a Microsoft 365 da un chiosco pubblico non gestito
- Proteggere i dati e la posta elettronica locale così da poter accedervi in modo sicuro dai dispositivi mobili, perché non sono più presenti server locali di Microsoft Exchange.

## <a name="deploy"></a>Distribuzione

Ecco come Contoso ha configurato l’infrastruttura di gestione dei dispositivi mobili:

- Ha impostato Intune come autorità di gestione dei dispositivi mobili (MDM) e usa Intune in Azure per amministrare il contenuto e gestire i dispositivi
- Ha creato gruppi di Azure AD per i dispositivi per la registrazione e le impostazioni di Intune e i criteri di accesso condizionale basati sul dispositivo

  Per altre informazioni, vedere [Criteri di accesso condizionale di Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Ha abilitato la piattaforma per dispositivi Apple per supportare i dipendenti con iPad, iMac, iPhone e telefoni aziendali basati su iPhone
- Ha creato criteri di termini e condizioni specifichi per Contoso, visualizzati durante l’installazione del Portale aziendale per i dispositivi mobili di Contoso
- Per i dispositivi non registrati, un set di criteri di gestione delle applicazioni mobili (MAM) per richiedere l'autenticazione per l'accesso ai servizi di Microsoft 365
- Ha creato criteri di Intune che garantiscono:
  - App consentite
  - Crittografia dei dispositivi per evitare l'accesso non autorizzato
  - Un PIN a sei cifre o una password
  - Un periodo di timout di inattività
  - Protezione antivirus e malware e gli aggiornamenti delle firme con Windows Defender nei dispositivi Windows 10
  - Aggiornamenti automatici nei dispositivi Windows 10 che includono gli aggiornamenti di sicurezza più recenti
  - Trasferimento dei certificati ai dispositivi gestiti
  - Una chiara separazione dei dati personali e aziendali. Gli utenti o amministratori possono cancellare in modo selettivo i dati aziendali dal dispositivo, senza modificare i dati personali, ad esempio immagini, account di posta elettronica personale e file personali.

Dopo la distribuzione, Contoso ha registrato PC e smartphone e tablet di proprietà aziendale, aggiungendoli ai gruppi di dispositivi Intune appropriati, e ha distribuito un programma BYOD che consente ai dipendenti di registrare i loro dispositivi personali. I dispositivi registrati hanno ricevuto i criteri Intune, diventando di conseguenza dispositivi e relative applicazioni gestiti e protetti. I dispositivi non registrati dispongono di criteri di gestione delle applicazioni mobili (MAM) che specificano le applicazioni consentite.

Ecco l'architettura di distribuzione di Gestione dispositivi mobili di Contoso.

![Infrastruttura di distribuzione di Gestione dispositivi mobili di Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Passaggio successivo

[Scopri](contoso-info-protect.md) come Contoso utilizza le funzionalità di protezione delle informazioni di Microsoft 365 per l'organizzazione per classificare, identificare e proteggere le risorse digitali cruciali all'interno della propria azienda.

## <a name="see-also"></a>Vedere anche

[Gestione dei dispositivi per Microsoft 365](device-management-roadmap-microsoft-365.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)

