---
title: Gestire i profili di fatturazione
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
keywords: Profilo di fatturazione, fatture, addebiti, spese gestite
ms.openlocfilehash: bd963ff993a064615f0f7ad06c8f2cc5c3401ad2
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646437"
---
# <a name="manage-billing-profiles"></a>Gestire i profili di fatturazione
Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare gli elementi inclusi nella fattura e come vengono pagate le fatture.

I profili di fatturazione includono le informazioni seguenti:

- Nome **account** &mdash; di fatturazione dell'account di fatturazione a cui è associato il profilo
- **Metodi** &mdash; di pagamento carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario
- Indirizzo di fatturazione **delle informazioni** &mdash; di contatto e nome del contatto
- Le **Impostazioni** &mdash; delle fatture valutano in base al paese dell'account di fatturazione, un numero di ordine facoltativo e l'opzione per la ricezione delle fatture come allegati di posta elettronica
- Autorizzazioni per le **autorizzazioni** &mdash; che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare gli acquisti

Utilizzare i profili di fatturazione per controllare gli acquisti e personalizzare la fattura. Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione. È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica.

Un profilo di fatturazione viene creato automaticamente per l'account di fatturazione durante il primo acquisto. È possibile creare profili di fatturazione nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> per configurare altre fatture. Ad esempio, è possibile utilizzare diversi profili di fatturazione quando si effettuano acquisti per ogni reparto dell'organizzazione. Alla data di fatturazione successiva, si riceverà una fattura per ogni profilo di fatturazione.

## <a name="billing-profile-roles"></a>Ruoli del profilo di fatturazione

I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture. Assegnare questi ruoli agli utenti che registrano, organizzano e pagano fatture, come i membri del team di approvvigionamento nell'organizzazione.

| Ruolo                          | Descrizione                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Proprietario del profilo di fatturazione         | Gestire tutti gli elementi per un profilo di fatturazione                                           |
| Collaboratore del profilo di fatturazione   | Gestire tutto tranne le autorizzazioni in un profilo di fatturazione                         |
| Lettore profili di fatturazione        | Visualizzazione di sola lettura di tutto in un profilo di fatturazione                                 |
| Responsabile fatturazione               | Visualizzare e pagare le bollette e dispone di una visualizzazione di sola lettura di tutto in un profilo di fatturazione   |

## <a name="view-billing-profiles"></a>Visualizzare i profili di fatturazione

1. Nell'interfaccia di amministrazione, **andare alla** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">fatture & pagamenti</a> .

2. Scegliere **profili di fatturazione**e quindi scegliere un profilo di fatturazione dall'elenco.

    - Nella scheda **Panoramica** , è possibile modificare i dettagli del profilo di fatturazione e abilitare o disabilitare l'invio di una fattura tramite posta elettronica.

    - Nella scheda **autorizzazioni** , è possibile assegnare i ruoli agli utenti per pagare le fatture.

    - Nella scheda **bilanciamento del credito di Azure** , i clienti di Azure possono visualizzare la cronologia degli equilibri delle transazioni per i crediti di Azure utilizzati dal profilo di fatturazione.

    - Nella scheda **crediti** di Azure, i clienti di Azure possono visualizzare un elenco di crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.

    > [!NOTE]
    > Se non si dispone di alcun credito di Azure, non verranno visualizzate le schede Azure credit **Balance** o **Azure Credits** .

## <a name="need-help-contact-support"></a>Serve assistenza? Contattare il supporto.

Se hai domande o hai bisogno di assistenza con i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.

Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [Contatta il supporto per i prodotti per le aziende](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products).