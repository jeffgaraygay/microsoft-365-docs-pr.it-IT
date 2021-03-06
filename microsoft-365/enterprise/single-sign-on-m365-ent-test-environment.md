---
title: Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685773"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Azure AD Seamless Single Sign-On consente agli utenti di eseguire l'accesso automaticamente quando utilizzano il proprio PC o i dispositivi connessi alla rete aziendale. Azure AD Seamless Single Sign-On permette agli utenti di accedere facilmente alle applicazioni basate sul cloud senza usare componenti aggiuntivi in locale.

In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per Azure AD Seamless SSO.

Esistono due fasi per la configurazione:

1.    Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.
2.    Configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On.
    
![Guide del laboratorio di testing per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On

In questa fase, si configura Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On e se ne verifica il funzionamento.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurare Azure AD Connect su APP1

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.

2. Dal desktop di APP1, eseguire Azure AD Connect.

3. Nella **Pagina di benvenuto** fare clic su **Configura**.

4. Nella pagina **Attività aggiuntive** fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.

5. Nella pagina **Connessione ad Azure AD** digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.

6. Nella pagina **Accesso utente**, selezionare **Abilita Single Sign-On**, quindi fare clic su **Avanti**.

7. Nella pagina **Abilita Single Sign-On**, fare clic su **Immetti credenziali**.

8. Nella finestra di dialogo **Sicurezza di Windows**, digitare **user1** e la password dell'account user1, quindi fare clic su **OK**. Poi, fare clic su **Avanti**.

9. Nella pagina **Pronto per la configurazione** fare clic su **Configura**.

10. Nella pagina **Configurazione completata**, fare clic su **Esci**.

11. Dal portale di Azure, nel riquadro sinistro fare clic su **Azure Active Directory > Azure AD Connect**. Verificare che la funzionalità **Accesso Single Sign-On facile** venga visualizzata come **Attivata**.

Successivamente, verificare la possibilità di accedere all'abbonamento con il <strong>User1@testlab.</strong>\<your public domain> per l’account User1.

1. Da Internet Explorer su AAP1, fare clic sull'icona delle impostazioni, quindi fare clic su **Opzioni Internet**.
 
2. In **Opzioni Internet**, fare clic sulla scheda **Sicurezza**.

3. Fare clic su **Intranet locale**, quindi su **Siti**.

4. In **Intranet locale**, fare clic su **Avanzate**.

5. In **Aggiungi questo sito Web alla zona**, digitare **https<span>://</span>autologon.microsoftazuread-sso.com**, quindi fare clic su **Aggiungi > Chiudi > OK > OK**.

6. Disconnettersi e quindi accedere nuovamente specificando un account diverso.

7. Quando viene richiesto di eseguire l'accesso, specificare <strong>User1@testlab.</strong>\<your public domain> nome e quindi fare clic su **Avanti**. È quindi possibile accedere come User1 senza che venga richiesta una password. Ciò dimostra che Seamless SSO funziona correttamente.

Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB di Active Directory Domain Services, non è un amministratore globale per Azure AD. Di conseguenza, l'icona **Amministratore** non sarà visibile.

Di seguito è riportata la configurazione risultante:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS testlab.\<your domain name> registrato.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services. 
- Azure AD Seamless SSO viene abilitato in modo che i computer sulla rete Intranet simulata possano accedere alle risorse cloud di Microsoft 365 senza specificare una password per l'account utente.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)


