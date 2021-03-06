---
title: Risoluzione dei problemi di posta elettronica inviata a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni per la risoluzione dei problemi relativi all'invio di posta elettronica alle cassette postali in Microsoft 365 & procedure consigliate per la posta in blocco ai clienti di Microsoft 365.
ms.openlocfilehash: 0d9c1646aa7491b3da458c7cb0ddeb908873153a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208598"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Risoluzione dei problemi di posta elettronica inviata a Microsoft 365

In questo articolo vengono fornite informazioni per la risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cassette postali in Microsoft 365 e le procedure consigliate per la posta in blocco ai clienti

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Si sta gestendo la reputazione di invio di IP e domini?

Le tecnologie di filtro EOP sono progettate per fornire la protezione da posta indesiderata per Microsoft 365 e altri prodotti Microsoft come Exchange Server. È inoltre possibile utilizzare SPF, DKIM e DMARC; tecnologie di autenticazione della posta elettronica che consentono di risolvere il problema dello spoofing e del phishing verificando che il dominio che invia il messaggio di posta elettronica sia autorizzato a farlo. Il filtro EOP è influenzato da una serie di fattori correlati all'IP di invio, al dominio, all'autenticazione, all'accuratezza degli elenchi, alle tariffe dei reclami, al contenuto e altro ancora. Tra questi, uno dei fattori principali per abbassare la reputazione del mittente e la possibilità di inviare messaggi di posta elettronica è la frequenza dei reclami per la posta indesiderata.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Si sta inviando messaggi di posta elettronica da nuovi indirizzi IP?

Gli indirizzi IP non utilizzati in precedenza per inviare messaggi di posta elettronica in genere non dispongono di una reputazione integrata nei sistemi. Di conseguenza, è più probabile che i messaggi di posta elettronica provenienti da nuovi IP sperimentino problemi di recapito. Una volta che l'IP ha creato una reputazione per l'invio di posta indesiderata, EOP consentirà una migliore esperienza di recapito della posta elettronica.

I nuovi indirizzi IP aggiunti per i domini autenticati con i record SPF esistenti in genere avvertono l'ulteriore vantaggio di ereditare una parte della reputazione di invio del dominio. Se il dominio ha una buona reputazione di invio, è possibile che i nuovi IP possano riscontrare tempi di rampa più veloci. Un nuovo IP può pretendere di essere completamente rampante entro un paio di settimane o prima a seconda del volume, dell'accuratezza degli elenchi e delle tariffe di reclamo per la posta indesiderata.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Verificare che il DNS sia configurato correttamente

Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, sarà necessario contattare il provider di hosting DNS.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Assicurarsi di non essere pubblicizzati come IP non instradabile

Non è possibile accettare messaggi di posta elettronica provenienti da mittenti che non eseguono una ricerca DNS inversa. In alcuni casi, i mittenti legittimi si annunciano in modo errato come IP instradabile non Internet quando si tenta di aprire una connessione a EOP. Gli indirizzi IP riservati per la rete privata (non instradabile) includono:

- 192.168.0.0/16 (o 192.168.0.0-192.168.255.255)

- 10.0.0.0/8 (o 10.0.0.0-10.255.255.255)

