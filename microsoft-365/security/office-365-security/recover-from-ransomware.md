---
title: Eseguire il ripristino da un attacco ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori di Office 365 possono ottenere informazioni su come eseguire il ripristino da un attacco ransomware.
ms.openlocfilehash: 04cfd2f2417b0c2e084a88f9ee156521339b18c4
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932373"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="3a10e-103">Eseguire il ripristino da un attacco ransomware in Office 365</span><span class="sxs-lookup"><span data-stu-id="3a10e-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="3a10e-104">Anche se si prevedono tutte le precauzioni per proteggere l'organizzazione di Office 365, è comunque possibile cadere vittima di un attacco [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) .</span><span class="sxs-lookup"><span data-stu-id="3a10e-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="3a10e-105">Ransomware è un'azienda di grandi dimensioni e gli attacchi sono verificati in una ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="3a10e-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="3a10e-106">Le procedure descritte in questo argomento offrono le migliori possibilità di recuperare i dati crittografati dal ransomware e aiutano a fermare la diffusione dell'infezione nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a10e-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="3a10e-107">Prima di iniziare, considera i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="3a10e-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="3a10e-108">Non vi è alcuna garanzia che il pagamento del riscatto restituirà l'accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="3a10e-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="3a10e-109">In effetti, pagare il riscatto può rendere un obiettivo per più ransomware.</span><span class="sxs-lookup"><span data-stu-id="3a10e-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="3a10e-110">Se si è già pagati, ma si è riusciti a recuperare i file senza dover utilizzare la risoluzione dell'utente malintenzionato, è necessario chiamare la banca per vedere se è possibile bloccare la transazione.</span><span class="sxs-lookup"><span data-stu-id="3a10e-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="3a10e-111">È inoltre consigliabile segnalare l'attacco ransomware alle forze dell'ordine, ai siti Web per la creazione di rapporti di truffa e Microsoft come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3a10e-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="3a10e-112">È molto importante rispondere rapidamente all'attacco e alle sue conseguenze.</span><span class="sxs-lookup"><span data-stu-id="3a10e-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="3a10e-113">Maggiore è l'attesa, minore è la probabilità che sia possibile ripristinare i dati interessati.</span><span class="sxs-lookup"><span data-stu-id="3a10e-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="3a10e-114">Passaggio 1: verificare i backup</span><span class="sxs-lookup"><span data-stu-id="3a10e-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="3a10e-115">Se si dispone di backup non in linea, è probabile che sia possibile ripristinare i dati crittografati **dopo** aver rimosso il payload ransomware (malware) dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a10e-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="3a10e-116">Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="3a10e-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="3a10e-117">Passaggio 2: disabilitare ActiveSync e la sincronizzazione di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3a10e-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="3a10e-118">Il punto chiave è l'interruzione della diffusione della crittografia dei dati da parte del ransomware.</span><span class="sxs-lookup"><span data-stu-id="3a10e-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="3a10e-119">Se si sospetta che la posta elettronica sia una destinazione, è necessario disabilitare temporaneamente l'accesso degli utenti alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="3a10e-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="3a10e-120">Exchange ActiveSync viene utilizzato dai dispositivi mobili per sincronizzare i dati tra il dispositivo e la cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3a10e-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="3a10e-121">Per disabilitare ActiveSync per una cassetta postale, vedere [la pagina relativa alla disattivazione di Exchange ActiveSync per gli utenti in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="3a10e-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="3a10e-122">Per disabilitare altri tipi di accesso a una cassetta postale, vedere:</span><span class="sxs-lookup"><span data-stu-id="3a10e-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="3a10e-123">[Abilitazione o disabilitazione di MAPI per una cassetta postale](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="3a10e-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="3a10e-124">Abilitazione o disabilitazione dell'accesso POP3 o IMAP4 per un utente</span><span class="sxs-lookup"><span data-stu-id="3a10e-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="3a10e-125">La sospensione di OneDrive Sync consentirà di proteggere i dati del cloud dall'aggiornamento da parte di dispositivi potenzialmente infetti.</span><span class="sxs-lookup"><span data-stu-id="3a10e-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="3a10e-126">Per ulteriori informazioni, vedere [How to pause and resume Sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="3a10e-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="3a10e-127">Passaggio 3: rimuovere il malware dai dispositivi coinvolti</span><span class="sxs-lookup"><span data-stu-id="3a10e-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="3a10e-128">Eseguire un'analisi antivirus completa con gli aggiornamenti più recenti su tutti i computer e i dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.</span><span class="sxs-lookup"><span data-stu-id="3a10e-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="3a10e-129">Non dimenticare i dispositivi che eseguono la sincronizzazione dei dati o l'obiettivo delle unità di rete mappate (anche tali computer e dispositivi devono essere analizzati).</span><span class="sxs-lookup"><span data-stu-id="3a10e-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="3a10e-130">È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per i client meno recenti) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="3a10e-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="3a10e-131">Un'alternativa che consente di rimuovere ransomware o malware è lo strumento per la [rimozione di software dannoso (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="3a10e-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="3a10e-132">Se queste opzioni non funzionano, è possibile provare [Windows Defender offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) o [risolvere i problemi relativi al rilevamento e alla rimozione di malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span><span class="sxs-lookup"><span data-stu-id="3a10e-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="3a10e-133">Passaggio 4: recuperare i file in un computer o dispositivo pulito</span><span class="sxs-lookup"><span data-stu-id="3a10e-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="3a10e-134">Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), è possibile utilizzare la [cronologia dei file](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 e Windows 8,1 o System Protection in Windows 7 per tentare di recuperare i file e le cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="3a10e-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="3a10e-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3a10e-135">**Notes**:</span></span>

- <span data-ttu-id="3a10e-136">Alcuni ransomware anche crittografare o eliminare le versioni di backup, quindi non è possibile utilizzare la cronologia dei file o la protezione del sistema per ripristinare i file.</span><span class="sxs-lookup"><span data-stu-id="3a10e-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="3a10e-137">In tal caso, è necessario utilizzare i backup su unità esterne o su dispositivi che non sono stati interessati dal ransomware o OneDrive, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="3a10e-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="3a10e-138">Se una cartella viene sincronizzata con OneDrive e non si utilizza la versione più recente di Windows, è possibile che vengano riportate alcune limitazioni tramite la cronologia dei file.</span><span class="sxs-lookup"><span data-stu-id="3a10e-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="3a10e-139">Passaggio 5: recuperare i file in OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="3a10e-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="3a10e-140">OneDrive for business consente di recuperare tutti i file archiviati in esso.</span><span class="sxs-lookup"><span data-stu-id="3a10e-140">OneDrive for Business will allow you to recover any files you have stored in it.</span></span> <span data-ttu-id="3a10e-141">Sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="3a10e-141">You have two options:</span></span>

- <span data-ttu-id="3a10e-142">Utilizzare il [sito Web OneDrive](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span><span class="sxs-lookup"><span data-stu-id="3a10e-142">Use the [OneDrive website](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span></span>

- <span data-ttu-id="3a10e-143">Se un numero elevato di file è stato influenzato, è possibile creare una richiesta di supporto per il ripristino di una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="3a10e-143">If a large number of files were affected, you can create a support request for a "Site Collection Restore".</span></span> <span data-ttu-id="3a10e-144">Questa richiesta è in grado di ripristinare i file da un massimo di 14 giorni nel passato.</span><span class="sxs-lookup"><span data-stu-id="3a10e-144">This request can restore files from up to 14 days in the past.</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="3a10e-145">Passaggio 6: recuperare il messaggio di posta elettronica eliminato</span><span class="sxs-lookup"><span data-stu-id="3a10e-145">Step 6: Recover deleted email</span></span>

<span data-ttu-id="3a10e-146">Nel caso raro che il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che gli elementi eliminati possano essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="3a10e-146">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="3a10e-147">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="3a10e-147">For more information, see:</span></span>

- [<span data-ttu-id="3a10e-148">Recupero dei messaggi eliminati nella cassetta postale di un utente</span><span class="sxs-lookup"><span data-stu-id="3a10e-148">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="3a10e-149">Ripristinare gli elementi eliminati in Outlook per Windows</span><span class="sxs-lookup"><span data-stu-id="3a10e-149">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="3a10e-150">Passaggio 7: riattivazione di Exchange ActiveSync e sincronizzazione di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3a10e-150">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="3a10e-151">Dopo aver pulito i computer e i dispositivi e aver recuperato i dati, è possibile riattivare ActiveSync e la sincronizzazione di OneDrive precedentemente disattivata nel [passaggio 2](#step-2-disable-activesync-and-onedrive-sync).</span><span class="sxs-lookup"><span data-stu-id="3a10e-151">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="3a10e-152">Passaggio 8 (facoltativo): bloccare la sincronizzazione di OneDrive per specifiche estensioni di file</span><span class="sxs-lookup"><span data-stu-id="3a10e-152">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="3a10e-153">Dopo aver recuperato, è possibile impedire ai client di OneDrive for business di sincronizzare i tipi di file che sono stati interessati da questo ransomware.</span><span class="sxs-lookup"><span data-stu-id="3a10e-153">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="3a10e-154">Per ulteriori informazioni, vedere [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="3a10e-154">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="3a10e-155">Segnalare l'attacco</span><span class="sxs-lookup"><span data-stu-id="3a10e-155">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="3a10e-156">Applicazione del diritto di contatto</span><span class="sxs-lookup"><span data-stu-id="3a10e-156">Contact law enforcement</span></span>

<span data-ttu-id="3a10e-157">È consigliabile contattare le agenzie di applicazione della legge locali o federali.</span><span class="sxs-lookup"><span data-stu-id="3a10e-157">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="3a10e-158">Ad esempio, se ci si trova negli Stati Uniti, è possibile contattare l' [ufficio del campo locale dell'FBI](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) o il [servizio segreto](http://www.secretservice.gov/).</span><span class="sxs-lookup"><span data-stu-id="3a10e-158">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="3a10e-159">Inviare un rapporto al sito Web di segnalazione Scam del proprio paese</span><span class="sxs-lookup"><span data-stu-id="3a10e-159">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="3a10e-160">I siti Web per la creazione di rapporti di truffa forniscono informazioni su come prevenire ed evitare truffe.</span><span class="sxs-lookup"><span data-stu-id="3a10e-160">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="3a10e-161">Essi forniscono anche meccanismi per segnalare se si è vittima di truffa.</span><span class="sxs-lookup"><span data-stu-id="3a10e-161">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="3a10e-162">Australia: [ScamWatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-162">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="3a10e-163">Canada: [centro per la lotta antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-163">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="3a10e-164">Francia: [Agence Nationale de la sécurité des Systèmes d'Information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-164">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="3a10e-165">Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="3a10e-165">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="3a10e-166">Irlanda: [An Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-166">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="3a10e-167">Nuova Zelanda: [truffe per gli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="3a10e-167">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="3a10e-168">Regno Unito: [frode d'azione](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-168">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="3a10e-169">Stati Uniti: [on Guard online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="3a10e-169">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="3a10e-170">Se il paese non è elencato, chiedere alle agenzie di applicazione della legge federali o locali.</span><span class="sxs-lookup"><span data-stu-id="3a10e-170">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="3a10e-171">Inviare messaggi di posta elettronica a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a10e-171">Submit email messages to Microsoft</span></span>

<span data-ttu-id="3a10e-172">È possibile segnalare un messaggio di phishing che contiene ransomware seguendo le istruzioni riportate in [inviare messaggi di posta indesiderata, non indesiderati e tentativi di phishing a Microsoft per l'analisi](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="3a10e-172">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a10e-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a10e-173">See also</span></span>

- [<span data-ttu-id="3a10e-174">Il ransomware</span><span class="sxs-lookup"><span data-stu-id="3a10e-174">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="3a10e-175">Risposta ransomware-da pagare o non pagare?</span><span class="sxs-lookup"><span data-stu-id="3a10e-175">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="3a10e-176">Norsk Hydro risponde all'attacco ransomware con trasparenza</span><span class="sxs-lookup"><span data-stu-id="3a10e-176">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="3a10e-177">Rilevamento ransomware e ripristino dei file in OneDrive</span><span class="sxs-lookup"><span data-stu-id="3a10e-177">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="3a10e-178">Report di intelligence sulla sicurezza di Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a10e-178">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="3a10e-179">Abilitare o disabilitare le macro nei file di Office</span><span class="sxs-lookup"><span data-stu-id="3a10e-179">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="3a10e-180">Impostazioni consigliate per la sicurezza ATP di EOP e Office 365</span><span class="sxs-lookup"><span data-stu-id="3a10e-180">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="3a10e-181">Un aggiornamento meritevole: la sicurezza di Next-gen su Windows 10 risulta resiliente rispetto ai focolai di ransomware nel 2017</span><span class="sxs-lookup"><span data-stu-id="3a10e-181">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="3a10e-182">No Mas, Samas: cosa c'è in questo modus operandi del ransomware?</span><span class="sxs-lookup"><span data-stu-id="3a10e-182">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="3a10e-183">Malware Locky, fortunato per evitarlo</span><span class="sxs-lookup"><span data-stu-id="3a10e-183">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="3a10e-184">MSRT 2016 luglio: cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="3a10e-184">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="3a10e-185">Le tre teste di Cerberus-like cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="3a10e-185">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="3a10e-186">Troldesh ransomware influenzato dal codice da Vinci (il)</span><span class="sxs-lookup"><span data-stu-id="3a10e-186">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)