---
title: Ripristinare un utente
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Informazioni su come ripristinare gli account utente eliminati e tutti i dati associati.
ms.openlocfilehash: 27b3f4a0077b5ef0dcfaef1dbe5019a5d69652f2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387004"
---
# <a name="restore-a-user"></a>Ripristinare un utente

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
   
Se si ripristina un account utente entro 30 giorni dalla sua eliminazione, vengono ripristinati l'account stesso e tutti i dati associati. L'utente può accedere con lo stesso account aziendale o dell'istituto di istruzione. La cassetta postale dell'utente verrà completamente ripristinata. Per scoprire quanto tempo rimane prima che non sia più possibile ripristinare un account utente specifico, [contattare il supporto tecnico](../contact-support-for-business-products.md).
  
Ecco un paio di suggerimenti:
  
- Assicurarsi che le licenze siano disponibili per l'assegnazione dell'account.
    
- Se l'azienda usa Active Directory, vedere [Risoluzione dei problemi relativi agli account utente eliminati in Office 365](https://support.microsoft.com/kb/2619308) per istruzioni sul ripristino di un account utente. 
    
## <a name="restore-one-or-more-user-accounts"></a>Ripristinare uno o più account utente

Per eseguire questa procedura è necessario essere un amministratore globale di Microsoft 365 o un amministratore di gestione utenti. 
  
 
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina utenti **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.

::: moniker-end

::: moniker range="o365-germany"

1. Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

2. Nella pagina **utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi fare clic su **Ripristina**.
    
 
3. Seguire le istruzioni visualizzate per impostare la password, quindi selezionare **Ripristina**.
    
4. Se l'utente è stato ripristinato correttamente, selezionare **Invia messaggio di posta elettronica e Chiudi**. Se si riscontra un conflitto tra nomi o indirizzi proxy, vedere le istruzioni di seguito per ripristinare questi account.
    
Dopo aver ripristinato un utente, verificare di aver informato che la password è stata modificata e che è stato eseguito il follow-up.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Ripristinare un utente con conflitto relativo al nome utente
<a name="RestoreUserNameConflict"> </a>

I conflitti relativi al nome utente si verificano quando l'amministratore elimina un account utente, ne crea uno nuovo con lo stesso nome utente (per lo stesso utente o per un altro utente con nome simile) e successivamente cerca di ripristinare l'account eliminato.
  
Per risolvere i conflitti di questo tipo, sostituire l'account utente attivo con quello da ripristinare oppure assegnare un altro nome utente a quest'ultimo account, in modo da evitare che esistano due account con lo stesso nome utente. Ecco come fare.
  

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina utenti **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.

::: moniker-end

::: moniker range="o365-germany"

1. Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

  
2. Nella pagina **utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi fare clic su **Ripristina**.
    
    > [!NOTE]
    > Se non si riesce a ripristinare due o più utenti, verrà visualizzato un messaggio di errore che comunica che l'operazione di ripristino non è riuscita per alcuni utenti. Per sapere quali utenti non sono stati ripristinati, visualizzare il log. Gli account che non è stato possibile ripristinare dovranno essere ripristinati uno alla volta. 
  
3. Seguire le istruzioni visualizzate per impostare la password e selezionare **Ripristina**.
    
4. Un messaggio popup informa che si è verificato un problema durante il ripristino dell'account. Eseguire una delle operazioni seguenti:
    
  - Annullare il ripristino e rinominare l'utente attivo corrente. Provare quindi a eseguire di nuovo il ripristino.
    
  - In alternativa, digitare un nuovo indirizzo di posta elettronica principale per l'utente e selezionare **Ripristina**.
    
5. Esaminare i risultati e quindi scegliere **Chiudi**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Ripristinare un utente che ha un conflitto tra indirizzi proxy

I conflitti relativi all'indirizzo proxy si verificano quando l'amministratore elimina un account utente contenente un indirizzo proxy, assegna lo stesso indirizzo proxy a un altro account, quindi cerca di ripristinare l'account eliminato. Eseguire la procedura seguente per risolvere il problema.
  
Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](about-admin-roles.md) in Microsoft 365. 
  

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina utenti **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.

::: moniker-end

::: moniker range="o365-germany"

Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.

::: moniker-end

2. Nella pagina **Utenti eliminati** selezionare l'utente da ripristinare e quindi scegliere **Ripristina**. 
    
3. Nella pagina **Ripristina** , seguire le istruzioni per impostare la password e selezionare **Ripristina**. Gli eventuali indirizzi proxy in conflitto vengono rimossi automaticamente dall'utente che si sta ripristinando.
    
4. Esaminare i risultati e quindi scegliere **Chiudi**.

## <a name="related-articles"></a>Articoli correlati

[Eliminare un utente](delete-a-user.md)
  
