---
title: Configurare team con la protezione di base
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Come distribuire team con un livello di protezione di base.
ms.openlocfilehash: 4a1843b687155cefd48bf3800be68c3e01abd7f5
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527861"
---
# <a name="configure-teams-with-baseline-protection"></a>Configurare team con la protezione di base

Questo articolo spiega come distribuire team con un livello di protezione di base. Questo livello offre agli utenti un'ampia gamma di opzioni per la collaborazione, migliorando la gestione delle autorizzazioni e fornendo una protezione di base dalla condivisione eccessiva. Le protezioni consigliate per questo livello includono criteri di accesso alle identità e ai dispositivi e protezione dal malware. Inoltre, è possibile applicare criteri di accesso condizionale e funzionalità di prevenzione della perdita dei dati come necessario.

## <a name="initial-protections"></a>Protezioni iniziali

Come primo passaggio, è consigliabile configurare criteri di base per le identità e l'accesso ai dispositivi. Per informazioni dettagliate, vedere [Suggerimenti sui criteri per la protezione di chat, gruppi e file di Teams](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies).

È anche consigliabile attivare le funzionalità di base di Advanced Threat Protection per prevenire il malware in documenti, allegati e collegamenti. È consigliabile attivare ognuna delle opzioni indicate nella tabella seguente.

|Opzione|Informazioni|
|:------|:-----------|
|Allegati sicuri ATP per SPO, OneDrive e Teams|[Allegati sicuri di Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|Sicurezza documenti ATP|[Sicurezza documenti in Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|Collegamenti sicuri ATP per Teams|[Collegamenti sicuri di Office 365 in Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[Collegamenti sicuri di Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a>Condivisione con gli utenti guest in Teams

In ognuno dei livelli è possibile la condivisione con utenti esterni all'organizzazione. Per i livelli dei dati sensibili e altamente sensibili, si avrà la possibilità di disattivare la condivisione guest al livello di team usando le etichette di riservatezza. Tuttavia, per il funzionamento della condivisione guest in Teams è necessario attivare l'opzione a livello aziendale.

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

Per configurare le impostazioni di accesso guest di Teams

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).
2. Nel riquadro di spostamento sinistro fare clic su **Mostra tutto**.
3. In **Interfacce di amministrazione** fare clic su **Teams**.
4. Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** nel riquadro di spostamento sinistro e fare clic su **Accesso guest**.
5. Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia** **abilitata.
6. Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.

> [!NOTE]
> Dopo l'attivazione, potrebbero essere necessarie fino a 24 ore prima che le impostazioni guest di Teams diventino effettive.

La condivisione guest è attivata per impostazione predefinita per i gruppi di Office 365 e SharePoint. Tuttavia, se in precedenza si sono modificate le impostazioni di condivisione guest per la propria organizzazione, è consigliabile rivedere [Collaborare con gli utenti guest in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) per assicurarsi che la condivisione guest sia disponibile in Teams.

## <a name="site-and-file-sharing"></a>Condivisione di siti e file

Per ridurre il rischio di condivisione accidentale di file o cartelle con persone esterne all'organizzazione, è consigliabile modificare il collegamento di condivisione predefinito per SharePoint in *Solo gli utenti dell'organizzazione*. Se gli utenti devono condividere all'esterno ed è stata abilitata la condivisione guest, potranno comunque modificare il tipo di collegamento quando condividono.

Per modificare il collegamento di condivisione predefinito
1. Aprire l'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint).
2. In **Criteri**fare clic su **Condivisione**.
3. In **Collegamenti di file e cartelle** selezionare **Solo gli utenti dell'organizzazione**.
4. Fare clic su **Salva**.

Per un'esperienza di condivisione guest ottimale, è inoltre consigliabile abilitare l'[Integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

## <a name="create-a-team"></a>Creare un team

Un'ulteriore configurazione per il livello di protezione di base va effettuata nel sito di SharePoint associato a un team. [Creare un team pubblico o privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) prima di procedere alla sezione successiva.

## <a name="site-sharing-settings"></a>Impostazioni di condivisione del sito

Per impostazione predefinita, i membri di un sito di SharePoint possono invitare altri utenti nel sito. Quando un sito fa parte di un team, i membri del team sono inclusi come membri del sito. Tuttavia, le persone aggiunte direttamente al sito non hanno accesso al resto del team. Per questo motivo, è consigliabile gestire le autorizzazioni esclusivamente attraverso il team.

Per agevolare la gestione delle autorizzazioni, è consigliabile configurare il sito associato in modo da consentire solo ai proprietari di condividere il sito. Questo semplifica la gestione delle autorizzazioni e impedisce che qualcuno possa accedere senza che il proprietario del team ne sia a conoscenza. Eseguire questa operazione per ogni team che richiede la protezione di base.

Per aggiornare le impostazioni di condivisione del sito
1. Nella barra degli strumenti per il team fare clic su **File**.
2. Fare clic su **Apri in SharePoint**.
3. Nella barra degli strumenti del sito di SharePoint fare clic sull'icona delle impostazioni, poi su **Autorizzazioni sito**.
4. Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.
5. In **Autorizzazioni di condivisione** selezionare **I proprietari e i membri del sito e gli utenti con autorizzazioni di modifica possono condividere file e cartelle, ma solo i proprietari del sito possono condividere il sito**, quindi fare clic su **Salva**.

## <a name="additional-protections"></a>Protezioni aggiuntive

In Microsoft 365 sono disponibili altri metodi per proteggere i contenuti. Valutare se le opzioni seguenti possono migliorare la sicurezza per l'organizzazione.

- Fare in modo che gli utenti guest accettino le [condizioni per l'utilizzo](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).
- Configurare un [criterio di timeout della sessione](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) per gli utenti guest.
- Creare [tipi di informazioni sensibili](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) e usare la [prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) per impostare criteri per l'accesso alle informazioni riservate.

## <a name="see-also"></a>Vedere anche

[Gestire i criteri di riunione in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[Introduzione alla gestione dei rischi Insider](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
