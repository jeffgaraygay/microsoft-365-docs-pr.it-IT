---
title: Creare un gruppo di Microsoft 365 con un PDL specifico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Informazioni su come creare un gruppo di Microsoft 365 con una posizione dati preferita specificata in un ambiente multi-geografico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906d0b4881dd69bbf47cbb536c6c448a1a4f611
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691271"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Creare un gruppo di Microsoft 365 con un PDL specifico

Quando gli utenti di un ambiente multi-geografico creano un gruppo di Microsoft 365, il percorso dei dati preferito del gruppo viene automaticamente impostato su quello dell'utente. Gli amministratori globali di SharePoint ed Exchange possono creare i gruppi in qualsiasi area selezionata. 

Se è necessario creare un gruppo con una posizione preferita per i dati specifica, è possibile usare il cmdlet New-UnifiedGroup di Microsoft PowerShell dall'interfaccia di amministrazione di SharePoint o tramite Exchange Online. Quando si esegue questa operazione, il provisioning della cassetta postale del gruppo e del sito di SharePoint associato al gruppo verrà effettuato nella posizione preferita per i dati specifica.

Per creare un gruppo di Microsoft 365 con il PDL specificato, passare all'interfaccia di amministrazione di SharePoint nella posizione geografica in cui si desidera creare il sito del gruppo.

Ad esempio:

Se si vuole per creare un sito del gruppo nella posizione in Australia, passare a https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Selezionare **+ Crea**.
2. Seguire la procedura per creare un sito di gruppo.

Il provisioning del sito del gruppo verrà effettuato nella posizione geografica corrispondente all'interfaccia di amministrazione di SharePoint da cui è stata avviata la richiesta di creazione del sito. 

Utilizzo di PowerShell di Exchange 

Connettersi a PowerShell per Exchange Online e passare il parametro *-MailBoxRegion* con il codice della posizione geografica.

Ad esempio: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Screenshot del cmdlet New-UnifiedGroup di PowerShell con la sintassi](../media/multi-geo-new-group-with-pdl-powershell.png)

Si noti che il provisioning del sito del gruppo di SharePoint viene effettuato su richiesta. Il provisioning del sito verrà effettuato la prima volta che un membro o un proprietario del gruppo prova ad accedervi.

## <a name="geo-location-codes"></a>Codici di posizione geografica

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Argomenti correlati

[Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
