---
title: Modificare i server dei nomi per configurare Microsoft con namecheap
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Informazioni su come configurare il dominio personalizzato Microsoft con namecheap se si desidera che la gestione dei record DNS venga gestita da Microsoft. '
ms.openlocfilehash: 55fde3b0db960d78ad77c9f9189c5367de16c73f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400618"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Modificare i server dei nomi per configurare Microsoft con namecheap

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.
  
Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito. Se si preferisce, è possibile [gestire tutti i record Microsoft DNS in Namecheap](create-dns-records-at-namecheap.md).
  
    
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

1. Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selezionare **DNS avanzato**.
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. Nella sezione **Host Records** selezionare **Aggiungi nuovo record**.
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. Nell'elenco a discesa **Type** selezionare **TXT Record**.
    
    > [!NOTE]
    > L'elenco a discesa **tipo** viene visualizzato automaticamente quando si seleziona **Aggiungi nuovo record**.
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    Scegliere il valore **TTL** nell'elenco a discesa. 
    
|**Tipo**|**Host**|**Valore**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota**: questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |30 min  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Selezionare il controllo **Salva modifiche** (segno di spunta). 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record dei server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft. Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio. Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain* . com) inizierà a venire a Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
>  Una volta completata la procedura descritta in questa sezione, dovrebbero essere elencati  *solo*  questi quattro server dei nomi: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  La seguente procedura illustra come eliminare eventuali altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi  *corretti*  se non sono presenti nell'elenco. 
  
1. Per iniziare, passare alla propria pagina dei domini su Namecheap usando [questo collegamento](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Verrà richiesto di eseguire l'accesso e continuare.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Nella pagina di **destinazione** , in **account**, scegliere **Domain List** nell'elenco a discesa. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Nella pagina **elenco dei domini** trovare il nome del dominio che si desidera modificare, quindi selezionare **Gestisci**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selezionare **dominio**.
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Trovare la sezione **NAMESERVERS** e quindi selezionare **Custom** dall'elenco a discesa **Namecheap Default**. 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. A seconda del fatto che siano già presenti o meno i server dei nomi elencati nella pagina visualizzata, continuare con una delle due procedure seguenti.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NON sono già elencati server dei nomi
<a name="BKMK_ProcedureWithOUT"> </a>

1. Fare doppio clic su **Aggiungi server dei nomi** per aggiungere due nuove righe.
    
    ![Namecheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. Nelle caselle **Nameserver** digitare oppure copiare e incollare i valori della tabella seguente.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Selezionare il controllo **Salva** (segno di spunta). 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se SONO già elencati server dei nomi

> [!CAUTION]
> Seguire questa procedura  *solo*  se sono presenti server dei nomi diversi dai quattro server dei nomi  *corretti*  . In altre parole, eliminare  *solo*  eventuali server dei nomi  *diversi*  da **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**. 
  
1. Se sono già elencati altri server dei nomi nelle caselle **Nameserver**, eliminarli selezionando ogni server e premendo **CANC**. 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Fare doppio clic su **Aggiungi server dei nomi** per aggiungere due nuove righe. 
    
    ![Namecheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. Nelle caselle **Nameserver** digitare oppure copiare e incollare i valori della tabella seguente.
 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Selezionare il controllo **Salva** (segno di spunta). 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.
