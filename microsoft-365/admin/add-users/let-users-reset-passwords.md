---
title: Consentire agli utenti di reimpostare le loro password
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Informazioni su come è possibile reimpostare le password utilizzando lo strumento di reimpostazione della password self-service.
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780590"
---
# <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

Cosa fare per non ricevere più richieste di modifica delle password degli utenti? Come amministratore di Microsoft 365, è possibile consentire agli utenti di utilizzare lo [strumento di reimpostazione della password in modalità self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo che non sia necessario reimpostare le password. Un gran risparmio di tempo! 
  
Ecco alcune informazioni utili:
  
- Si ottiene la reimpostazione della password in modalità self-service per gli utenti Cloud **gratis** con qualsiasi piano di Microsoft 365 business, Education o no profit paid. Non funziona con Microsoft 365 Trial.

- Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure.

- **Se si utilizza Active Directory locale**, non si applicano i due punti sopra riportati. Piuttosto, è possibile configurare questa impostazione, ma **richiede un abbonamento a pagamento ad Azure ad Premium**.

Guardare un breve video su come consentire agli utenti di reimpostare le proprie password. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Consentire alle persone di reimpostare le proprie password

Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>, passare alla pagina **Impostazioni** > **org** Settings.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> ** &amp; privacy sicurezza** .

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>passare alla pagina impostazioni di sicurezza **per la** \> **Settings** \> ** &amp; privacy** delle impostazioni.

::: moniker-end

2. Nella parte superiore della pagina **Impostazioni organizzazione** selezionare la scheda **protezione & privacy** .
  
3. Selezionare **reimpostazione della password in modalità self-service**.

4. In **reimpostazione della password self-service**selezionare **Vai al portale di Azure per abilitare la reimpostazione della password in modalità self-service**.

5. Nel riquadro di spostamento a sinistra, selezionare **utenti**e quindi fare clic su **utenti | Pagina tutti gli utenti** , selezionare **Reimposta password**.
  
6. Nella pagina delle **Proprietà** , selezionare **tutto** per attivarlo per tutti gli utenti dell'azienda, quindi selezionare **Salva**.
  
7. Quando gli utenti accedono, verrà richiesto di immettere ulteriori informazioni di contatto che consentiranno di reimpostare la password in futuro.

## <a name="related-articles"></a>Articoli correlati

[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md)
  
[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md)

[Video per la formazione di Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
