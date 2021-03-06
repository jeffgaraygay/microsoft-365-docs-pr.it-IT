---
title: Creare e usare un modello per aggiungere utenti
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: È possibile creare e utilizzare un modello per risparmiare tempo e standardizzare le impostazioni quando si aggiungono più utenti.
ms.openlocfilehash: 29953eb97476799d74e883ed8b20bd5f3382cbf4
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022146"
---
# <a name="create-and-use-a-template-to-add-users"></a>Creare e usare un modello per aggiungere utenti

È possibile creare e utilizzare un modello per risparmiare tempo e standardizzare le impostazioni quando si aggiungono più utenti. I modelli sono particolarmente utili se si dispone di utenti che condividono molte proprietà comuni, come quelli che hanno lo stesso ruolo e lavorano nello stesso percorso e quelli che richiedono lo stesso software. Ad esempio, è possibile disporre di un team di ingegneri del supporto tecnico che lavorano nello stesso ufficio.  

## <a name="create-a-template"></a>Creare un modello

I modelli sono facili da creare &mdash; è possibile selezionare **utenti**  >  **attivi**user  >  **template utente**, quindi selezionare **Aggiungi un modello** dall'elenco a discesa oppure è possibile aggiungere un nuovo utente e al termine, si avrà la possibilità di salvare la voce come modello.

Quando si crea un modello dopo l'aggiunta di un utente, i valori scelti per le impostazioni seguenti vengono salvati nel modello:

- Nome di dominio
- Scelta delle impostazioni della password: è possibile scegliere di creare password o farli generare automaticamente
- Scelta della password singola: è possibile richiedere all'utente di creare una nuova password dopo il primo accesso
- Posizione della licenza
- Scelte di licenza
- Scelte dell'applicazione
- Ruolo
- La maggior parte delle informazioni sul profilo, ad esempio **profilo dei processi**, **reparto**, **Office**, **telefono di Office**e indirizzo di **strada** 

Le informazioni seguenti sono specifiche dell'utente e non vengono salvate nel modello:

- Nome e cognome
- Nome visualizzato
- Nome utente
- Scelta per inviare la password tramite posta elettronica e per l'invio della posta elettronica alla password
- Numero di cellulare

Se si sceglie di non immettere le informazioni per un'impostazione all'interno di una sezione, il valore sarà vuoto e l'impostazione non verrà visualizzata nel modello. Ad esempio, se si lascia vuoto il **titolo del processo** , quando si esamina il modello e quando si utilizza il modello, il **titolo del processo** non verrà visualizzato. Se si lasciano vuote tutte le impostazioni della sezione **profilo** , la sezione **profile** visualizzerà **Nessuna fornita** nel modello finale.

Quando si crea un modello selezionando l'opzione **Aggiungi un modello** , è possibile scegliere i valori da completare. Tutto ciò che viene lasciato vuoto verrà visualizzato come **nessuno fornito** nel modello.

## <a name="use-a-template-to-add-a-user"></a>Utilizzo di un modello per aggiungere un utente

Per utilizzare un modello esistente per aggiungere un utente:

1. Nell'interfaccia di **Amministrazione selezionare utenti**  >  **attivi**.

2. Selezionare **modelli utente**e quindi selezionare un modello nell'elenco a discesa. L'elenco conterrà solo i modelli creati e non quelli creati da altri amministratori.

 > [!NOTE]
 > È inoltre possibile utilizzare un modello per aggiungere un utente selezionando **modelli utente**per la  >  **gestione dei modelli**, selezionando un modello e quindi selezionando **utilizza modello**.

3. Seguire la procedura per creare un utente dal modello selezionato.

> [!NOTE]
> Se sono disponibili licenze insufficienti per un utente aggiunto e le informazioni sui pagamenti sono disponibili, si tenterà di acquistare un'altra licenza utilizzando le informazioni di pagamento esistenti. Se le informazioni di pagamento non sono disponibili, l'utente verrà creato come utente senza licenza.

## <a name="manage-templates"></a>Gestire i modelli

È possibile eliminare facilmente i modelli che non sono più necessari e aggiungerne di nuovi. Per eliminare un modello:

1. Nell'interfaccia di **Amministrazione selezionare utenti**  >  **attivi**.

2. Selezionare **modelli**e quindi fare clic su **Gestisci modelli** nell'elenco a discesa.

3. Verrà visualizzato un elenco di modelli. È possibile eliminare un modello eseguendo una delle operazioni seguenti:
    - Selezionare uno o più modelli, quindi fare clic su **Elimina**. 
    - Selezionare i tre punti a destra del nome del modello e quindi fare clic su **Elimina**.
    - Selezionare il nome del modello. Quando vengono visualizzati i dettagli del modello nella parte destra dello schermo, selezionare **Elimina modello**.

## <a name="related-articles"></a>Articoli correlati

[Aggiungere utenti e assegnare licenze contemporaneamente](add-users.md)

[Rimuovere un ex dipendente da Microsoft 365](remove-former-employee.md)
  
