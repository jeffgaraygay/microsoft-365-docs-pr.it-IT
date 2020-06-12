---
title: Gestire gli URL e i file bloccati e consentiti nell'elenco Consenti/blocca tenant
f1.keywords:
- NOCSH
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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono ottenere informazioni su come configurare le voci di URL e file nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance.
ms.openlocfilehash: 0143ee2601a4cb9593c79f8c6c62d1f06914088f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613421"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>Gestire gli URL e i file nell'elenco Consenti/blocca tenant

> [!NOTE]
> Le funzionalità descritte in questo argomento sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP. Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).

L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365. L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su. È possibile specificare gli URL e i file da consentire o bloccare nell'elenco tenant Allow/Block.

In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .

- È possibile specificare i file utilizzando il valore hash SHA256 del file. Per trovare il valore hash di SHA256 di un file in Windows, al prompt dei comandi eseguire il comando seguente:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . I valori dell'hash percettivo (pHash) non sono consentiti.

- I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.

- L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.

- Una voce dovrebbe essere attiva entro 15 minuti.

- Le voci di blocco hanno la precedenza su Consenti voci.

- Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni. È possibile specificare una data o impostarla in modo che non scada mai.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant

Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.

1. Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.

2. Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**

3. Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:

   - **Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.

   - **Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.

   - Non **scade mai**: eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.

     oppure

     - Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai: ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Nota facoltativa**: immettere il testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per creare voci di file nell'elenco Consenti/blocca tenant

1. Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.

2. Nella pagina **elenco Consenti/blocca tenant** selezionare scheda **file** e quindi fare clic su **Aggiungi**.

3. Nel riquadro a comparsa dei **nuovi file** che viene visualizzato, configurare le seguenti impostazioni:

   - **Aggiungere gli hash dei file**: immettere un valore hash SHA256 per riga, fino a un massimo di 20.

   - **Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** i file specificati.

   - Non **scade mai**: eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.

     oppure

     - Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai: ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Nota facoltativa**: immettere il testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per visualizzare le voci di URL e file nell'elenco Consenti/blocca tenant

1. Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.

2. Selezionare la scheda **URL** o la scheda **file** .

Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:

- **Valore**: l'URL o il file hash.
- **Azione**: **blocca** o **Consenti**.
- **Data dell'ultimo aggiornamento**
- **Data di scadenza**
- **Nota**

Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.

Fare clic su **ricerca**, immettere tutto o parte di un valore URL o file e quindi premere INVIO per trovare un valore specifico. Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.

Fare clic su **filtro**. Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:

- **Azione**: selezionare **Consenti**, **blocca** o entrambi.

