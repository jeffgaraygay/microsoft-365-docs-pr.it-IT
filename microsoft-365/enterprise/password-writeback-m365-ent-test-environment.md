---
title: Writeback della password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: "Riepilogo: configurare il writeback della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: b8c89ca7ef967c423b89db4559ef04f715a5f869
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686227"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Writeback della password per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

Con il writeback delle password, gli utenti possono aggiornare le password tramite Azure Active Directory (Azure AD) e la modifica verrà replicata nell'istanza locale di Active Directory Domain Services (AD DS). Grazie al writeback delle password gli utenti non devono aggiornare le password tramite l'istanza locale di AD DS in cui sono archiviati gli account utente originali. Questa funzione è utile per gli utenti che lavorano da remoto o in roaming e non dispongono di una connessione di accesso remoto alla rete locale.

In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per il writeback delle password.

Esistono due fasi per la configurazione:

1.    Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.
2.    Abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.
    
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Prima di tutto, seguire le istruzioni riportate in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.

Per iniziare, configurare l'account utente 1 con il ruolo amministratore globale.

1. Dall’[Interfaccia di amministrazione di Microsoft 365](https://portal.microsoft.com), accedere con l'account di amministratore globale.

2. Fare clic su **Utenti attivi**.
 
3. Nella pagina **Utenti attivi**, fare clic sull’account **Utente1**,

4. Nel riquadro **Utente1**, fare clic su **Modifica** accanto a **Ruoli**.

5. Nel riquadro **Modifica ruoli utente** per utente1, fare clic su **Amministratore globale**. Fare clic su **Salva** e quindi su **Chiudi**.

Quindi, configurare l'account Utente 1 con le impostazioni di sicurezza che gli consentono di cambiare le password per conto di altri utenti nel dominio TESTLAB Active Directory Domain Services.

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\Utente1.

2.  Dal desktop di APP1, fare clic su **Inizio**, digitare **attivo**, quindi fare clic su **Utenti e computer di Active Directory**.

3. Fare clic su **Visualizza** nella barra dei menu. Se l’opzione **Funzionalità avanzate** non è attiva, fare clic per abilitarla.

4. Nel riquadro della struttura, fare clic con il pulsante destro del mouse sul dominio, fare clic su **Proprietà** e quindi sulla scheda **Protezione**.

5. Fare clic su **Avanzate**.

6. Nella scheda **Autorizzazioni**, fare clic su **Aggiungi**.

7. Fare clic su **Seleziona un'entità**, digitare **Utente1**, quindi fare clic su **OK**.

8. In **Si applica a**, selezionare **Oggetti utente discendenti**.

9. In **Autorizzazioni**, selezionare le opzioni seguenti:

    - Cambiare la password
    - Reimpostare la password

10. In **Proprietà**, selezionare le opzioni seguenti:
    - Scrittura lockoutTime
    - Scrittura pwdLastSet

11. Fare clic su **OK** tre volte per salvare le modifiche.

12. Chiudere **Utenti e computer di Active Directory**.

Successivamente, configurare Azure AD Connect su APP1 per il writeback delle password.

1. Se necessario, connettersi ad APP1 con l'account TESTLAB\Utente1.

2. Dal desktop di APP1, fare doppio clic su **Azure AD Connect**.

3. Nella **Pagina di benvenuto** fare clic su **Configura**.

4. Nella pagina **Attività aggiuntive**, fare clic su **Personalizza le opzioni di sincronizzazione**, quindi fare clic su **Avanti**.

5. Nella pagina **Connessione ad Azure AD** digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.

6. Nelle pagine **Connessione delle directory** e **Filtro di domini/unità organizzative**, fare clic su **Avanti**.

7. Nella pagina **Funzionalità facoltative** selezionare **Writeback password** e fare clic su **Avanti**. 

8. Nella pagina **Pronto per la configurazione**, fare clic su **Configura** e attendere il completamento del processo.

9. Quando viene visualizzata la fine della configurazione, fare clic su **Esci**.

È ora possibile testare il writeback delle password per gli utenti in computer non connessi alla rete virtuale della rete intranet simulata.

Di seguito è riportata la configurazione risultante:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS TESTLAB.\<your domain name> registrato.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services. 
- Il writeback delle password è abilitato in modo che gli utenti possono modificare la password tramite Azure AD senza dover essere connessi alla rete intranet semplificata.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)


