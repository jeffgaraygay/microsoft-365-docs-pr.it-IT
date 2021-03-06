---
title: Funzionamento dell'autenticazione moderna per le applicazioni client di Office 2013 e Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Informazioni su come le funzionalità di autenticazione moderna di Microsoft 365 funzionano in modo diverso per le app client di Office 2013 e 2016.
ms.openlocfilehash: 62aa04e295c2734d705f22bd2f62c6bc5e622426
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691510"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Funzionamento dell'autenticazione moderna per le app client di Office 2013, Office 2016 e Office 2019

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Leggere questo articolo per informazioni su come le app client di Office 2013, Office 2016 e Office 2019 utilizzano le funzionalità di autenticazione moderne in base alla configurazione dell'autenticazione sul tenant di Microsoft 365 per Exchange Online, SharePoint Online e Skype for business online.

> [!NOTE]
> Le app client legacy, come Office 2010 e Office per Mac 2011, non supportano l'autenticazione moderna e possono essere utilizzate solo con l'autenticazione di base.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Disponibilità dell'autenticazione moderna per i servizi Microsoft 365

Per i servizi Microsoft 365, lo stato predefinito dell'autenticazione moderna è il seguente:
  
- Attivata **per** Exchange Online per impostazione predefinita. Vedere [abilitare o disabilitare l'autenticazione moderna in Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) per disattivarla. 
    
- Attivata **per** SharePoint Online per impostazione predefinita. 
    
- Attivata per Skype for business **online per impostazione** predefinita. Vedere [abilitare Skype for business online per l'autenticazione moderna ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)per disattivarla o attivarla.

> [!NOTE]
> Per i tenant creati **prima** del 1° agosto 2017, l'autenticazione moderna è **disattivata** per impostazione predefinita per Exchange Online e Skype for Business Online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Comportamento di accesso delle app client di Office

Le app client di Office 2013 supportano l'autenticazione legacy per impostazione predefinita. Legacy significa che supportano l'assistente per l'accesso di Microsoft online o l'autenticazione di base. Affinché questi client utilizzino le funzionalità di autenticazione moderne, è necessario che il client Windows disponga delle chiavi del registro di sistema impostate. Per istruzioni, vedere [abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Per abilitare l'autenticazione moderna per tutti i dispositivi che eseguono Windows (ad esempio su portatili e tablet) con Microsoft Office 2013 installato, è necessario impostare le seguenti chiavi del Registro di sistema. Le chiavi devono essere impostate in ogni dispositivo per cui si vuole abilitare l'autenticazione moderna:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Leggere [come usare l'autenticazione moderna (adal) con Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=785431) per informazioni su come funziona con Skype for business. 
  
I client di Office 2016 e Office 2019 supportano l'autenticazione moderna per impostazione predefinita e non è necessaria alcuna azione per il client per l'utilizzo di questi nuovi flussi. Tuttavia, è necessaria un'azione esplicita per l'utilizzo dell'autenticazione legacy.
  
Fare clic sui collegamenti riportati di seguito per vedere come funziona l'autenticazione client di Office 2013, Office 2016 e Office 2019 con i servizi Microsoft 365 a seconda che l'autenticazione moderna sia attivata o meno.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a Exchange Online con o senza l'autenticazione moderna.
  
|Versione app client di Office * * * *|Chiave del registro di sistema presente? * * * *|Autenticazione moderna in? * * * *|Comportamento di autenticazione con autenticazione moderna attivata per il tenant (impostazione predefinita) * * * *|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sì  <br/> |Impone l'autenticazione moderna in Outlook 2013, 2016 o 2019. <br/> [Altre informazioni](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Impone l'autenticazione moderna all'interno del client Outlook.<br/> |
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2016  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sì  <br/> |Impone l'autenticazione moderna su 2013, 2016 o 2019. <br/> [Altre informazioni](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Impone l'autenticazione moderna all'interno del client Outlook.<br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a SharePoint Online con o senza l'autenticazione moderna.
  
|Versione app client di Office * * * *|Chiave del registro di sistema presente? * * * *|Autenticazione moderna in? * * * *|Comportamento di autenticazione con autenticazione moderna attivata per il tenant (impostazione predefinita) * * * *|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business online
<a name="BK_SFBO"> </a>

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a Skype for business online con o senza l'autenticazione moderna.
  
|Versione app client di Office * * * *|Chiave del registro di sistema presente? * * * *|Autenticazione moderna in? * * * *|Comportamento di autenticazione con autenticazione moderna attivata per il tenant * * * *|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant (impostazione predefinita) * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2016  <br/> |No, o EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |L'autenticazione moderna viene tentata per prima. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'assistente per l'accesso di Microsoft online. Server rifiuta l'autenticazione moderna quando i tenant di Skype for business online non sono abilitati.  <br/> |Solo assistente per l'accesso di Microsoft online.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)

[Autenticazione a più fattori per Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)

[Accedere a Microsoft 365 con l'autenticazione a più fattori](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