- **Non scade mai**: selezionare disattivata (disattivazione ![ ](../../media/scc-toggle-off.png) ) o attivata ( ![ attiva o disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.

- **Data di scadenza**: selezionare una data di inizio (**da**), una data**di**fine (a) o entrambe.

Al termine, fare clic su **applica**.

Per cancellare i filtri esistenti, fare clic su **filtro**e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per modificare le voci di URL e file nell'elenco Consenti/blocca tenant

Non è possibile modificare l'URL o il valore del file stesso. Al contrario, è necessario eliminare la voce e ricrearla.

1. Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.

2. Selezionare la scheda **URL** o la scheda **file** .

3. Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:

   - **Blocca/Consenti**: selezionare **Consenti** o **blocca**.

   - Non **scade mai**: eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.

     oppure

     - Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai: ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Nota facoltativa**: immettere il testo descrittivo per la voce.

5. Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant

1. Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.

2. Selezionare la scheda **URL** o la scheda **file** .

3. Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>Utilizzo di PowerShell per aggiungere URL e voci di file nell'elenco Consenti/blocca tenant

Per aggiungere voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com). Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In questo esempio viene aggiunta una voce Consenti file per i file specificati che non scadono mai.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Utilizzo di PowerShell per visualizzare le voci degli URL e dei file nell'elenco Consenti/blocca tenant

Per visualizzare le voci relative a URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In questo esempio vengono restituiti tutti gli URL bloccati.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

In questo esempio vengono restituite le informazioni relative al valore hash del file specificato.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Utilizzo di PowerShell per modificare le voci di URL e file nell'elenco Consenti/blocca tenant

Non è possibile modificare l'URL o il valore del file stesso. Al contrario, è necessario eliminare la voce e ricrearla.

Per modificare le voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In questo esempio viene modificata la data di scadenza della voce specificata.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Utilizzo di PowerShell per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant

Per rimuovere l'URL e le voci di file dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintassi URL per l'elenco Consenti/blocca tenant

- Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.

- Le estensioni dei nomi di file non sono consentite (ad esempio, test. pdf).

- Unicode non è supportato, ma Punycode è.

- I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:

  - Il nome host contiene un punto.
  - Vi è almeno un carattere a sinistra del punto.
  - A destra del punto sono presenti almeno due caratteri.

  Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.

- I sottopercorsi non sono impliciti.

  Ad esempio, `contoso.com` non include `contoso.com/a` .

- I caratteri jolly (*) sono consentiti negli scenari seguenti:

  - Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.

    Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.

  - Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.

    Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.

  - Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.

    Ad esempio, `contoso.com/*` non include `contoso.com/a` .

  - `*.com*`non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).

  - I caratteri jolly non sono consentiti negli indirizzi IP.

- Il carattere tilde (~) è disponibile negli scenari seguenti:

  - Una tilde sinistra implica un dominio e tutti i sottodomini.

    Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .

- Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.

- Un nome utente o una password non sono supportati o richiesti.

- Le virgolette (' or ') sono caratteri non validi.

- Un URL deve includere tutti i reindirizzamenti laddove possibile.

### <a name="url-entry-scenarios"></a>Scenari di immissione URL

Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.

#### <a name="scenario-no-wildcards"></a>Scenario: nessun carattere jolly

**Voce**:`contoso.com`

- **Consenti corrispondenza**: contoso.com

- **Consenti non confrontato**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
- **Blocca corrispondenza**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Blocca non confrontato**: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: carattere jolly sinistro (sottodominio)

**Voce**:`*.contoso.com`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Consenti non corrispondente** e **non corrisponde**a un blocco:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: carattere jolly destro nella parte superiore del percorso

**Voce**:`contoso.com/a/*`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = joe@t. com

- **Consenti non corrispondente** e **non corrisponde**a un blocco:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
#### <a name="scenario-left-tilde"></a>Scenario: tilde sinistra

**Voce**:`~contoso.com`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Consenti non corrispondente** e **non corrisponde**a un blocco:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: suffisso con caratteri jolly giusti

**Voce**:`contoso.com/*`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Consenti non corrispondente** e **blocco non corrispondente**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro

**Voce**:`*.contoso.com/*`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: tilde sinistro e destro

**Voce**:`~contoso.com~`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Consenti non corrispondente** e **non corrisponde**a un blocco:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: indirizzo IP

**Voce**:`1.2.3.4`

- **Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4

- **Consenti non corrispondente** e **non corrisponde**a un blocco:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Indirizzo IP con carattere jolly destro

**Voce**:`1.2.3.4/*`

- **Consenti** corrispondenza e **blocca corrispondenza**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Esempi di voci non valide

Le voci seguenti non sono valide:

- **Valori di dominio mancanti o non validi**:

  - contoso
  - \*contoso.\*
  - \*. com
  - \*.pdf

- **Carattere jolly su testo o senza caratteri di spaziatura**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Indirizzi IP con porte**:

  - contoso.com:443
  - abc.contoso.com:25

- **Caratteri jolly non descrittivi**:

  - \*
  - \*.\*

- **Caratteri jolly intermedi**:

  - conto \* so.com
  - conto ~ so. com

- **Caratteri jolly doppi**

  - contoso.com/\*\*
  - contoso.com/\*/\*