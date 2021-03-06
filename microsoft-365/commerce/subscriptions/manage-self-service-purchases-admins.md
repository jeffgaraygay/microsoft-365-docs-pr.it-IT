---
title: Gestire gli acquisti in modalità self-service (amministratori)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Gli amministratori possono imparare a gestire gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione.
ms.openlocfilehash: 562e0e26d9ca7d10d71a46b8cf2d87c487c1b529
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403271"
---
# <a name="manage-self-service-purchases-admin"></a>Gestire acquisti in modalità self-service (amministratore)

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Come amministratore, è possibile visualizzare gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione. È possibile visualizzare il prodotto, il nome dell'acquirente, gli abbonamenti acquistati, la data di scadenza, il prezzo di acquisto e gli utenti assegnati per ogni acquisto in modalità self-service. Se necessario per l'organizzazione, è possibile disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Si dispone degli stessi criteri di gestione dei dati e di accesso rispetto ai prodotti acquistati tramite l'acquisto in modalità self-service o in modo centralizzato.

È inoltre possibile controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visualizzare le sottoscrizioni in modalità self-service

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .

2. Accanto a **risultati di affinamento**, dall'elenco a discesa **tipo di account** scegliere **self-service**.

3. Per visualizzare ulteriori dettagli su un abbonamento, selezionarne uno dall'elenco.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visualizzazione delle licenze per un abbonamento all'acquisto in modalità self-service

1. Nell'interfaccia di amministrazione, andare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.

2. Scegliere l'icona filtro e quindi fare clic su **self-service**.

3. Selezionare un prodotto per visualizzare le licenze assegnate agli utenti.

    > [!NOTE]
    > Se per un prodotto sono presenti più acquisti, tale prodotto è elencato solo una volta e la colonna **quantità disponibile** indica il totale di tutte le sottoscrizioni acquistate per il prodotto.

4. L'elenco **utenti** è raggruppato in base ai nomi delle persone che hanno effettuato acquisti in modalità self-service.

5. Per esportare un elenco di utenti con licenze per le sottoscrizioni, scegliere gli abbonamenti che si desidera esportare, quindi scegliere **Esporta utenti**.

## <a name="disable-or-enable-self-service-purchases"></a>Disabilitare o abilitare gli acquisti in modalità self-service

È possibile disabilitare o abilitare l'acquisto in modalità self-service per gli utenti dell'organizzazione. Il modulo di **MSCommerce** PowerShell include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service e per quali prodotti.

È possibile utilizzare il modulo di **MSCommerce** PowerShell per:

- Visualizzare lo stato predefinito del valore **AllowSelfServicePurchase** del parametro AllowSelfServicePurchase &mdash; se è abilitato o disabilitato per prodotto
- Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato
- Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo

Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizzare le licenze in un singolo abbonamento

È possibile assegnare licenze esistenti o acquistare abbonamenti aggiuntivi mediante contratti esistenti per gli utenti assegnati agli acquisti in modalità self-service. Dopo aver assegnato le licenze acquistate in modo centralizzato, è possibile richiedere che gli acquirenti cancellino le sottoscrizioni esistenti.

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a> con l'account di amministratore globale o amministratore di fatturazione.

2. Passare alla pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servizi di acquisto</a> per la fatturazione.

3. Trovare e scegliere il prodotto che si desidera acquistare, quindi scegliere **buy**.

4. Completare i passaggi rimanenti per completare l'acquisto.

5. Seguire la procedura illustrata [per l'](#view-who-has-licenses-for-a-self-service-purchase-subscription) esportazione di un elenco di utenti a cui fare riferimento nel passaggio 6.

6. Assegnare le licenze a tutti gli utenti che dispongono di una licenza nell'altra sottoscrizione. Per i passaggi completi, vedere [assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).

7. Contattare la persona che ha acquistato l'abbonamento all'acquisto in modalità self-service e chiedergli di annullarla.

## <a name="need-help-contact-us"></a>Serve assistenza? Contattaci.

Per domande comuni sugli acquisti in modalità self-service, vedere domande [frequenti sugli acquisti in modalità self-service](self-service-purchase-faq.md).

Se hai domande o hai bisogno di assistenza per gli acquisti in modalità self-service, [Contatta il supporto](../../admin/contact-support-for-business-products.md).
