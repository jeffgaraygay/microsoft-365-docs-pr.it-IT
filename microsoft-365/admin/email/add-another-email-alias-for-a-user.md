---
title: Aggiungere un altro alias di posta elettronica per un utente
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Informazioni su come è possibile disporre di più indirizzi di posta elettronica, denominati alias di posta elettronica, associati all'account Microsoft 365 for business. "
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080016"
---
# <a name="add-another-email-alias-for-a-user"></a>Aggiungere un altro alias di posta elettronica per un utente

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Questo articolo è per gli amministratori di Microsoft 365 che dispongono di sottoscrizioni aziendali. Non è destinato agli utenti privati.
  
Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica a cui è stato assegnato un utente quando è stato creato l'account. Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica. Possono anche avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 for business. Questi indirizzi aggiuntivi sono detti alias. 
  
Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma desidera anche ricevere messaggi di posta elettronica in jen@contosoco.com perché alcune persone si riferiscono a lei con quel nome. È possibile creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano alla posta in arrivo di Jenna.
<br><br>  
  
È possibile creare fino a 400 alias per utente. Non sono previsti ulteriori costi o licenze.
  
> [!Tip]
> Se si desidera che più persone gestiscano la posta elettronica inviata a un singolo indirizzo di posta elettronica, come info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa. Per ulteriori informazioni, vedere [creare una cassetta postale condivisa](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Aggiungere alias di posta elettronica a un utente
<a name="AddEmailPreview"> </a>

Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](../add-users/about-admin-roles.md) . 

  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **utenti attivi** selezionare l'utente > gestire gli **alias di posta elettronica**. Questa opzione non viene visualizzata se alla persona non è stata assegnata una licenza. 
    
3. Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.   
    
    > [!Important] 
    > Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
    
  
    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 
  
     
5. Al termine, scegliere **Save Changes**.
    
6. Attendere 24 ore affinché i nuovi alias vengano inseriti in Microsoft 365.
    
    L'utente avrà ora un indirizzo primario e un alias. Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.** Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>. 
    
    
2. Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.

3. Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.

    > [!Important] 
    > Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.

4. Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica. Se è stato aggiunto il proprio dominio a Microsoft 365, è possibile scegliere il dominio per il nuovo alias di posta elettronica utilizzando l'elenco a discesa. Selezionare **Aggiungi**.

    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Al termine, seleziona **Salva**.

6. Attendere 24 ore affinché i nuovi alias vengano inseriti in Microsoft 365. 
    
    L'utente avrà ora un indirizzo primario e un alias. Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.** Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

    
2. Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.

3. Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.

    > [!Important] 
    > Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.

4. Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica. Se è stato aggiunto il proprio dominio a Microsoft 365, è possibile scegliere il dominio per il nuovo alias di posta elettronica utilizzando l'elenco a discesa. Selezionare **Aggiungi**.

    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Al termine, seleziona **Salva**.

6. Attendere 24 ore affinché i nuovi alias vengano inseriti in Microsoft 365. 
    
    L'utente avrà ora un indirizzo primario e un alias. Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.** Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>È stato visualizzato "non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses"?


Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses**" significa che è necessario un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>L'abbonamento è stato acquistato presso GoDaddy o un altro partner?


Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.
  
## <a name="related-articles"></a>Articoli correlati

[Inviare un messaggio di posta elettronica da un indirizzo diverso](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Cambiare un nome utente e un indirizzo di posta elettronica](../add-users/change-a-user-name-and-email-address.md)
  

