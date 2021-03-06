---
title: Risolvere i problemi relativi ai dispositivi AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere i problemi che potrebbero essere visualizzati durante l'utilizzo dei file del dispositivo Autopilot in Microsoft 365 Business Premium.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403411"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Risolvere i problemi relativi ai dispositivi AutoPilot

## <a name="device-file-error-messages"></a>Messaggi di errore del file del dispositivo

Di seguito sono riportate alcune informazioni sugli errori che potrebbero verificarsi durante l'utilizzo dei file del dispositivo Autopilot in Microsoft 365 Business Premium. 
  
|**Codice di errore**|**Correzione da provare**|
|:-----|:-----|
|Corpo richiesta non valida  <br/> |Questo errore dovrebbe verificarsi raramente, se viene visualizzato questo errore, provare a eseguire di nuovo l'operazione.  <br/> |
|Il valore hash hardware per un dispositivo non è corretto.  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto. Verificare innanzitutto che il valore sia stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore è ancora in corso, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Dispositivo assegnato a un altro tenant  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV sia per il numero di serie che per il codice Product Key di uno o più dispositivi non è corretto. Verificare innanzitutto che il valore sia stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore è ancora in corso, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Il file CSV contiene un numero di serie o un codice Product Key non valido  <br/> |Se viene visualizzato questo errore, significa che il dispositivo che si sta tentando di registrare è già registrato da un'altra organizzazione. Per correggere l'errore, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Questo dispositivo non è supportato per il programma di installazione tramite Autopilot  <br/> | Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione del pilota automatico. I dispositivi devono soddisfare questi requisiti:  <br/>  Devono eseguire Windows 10 1703 o versione successiva.  <br/>  Nuovi dispositivi che non sono stati eseguiti tramite Windows.  <br/> |
|Dispositivo non trovato  <br/> |Questo errore indica che uno o più dispositivi nel file CSV non sono registrati nell'organizzazione. Per risolvere il riguardo, chiedere assistenza al fornitore dell'hardware.  <br/> |
