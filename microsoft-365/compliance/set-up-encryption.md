---
title: Configurare la crittografia in Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, alcune funzionalità di crittografia sono attivate per impostazione predefinita. altre funzionalità possono essere configurate per soddisfare determinati requisiti legali o di conformità.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799991"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurare la crittografia in Office 365 Enterprise

La crittografia può proteggere il contenuto dalla lettura da parte di utenti non autorizzati. Poiché la [crittografia in Office 365](encryption.md) può essere eseguita utilizzando diverse tecnologie e metodi, non esiste un singolo luogo in cui si attiva o si configura la crittografia. In questo articolo vengono fornite informazioni sui vari modi in cui è possibile impostare o configurare la crittografia come parte della strategia di protezione delle informazioni.
  
> [!TIP]
> Se si desiderano ulteriori informazioni tecniche sulla crittografia, vedere [informazioni di riferimento tecnico sulla crittografia in Office 365](technical-reference-details-about-encryption.md).
  
Con Office 365, sono disponibili diverse funzionalità di crittografia per impostazione predefinita. Ulteriori funzionalità di crittografia possono essere configurate per soddisfare determinati requisiti legali o di conformità. Nella tabella seguente vengono descritti diversi metodi di crittografia per diversi scenari.
  
|**Scenario**|**Metodi di crittografia**|
|:-----|:-----|
|I file vengono salvati nei computer Windows  <br/> |La crittografia a livello di computer può essere completata tramite BitLocker nei dispositivi Windows. In qualità di amministratore aziendale o Pro IT, è possibile configurarlo utilizzando Microsoft Deployment Toolkit (MDT). Vedere [configurare MDT per BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|I file vengono salvati nei dispositivi mobili  <br/> |Alcuni tipi di dispositivi mobili crittografano i file salvati nei dispositivi per impostazione predefinita. Con le [funzionalità di gestione dei dispositivi mobili incorporati per office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0), è possibile impostare criteri che determinano se consentire ai dispositivi mobili di accedere ai dati in Office 365. Ad esempio, è possibile impostare un criterio che consenta solo i dispositivi che crittografano il contenuto per accedere ai dati di Office 365. Vedere [creare e distribuire i criteri di sicurezza del dispositivo](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Per un ulteriore controllo su come i dispositivi mobili interagiscono con Office 365, è possibile considerare l'aggiunta di [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps).  <br/> |
|È necessario controllare le chiavi di crittografia utilizzate per crittografare i dati nei data center di Microsoft  <br/> | In qualità di amministratore di Office 365, è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft.  <br/> [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md) <br/> |
|Le persone stanno comunicando tramite posta elettronica (Exchange Online)  <br/> | In qualità di amministratore di Exchange Online, sono disponibili diverse opzioni per la configurazione della crittografia della posta elettronica. Ad esempio:  <br/>  Utilizzo di [Office 365 Message Encryption (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) per consentire agli utenti di inviare messaggi crittografati all'interno o all'esterno dell'organizzazione  <br/>  Utilizzo di [S/MIME per la firma e la crittografia dei messaggi](https://aka.ms/c6dozg) per crittografare e firmare digitalmente i messaggi di posta elettronica  <br/>  Utilizzo di TLS per [configurare i connettori per il flusso di posta sicura con un'altra organizzazione](https://aka.ms/hs809p) <br/>  Vedere la [crittografia della posta elettronica in Office 365](https://aka.ms/hic3f7).  <br/> |
|È possibile accedere ai file dai siti del team o dalle raccolte documenti (OneDrive for business o SharePoint Online)  <br/> |Quando si utilizzano file salvati in OneDrive for business o SharePoint Online, vengono utilizzate le connessioni TLS. Questo è incorporato in Office 365 automaticamente. Vedere [crittografia dei dati in OneDrive for business e SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|I file sono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Skype for business online)  <br/> |Quando gli utenti utilizzano i file che usano Skype for business online, TLS viene utilizzato per la connessione. Questo è incorporato in Office 365 automaticamente. Vedere [sicurezza e archiviazione (Skype for business online)](https://aka.ms/nuq4ws).  <br/> |
|I file sono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Microsoft Teams)  <br/> |Quando gli utenti utilizzano i file tramite Microsoft teams, TLS viene utilizzato per la connessione. Questo è incorporato in Office 365 automaticamente. Microsoft teams attualmente non supporta il rendering in linea dei messaggi di posta elettronica crittografati. Per impedire l'atterraggio di messaggi di posta elettronica crittografati in Microsoft teams come crittografati, vedere [Message Encryption FAQ](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail).  <br/> 

## <a name="additional-information"></a>Informazioni aggiuntive

Per ulteriori informazioni sulle soluzioni di protezione dei file che includono le opzioni di crittografia, vedere [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
 
