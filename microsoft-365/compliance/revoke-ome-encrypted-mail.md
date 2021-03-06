---
title: Revoca della posta elettronica crittografata tramite crittografia avanzata dei messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Come amministratore e come mittente del messaggio, è possibile revocare alcuni messaggi di posta elettronica crittografati con la crittografia avanzata dei messaggi di Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868948"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revoca della posta elettronica crittografata tramite crittografia avanzata dei messaggi

La revoca del messaggio di posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365. La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5. Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o il componente aggiuntivo Office 365 Advanced Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 SKU.

Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md).

Se un messaggio è stato crittografato utilizzando la crittografia avanzata dei messaggi di Office 365 e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni. Gli amministratori revocano i messaggi tramite PowerShell. Come mittente, è possibile revocare un messaggio inviato direttamente da Outlook sul Web. In questo articolo vengono descritte le circostanze in cui la revoca è possibile e come procedere.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento. Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, non è possibile revocare il messaggio.

Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari di Gmail e Yahoo, ricevono un'esperienza basata sul collegamento.

Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente da Outlook sul Web. Ad esempio, i messaggi vengono crittografati con l'opzione solo crittografia.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Schermata che mostra solo l'opzione Crittografa solo in Outlook sul Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Esperienza dei destinatari per i messaggi di posta elettronica crittografati

Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".

![Schermata che visualizza un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Come revocare un messaggio crittografato inviato

Per revocare un messaggio crittografato inviato, eseguire la procedura seguente.

1. In Outlook sul Web, nella cartella **inviata** , passare al messaggio che si desidera revocare.

   Se la posta è revocabile, vedrai il collegamento "Rimuovi accesso esterno" nella parte superiore del messaggio.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Schermata che mostra il messaggio crittografato che si desidera revocare in Outlook sul Web.":::

2. Fare clic su **Rimuovi accesso esterno** per revocare il messaggio.

   Il messaggio indica che lo stato è stato revocato.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Schermata in cui viene visualizzato il messaggio crittografato revocato in Outlook sul Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Come revocare un messaggio crittografato come amministratore

Gli amministratori di Microsoft 365 seguono queste procedure generali per revocare un messaggio di posta elettronica crittografato idoneo:

- Ottenere l'ID del messaggio di posta elettronica.
- Verificare che sia possibile revocare il messaggio.
- Revocare la posta.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Passaggio 1. Ottenere l'ID del messaggio di posta elettronica

Prima di poter revocare una posta crittografata, raccogliere l'ID del messaggio di posta elettronica. Il MessageId è in genere del formato seguente:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Sono disponibili diversi modi per individuare l'ID del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte alcune opzioni, ma è possibile utilizzare qualsiasi metodo che fornisca l'ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la traccia dei messaggi nel &amp; Centro sicurezza e conformità

1. Cercare il messaggio di posta elettronica dal mittente o dal destinatario utilizzando la [nuova traccia dei messaggi nel centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **Dettagli traccia dei messaggi** . Espandere **ulteriori informazioni** per individuare l'ID del messaggio.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i rapporti di crittografia dei messaggi di Office nel centro sicurezza e &amp; conformità

1. Nel centro sicurezza &amp; e conformità, passare al **rapporto di crittografia dei messaggi**. Per informazioni su questo report, vedere [visualizzare i report di sicurezza della posta elettronica nel &amp; Centro sicurezza e conformità](../security/office-365-security/view-email-security-reports.md).

2. Scegliere la tabella **Visualizza dettagli** e identificare il messaggio che si desidera revocare.

3. Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID del messaggio.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Passaggio 2. Verificare che la posta sia revocabile

Per verificare se è possibile revocare un messaggio, controllare se il campo stato revoca è visibile nel rapporto di crittografia, nella tabella **Details** del Centro sicurezza e &amp; conformità.

Per verificare se è possibile revocare un messaggio di posta elettronica specifico utilizzando Windows PowerShell, eseguire la procedura seguente.

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Get-OMEMessageStatus nel modo seguente:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Questo comando restituisce l'oggetto del messaggio e indica se il messaggio è revocabile. Ad esempio,

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Passaggio 3. Revocare la posta elettronica

Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta elettronica utilizzando il &amp; Centro sicurezza e conformità di Windows PowerShell.

Per revocare il messaggio utilizzando il Centro sicurezza e &amp; conformità

1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al centro sicurezza & Compliance.

2. Nel **rapporto di crittografia**, nella tabella **Details** del messaggio, scegliere **revoca messaggio**.

Per revocare un messaggio di posta elettronica utilizzando Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation.

1. Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Crittografia messaggi avanzata di Office 365-scadenza del messaggio di posta elettronica](ome-advanced-expiration.md)

- [Descrizione del servizio criteri di conformità e del messaggio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
