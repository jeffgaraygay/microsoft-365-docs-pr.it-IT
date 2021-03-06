---
title: GDPR per Skype for Business Server
description: Informazioni su come gestire i requisiti GDPR nell'ambiente Skype for Business Server e Lync Server locale.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: aa0d66bcf727b7dd3c545384ec3a4838667a9183
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596403"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a>GDPR per Skype for Business Server e Lync Server

La maggior parte dei dati di Skype for Business Server e Lync Server è archiviata in Exchange Server. Ad esempio:

-   Cronologia conversazioni

-   Trascrizioni e notifiche di segreteria telefonica

-   Inviti alle riunioni

Seguire le procedure descritte per [GDPR per Exchange Server](gdpr-for-exchange-server.md) per trovare, esportare o eliminare questi tipi di dati per le richieste GDPR.

Gli elenchi contatti sono archiviati nel database di SQL Server. Possono essere esportati nei modi seguenti:

-   Gli utenti finali possono esportare autonomamente i contatti direttamente facendo clic sull’intestazione del gruppo e scegliendo Copia. Tutti i contatti in tale gruppo verranno copiati negli Appunti, per poi essere incollati in qualsiasi applicazione.

-   È possibile usare il cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) per esportare i dati.

Il contenuto caricato in una riunione, come file di PowerPoint o gli stampati, o il contenuto generato durante una riunione, come lavagna, sondaggi e domande e risposte, viene archiviato nel filtro. Può essere esportato anche se gli utenti finali accedono di nuovo a una riunione che non sia scaduta e scaricano il contenuto aggiornato o memorizzano screenshot nel caso di contenuto generato.

Le riunioni MeetNow che non si trovano nel Calendario e nella lista contatti e diritti di contatto (familiari, colleghi e così via) di Exchange sono nel database dell’utente. In Lync Server 2013 e versioni successive, è possibile usare il cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) per esportare i dati.