- 172.16.0.0/11 (o 172.16.0.0-172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Si è ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365

Alcuni problemi di recapito sono il risultato dell'indirizzo IP del mittente che è stato bloccato da Microsoft o perché l'account utente è stato identificato come mittente vietato a causa di precedenti attività di posta indesiderata. Se si ritiene di aver ricevuto il rapporto di mancato recapito in caso di errore, seguire le istruzioni riportate nel messaggio di mancato recapito per risolvere il problema.

Per ulteriori informazioni sull'errore ricevuto, vedere l'elenco dei codici di errore nei [rapporti di mancato recapito della posta elettronica in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Ad esempio, se si riceve il rapporto di mancato recapito seguente, indica che l'indirizzo IP di invio è stato bloccato da Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Per richiedere la rimozione da questo elenco, è possibile [utilizzare il portale di delist per rimuovere se stessi dall'elenco dei mittenti bloccati](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>La posta elettronica è atterrata nella cartella posta indesiderata del destinatario

Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile collaborare con il destinatario per inviare questo messaggio falso positivo al team di analisi di posta indesiderata di Microsoft, che valuterà e analizzerà il messaggio. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Il traffico proveniente dall'indirizzo IP è limitato da EOP

Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP è sottoposto a limitazione da EOP, ad esempio:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

È stato ricevuto il rapporto di mancato recapito perché l'attività sospetta è stata rilevata dall'indirizzo IP ed è stata temporaneamente limitata durante la valutazione. Se il sospetto è deselezionato tramite valutazione, questa restrizione verrà revocata a breve.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>Non è possibile ricevere messaggi di posta elettronica da mittenti in Microsoft 365

 Per ricevere i messaggi dagli utenti, verificare che la rete consenta le connessioni dagli indirizzi IP utilizzati da EOP nei data center. Per ulteriori informazioni, vedere [indirizzi IP di Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Procedure consigliate per l'invio di messaggi di posta elettronica agli utenti di Microsoft 365

Se si eseguono spesso campagne di posta elettronica in blocco per gli utenti di Microsoft 365 e si vuole garantire che i messaggi vengano verificati in modo sicuro e tempestivo, seguire i suggerimenti in questa sezione.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Verificare che il nome del mittente rispecchi chi sta inviando il messaggio

L'oggetto dovrebbe essere un breve riepilogo del messaggio e il corpo del messaggio deve indicare in modo chiaro e conciso cosa significa l'offerta, il servizio o il prodotto. Ad esempio:

Impostazione corretta:

> Da: marketing@shoppershandbag.com <br/> Oggetto: aggiornamento del catalogo per la stagione natalizia.

Impostazione non corretta:

> Da: someone@outlook.com <br/> Oggetto: Cataloghi

Più è facile per gli utenti sapere chi è e cosa si sta facendo, minore sarà la difficoltà con la maggior parte dei filtri per la posta indesiderata.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Includi sempre un'opzione di annullamento della sottoscrizione nei messaggi di posta elettronica della campagna

I messaggi di posta elettronica di marketing, in particolare le newsletter, dovrebbero includere sempre un modo di annullamento della sottoscrizione da messaggi di posta elettronica futuri. Ad esempio:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Alcuni mittenti includono questa opzione richiedendo ai destinatari di inviare un messaggio di posta elettronica a un determinato alias con "Annulla sottoscrizione" nell'oggetto. Questo non è preferibile all'esempio di un clic sopra riportato. Se si sceglie di richiedere ai destinatari di inviare un messaggio di posta elettronica, verificare che quando si fa clic sul collegamento, tutti i campi richiesti siano precompilati.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Utilizzare l'opzione double opt-in per la registrazione della posta elettronica o della newsletter di marketing

Questa procedura consigliata per il settore è consigliabile se la propria azienda richiede o incoraggia gli utenti a registrare le proprie informazioni di contatto per accedere al prodotto o ai servizi. Alcune aziende hanno la consuetudine di iscrivere automaticamente gli utenti per i messaggi di posta elettronica di marketing o di e-newsletter durante il processo di registrazione, ma questa è considerata una pratica di marketing discutibile nel mondo del filtraggio della posta elettronica.

Durante il processo di registrazione, se la casella di controllo "Sì, Inviami la tua newsletter" o "Sì, Inviami offerte speciali" è selezionata per impostazione predefinita, gli utenti che non prestano molta attenzione possono involontariamente iscriversi per la posta elettronica di marketing o le newsletter che non desiderano ricevere.

 È consigliabile invece l'opzione double opt-in, il che significa che la casella di controllo per i messaggi di posta elettronica di marketing o le newsletter è deselezionata per impostazione predefinita. Inoltre, una volta che il modulo di registrazione è stato inviato, un messaggio di posta elettronica di verifica viene inviato all'utente con un URL che consente di confermare la decisione di ricevere messaggi di posta elettronica di marketing.

 In questo modo si garantisce che solo gli utenti che desiderano ricevere la posta elettronica di marketing siano iscritti per la posta elettronica, successivamente deselezionando la società di invio di eventuali pratiche di marketing della posta elettronica discutibili.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Verificare che il contenuto del messaggio di posta elettronica sia trasparente e tracciabile

Altrettanto importante del modo in cui vengono inviati i messaggi di posta elettronica è il contenuto che contengono. Quando si crea il contenuto della posta elettronica, utilizzare le procedure consigliate seguenti per garantire che i messaggi di posta elettronica non vengano contrassegnati tramite i servizi di filtraggio delle e-mail:

- Quando il messaggio di posta elettronica richiede che i destinatari aggiungono il mittente alla Rubrica, è necessario indicare chiaramente che tale azione non è una garanzia di recapito.

- I reindirizzamenti inclusi nel corpo del messaggio devono essere simili e coerenti e non multipli e diversificati. Un reindirizzamento in questo contesto è qualsiasi elemento che punti al di fuori del messaggio, ad esempio collegamenti e documenti. Se si dispone di numerosi collegamenti pubblicitari o di annullamento della sottoscrizione oppure si aggiornano i collegamenti dei profili, tutti gli utenti devono puntare allo stesso dominio. Ad esempio:

  Impostazione corretta:

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Impostazione non corretta:

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evitare contenuti con immagini e allegati di grandi dimensioni o messaggi composti unicamente da un'immagine.

- La privacy pubblica o le impostazioni di P3P devono indicare chiaramente la presenza di pixel di rilevamento (bug Web o beacon).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Rimuovere gli alias di posta elettronica non corretti dai database

Qualsiasi alias di posta elettronica nel database che consente di creare un rimbalzo non è necessario e pone i messaggi di posta elettronica in uscita a rischio per un ulteriore controllo tramite i servizi di filtraggio della posta elettronica. Verificare che il database di posta elettronica sia aggiornato.
