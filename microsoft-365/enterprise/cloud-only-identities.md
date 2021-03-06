---
title: Identità solo cloud di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: In questo articolo viene descritto come creare utenti e gruppi quando la sottoscrizione Microsoft 365 utilizza l'identità solo cloud.
ms.openlocfilehash: 4c8e7d4a29f548fca2fef9696f488dc333743ef9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691095"
---
# <a name="microsoft-365-cloud-only-identity"></a>Identità solo cloud di Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Con l'identità solo cloud, tutti gli utenti, i gruppi e i contatti vengono archiviati nel tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365. Ecco i componenti di base dell'identità solo cloud.
 
![I componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

Gli utenti e i loro account utente nelle organizzazioni possono essere categorizzati in vari modi. Ad esempio, alcuni sono dipendenti e hanno uno stato permanente. Alcuni sono fornitori, appaltatori o partner che hanno uno stato temporaneo. Alcuni sono utenti esterni che non dispongono di account utente, ma è comunque necessario concedere l'accesso a servizi e risorse specifici per supportare l'interazione e la collaborazione. Ad esempio:

- Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud

- Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.

Fare un bilancio dei tipi di utenti dell'organizzazione. Quali sono i raggruppamenti? Ad esempio, è possibile raggruppare gli utenti in base alla funzione o allo scopo di alto livello dell'organizzazione.

Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.

È possibile utilizzare i gruppi in Azure AD per diversi scopi che semplificano la gestione dell'ambiente cloud. Ad esempio, con i gruppi di Azure AD, è possibile:

- Utilizzare la gestione delle licenze basate su gruppo per assegnare le licenze per Microsoft 365 agli account utente automaticamente non appena vengono aggiunti come membri.
- Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi degli account utente, ad esempio il nome del reparto.
- Provisioning automatico degli utenti per le applicazioni del software come servizio (SaaS) e per proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori e altre regole di accesso condizionale.
- Provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online.

È possibile creare nuovi ***utenti*** con:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [PowerShell per Microsoft 365](create-user-accounts-with-microsoft-365-powershell.md)

È possibile creare nuovi ***gruppi*** con:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [PowerShell per Microsoft 365](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a>Passaggio successivo per l'identità solo cloud

[Assegnare licenze agli account utente](assign-licenses-to-user-accounts.md).
