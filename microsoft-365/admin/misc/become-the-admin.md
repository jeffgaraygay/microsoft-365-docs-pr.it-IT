---
title: Eseguire l'acquisizione di un amministratore interno
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Informazioni su come verificare la posta elettronica e la proprietà del dominio in modo da assumere un tenant non gestito in Microsoft 365
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814469"
---
# <a name="perform-an-internal-admin-takeover"></a>Eseguire l'acquisizione di un amministratore interno

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 

Se si è un amministratore e si vuole assumere un tenant non gestito creato da un utente in modalità self-service, è possibile eseguire questa operazione con l'acquisizione di un amministratore interno.

> [!NOTE]
> Una registrazione in modalità self-service per qualsiasi servizio cloud che utilizza Azure AD aggiunge l'utente a una directory di Azure AD non gestita o "Shadow" e crea un tenant non gestito. Un tenant non gestito è una directory senza un amministratore globale. Per determinare se un tenant è gestito o non gestito, vedere determinare il [tipo di tenant](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Passaggio 1: verificare l'indirizzo di posta elettronica

> [!NOTE]
> Se il servizio self-service è abilitato nel tenant, gli utenti possono iscriversi a servizi gratuiti, ad esempio Power BI, per conto proprio. In questa procedura si presuppone che la sottoscrizione di un utente in modalità self-service abbia creato il tenant non gestito che si desidera sottoporre a amministratore. Nel primo passaggio viene creato un contesto utente nel tenant non gestito, utilizzando Power BI per illustrare il percorso di acquisizione dell'amministratore.

1. Per iscriversi a Power bi, passare al [sito Power bi](https://powerbi.com) e selezionare **Avvia**versione di valutazione gratuita di avvio gratuito  >  **Start free trial** (in Condividi con Power bi Pro box). 

2. Iscriversi con un account utente che utilizza il nome di dominio dell'organizzazione (come `powerbiadmin@contoso.com` ). Se l'account è già in uso, accedere utilizzando la password corrente.

3. Controllare la posta elettronica per il **codice di verifica** e immettere il codice per convalidare l'indirizzo di posta elettronica.
    
## <a name="step-2-create-a-new-account"></a>Passaggio 2: creare un nuovo account

1. Quando si immette il codice di verifica, viene visualizzata una pagina in cui è possibile creare un nuovo account. 
    
2. Inserire i campi nome utente e password con l'account che si desidera utilizzare, quindi selezionare **Avvia**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Passaggio 3: verificare la proprietà del dominio e divenire l'amministratore

1. Verrà aperta la procedura guidata di **amministratore** . Se la procedura guidata non viene avviata, cercare il riquadro **amministratore** e selezionarlo. 

2. Selezionare **Sì, voglio essere l'amministratore**.

3. Verificare di essere proprietari del dominio di cui si desidera eseguire l'aggiunta di un record TXT al registrar. La procedura guidata fornirà il record TXT da aggiungere, oltre a fornire un collegamento al sito Web del registrar e un collegamento a istruzioni dettagliate.
    
4. Dopo aver aggiunto il record TXT al sito di registrazione, tornare alla procedura guidata e selezionare **OK, ho aggiunto il record**.
    
> [!NOTE]
> La presa in considerazione del tenant shadow non avrà alcun impatto sulle informazioni o sui servizi esistenti. Tuttavia, se gli utenti del dominio hanno effettuato l'iscrizione per i servizi che richiedono una licenza, ti verrà richiesto di acquistare licenze per il ruolo di amministratore. Dopo aver completato il processo di configurazione dell'amministratore, è possibile acquistare o rimuovere licenze.
  
## <a name="related-articles"></a>Articoli correlati

YouTube: [3 passaggi per eseguire l'acquisizione di un amministratore IT per Power bi e Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Acquisizione dell'amministratore in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Uso dell'iscrizione self-service nell'organizzazione](self-service-sign-up.md)
  
[Informazioni sul ruolo di amministratore del servizio Power BI](https://docs.microsoft.com/power-bi/service-admin-role)

