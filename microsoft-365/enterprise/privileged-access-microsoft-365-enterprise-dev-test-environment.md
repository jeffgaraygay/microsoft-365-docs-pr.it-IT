---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Utilizzare questa guida del laboratorio di testing per abilitare la gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365.
ms.openlocfilehash: 28fd27c3059fe25da5da8aaf8700b84c5989b408
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695147"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Con le istruzioni riportate in questo articolo, è possibile configurare la gestione degli accessi con privilegi per aumentare la sicurezza nell'ambiente di testing Microsoft 365 for Enterprise.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
>Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera configurare la gestione degli accessi con privilegi in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare la gestione degli accessi con privilegi in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Se si verifica la gestione degli accessi con privilegi non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di AD DS. Viene fornito come opzione in modo che sia possibile testare la gestione degli accessi con privilegi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: configurare la gestione degli accessi con privilegi

In questa fase, è possibile configurare un gruppo responsabili approvazione e abilitare la gestione degli accessi con privilegi per l'ambiente di testing Microsoft 365 for Enterprise. Per ulteriori informazioni e una panoramica della gestione degli accessi con privilegi, vedere [Privileged Access Management](../compliance/privileged-access-management-overview.md).

Eseguire la procedura seguente per configurare e usare l'accesso privilegiato nell'organizzazione:

- [Passaggio 1: creare un gruppo del responsabile approvazione](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati. Qualsiasi utente che fa parte del gruppo responsabili approvazione sarà in grado di approvare le richieste di accesso. Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Microsoft 365. Creare un nuovo gruppo di sicurezza denominato "revisori accesso privilegiato" nell'ambiente di testing e aggiungere "User 3" precedentemente creato nei passaggi precedenti della guida del laboratorio di testing.

- [Passaggio 2: abilitare l'accesso con privilegi](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    L'accesso privilegiato deve essere attivato in modo esplicito in Microsoft 365 con il gruppo di approvazione predefinito e includendo un set di account di sistema che si desidera escludere dal controllo di accesso a gestione accesso privilegiato. Assicurarsi di abilitare l'accesso privilegiato nell'organizzazione prima di iniziare la fase 3 di questa guida.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: verificare che l'approvazione sia necessaria per le attività con privilegi elevati e

In questa fase, è possibile verificare che il criterio di accesso privilegiato funzioni e che gli utenti dispongano dell'approvazione per l'esecuzione di attività definite con privilegi elevati.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Provare la possibilità di eseguire un'attività non definita in un criterio di accesso con privilegi

Innanzitutto, connettersi a Exchange Management PowerShell con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tentare di creare una nuova regola del journal. L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) non è attualmente definita in un criterio di accesso con privilegi per l'organizzazione.

1. Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.

2. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Visualizzare la nuova regola del journal in Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Creare un nuovo criterio di accesso privilegiato per l'attività New-JournalRule

>[!NOTE]
>Se non sono già stati completati i passaggi 1 e 2 della fase 2 della guida, seguire la procedura seguente per creare un gruppo del responsabile approvazione denominato "revisori di accesso Privilege" e per abilitare l'accesso con privilegi nell'ambiente di testing.

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali dell'account di amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **Configure policies** e selezionare **Add a Policy**.

5. Nei campi a discesa selezionare o immettere i valori seguenti:

    **Tipo di criterio**: attività

    **Ambito di criteri**: Exchange

    **Nome criterio**: nuova regola del Journal

    **Tipo di approvazione**: Manual

    **Gruppo di approvazione**: responsabili approvazione accesso privilegiato

6. Selezionare **Crea** e quindi **Chiudi**. È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti. Assicurarsi che il criterio venga abilitato completamente prima di testare il requisito di approvazione nel passaggio successivo.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisiti di approvazione del test per l'attività New-JournalRule definita in un criterio di accesso con privilegi

1. Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando un account di amministratore globale per l'ambiente di testing.

2. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visualizzazione dell'errore "autorizzazioni insufficienti" in Exchange Management PowerShell:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Richiedere l'accesso per creare una nuova regola del journal utilizzando l'attività New-JournalRule

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale per l'ambiente di testing.

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare **nuova richiesta**. Nei campi a discesa selezionare i valori corretti per l'organizzazione:

    **Tipo di richiesta**: attività

    **Ambito delle richieste**: Exchange

    **Richiesta per**: nuova regola del Journal

    **Durata (ore)**: 2

    **Commenti**: richiedere l'autorizzazione per la creazione di una nuova regola del Journal

5. Selezionare **Salva** e quindi **Chiudi**. La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Approva la richiesta di accesso privilegiato per la creazione di una nuova regola di Journal

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di sicurezza "responsabili approvazione accesso privilegiato" nell'ambiente di testing).

2. Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.

3. Selezionare **Gestisci criteri di accesso e richieste**.

4. Selezionare la richiesta in sospeso e selezionare **approva** per concedere l'accesso all'account di amministratore globale per creare una nuova regola del journal. Un messaggio di posta elettronica di notifica che conferma che l'approvazione è stata concessa verrà inviata all'account di amministratore globale (l'utente richiedente).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testare la creazione di una nuova regola del journal con accesso privilegiato approvato per l'attività New-JournalRule

1. Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.

2. In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Visualizzare la nuova regola del journal in Exchange Management PowerShell.

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
