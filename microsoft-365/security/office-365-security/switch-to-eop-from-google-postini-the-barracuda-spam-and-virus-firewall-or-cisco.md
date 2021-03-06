---
title: Passare a EOP da un altro servizio di protezione
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni su come passare a Exchange Online Protection (EOP) da un dispositivo di igiene della posta elettronica locale o da un servizio di protezione basato sul cloud.
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827798"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Passaggio a Exchange Online Protection da Google Postini, Barracuda Spam e Virus Firewall o Cisco IronPort

 Lo scopo di questo argomento è quello di aiutare l'utente a comprendere il processo per passare a Exchange Online Protection (EOP) da un'applicazione per l'igiene della posta elettronica locale o un servizio di protezione basato su cloud, nonché di fornire risorse per iniziare. Esistono diverse soluzioni per il filtro da posta indesiderata, ma il processo per il passaggio a EOP nella maggior parte dei casi è analogo.

Se si è nuovi di EOP e si desidera leggere una panoramica delle sue caratteristiche prima di decidere di cambiare, iniziare con l'argomento [Overview di Exchange Online Protection](exchange-online-protection-overview.md) .

Prima di effettuare il passaggio a EOP, è importante considerare se ospitare le cassette postali protette da EOP nel cloud, con Exchange Online, in locale o in uno scenario ibrido. Ibrido significa che alcune cassette postali sono locali e altre sono ospitate su Exchange Online. Ciascuno di questi scenari di hosting: cloud, locale, ibrido è possibile. Tuttavia la procedura di impostazione può variare. Di seguito sono riportate alcune considerazioni che faciliteranno l'utente nella scelta della distribuzione appropriata:

- **Protezione EOP con cassette postali locali**: questo scenario è appropriato se si dispone di un'infrastruttura di hosting della posta che si desidera utilizzare oppure se si dispone di requisiti aziendali per mantenere le cassette postali in locale e si desidera utilizzare EOP come protezione della posta elettronica basata sul cloud. [Passare a EOP autonomo](#switch-to-eop-standalone) descrive lo scenario in maggiore dettaglio.

- **Protezione EOP con cassette postali di Exchange Online**: questo scenario è appropriato se si desidera che la protezione di EOP e tutte le cassette postali siano ospitate nel cloud. Può facilitare la riduzione della complessità, poiché non è necessario mantenere i server di messaggistica in locale. [Passaggio a Exchange Online](#switch-to-exchange-online) descrive questo scenario.

- **Protezione EOP con cassette postali ibride**: è possibile che si desiderino cassette postali cloud, ma è necessario mantenere le cassette postali per alcuni utenti locali. Scegliere questo scenario se si desidera che alcune cassette postali siano locali e altre siano ospitate su cloud con Exchange Online. [Passare a una soluzione ibrida](#switch-to-a-hybrid-solution) descrive questo scenario.

## <a name="switch-to-eop-standalone"></a>Passare a EOP autonomo

Se attualmente le cassette postali sono ospitate in locale e si utilizza un'applicazione di protezione locale o un servizio di protezione della messaggistica cloud, è possibile passare a EOP per utilizzare disponibilità e funzionalità di protezione. Per impostare EOP in uno scenario autonomo, in cui le cassette postali sono ospitate in locale e utilizzano EOP per la protezione della posta elettronica, seguire la procedura indicata in [Installazione del servizio EOP](set-up-your-eop-service.md). Nell'argomento viene descritta la procedura per impostare la protezione EOP, che include l'accesso, l'aggiunta del proprio dominio e l'impostazione del flusso di posta con i connettori.

## <a name="switch-to-exchange-online"></a>Passaggio a Exchange Online

È possibile che le cassette postali locali siano protette da un dispositivo locale e che si desideri passare alle cassette postali ospitate sul cloud di Exchange Online e alla protezione di EOP per usufruire delle funzionalità di messaggistica e protezione di Microsoft 365 cloud. Per iniziare, è possibile iscriversi a Microsoft 365 e aggiungere il proprio dominio. Questo scenario non richiede di impostare connettori, poiché non esistono routing alle cassette postali locali. Iniziare a [ottenere le funzionalità avanzate più recenti con Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) per iscriversi e familiarizzare con le sue caratteristiche.

Durante il processo di installazione di Microsoft 365, verranno creati gli utenti delle cassette postali basate sul cloud.

## <a name="switch-to-a-hybrid-solution"></a>Passare a una soluzione ibrida

È possibile spostare solamente una parte delle cassette postali nel cloud in base a requisiti aziendali o considerazioni normative. Quando viene distribuito uno scenario ibrido, è possibile spostare le cassette postali nel cloud come stabilito dai requisiti aziendali. La migrazione a uno scenario ibrido con protezione EOP risulta più complicata rispetto alla migrazione a uno scenario completamente cloud. Tuttavia Microsoft mette a disposizione dell'utente una vasta gamma di risorse e un'assistenza completa affinché lo spostamento allo scenario ibrido avvenga nel modo più semplice possibile.

Il modo migliore per iniziare, se si sta prendendo in considerazione una distribuzione ibrida, è [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). Inoltre, esistono alcuni metodi per indirizzare la posta a uno scenario ibrido che è importante comprendere. Il [routing di trasporto nelle distribuzioni ibride di Exchange](https://docs.microsoft.com/exchange/transport-routing) spiega ogni tipo, in modo da poter scegliere il miglior scenario di routing, in base ai requisiti aziendali.

## <a name="migration-planning"></a>Pianificazione della migrazione

Se si decide di passare a EOP, assicurarsi di prestare particolare attenzione alle seguenti aree:

- **Regole di filtro personalizzate**: se si dispone di un filtro personalizzato o di regole aziendali per rilevare una posta indesiderata specifica, è consigliabile provare EOP con le impostazioni predefinite per un determinato periodo di tempo prima di eseguire la migrazione delle regole. Poiché EOP offre protezione da posta indesiderata a livello aziendale con impostazioni predefinite, è possibile che non sia necessario migrare alcune delle regole a EOP. Ovviamente, nel caso di regole che applicano criteri aziendali personalizzati specifici, è possibile eseguirne la creazione. [Le regole del flusso di posta (regole di trasporto) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) sono disponibili istruzioni dettagliate per la creazione di regole del flusso di posta in EOP.

- Elenchi di indirizzi IP **consentiti ed elenchi di indirizzi IP bloccati**: se si dispone di elenchi di indirizzi consentiti per utente e di blocco, è possibile copiare gli elenchi in EOP come parte del processo di configurazione. Per ulteriori informazioni sull'elenco indirizzi IP consentiti e sull'elenco indirizzi IP bloccati, vedere [Configure the Connection Filter Policy](configure-the-connection-filter-policy.md).

- **Comunicazione sicura**: se si dispone di un partner che richiede la messaggistica crittografata, è consigliabile configurarla nell'interfaccia di amministrazione di Exchange. Per configurare questo scenario, vedere [configurare i connettori per il flusso di posta sicura con un'organizzazione partner](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Durante il passaggio da un'applicazione locale a EOP, è possibile lasciare che l'applicazione o server locale esegua le verifiche relative alle regole aziendali. Ad esempio, se l'apparecchio esegue il filtro personalizzato sulla posta in uscita e si desidera continuare a farlo, è possibile configurare EOP in modo da inviare posta direttamente all'accessorio per ulteriori filtri, prima di instradarli a Internet.
