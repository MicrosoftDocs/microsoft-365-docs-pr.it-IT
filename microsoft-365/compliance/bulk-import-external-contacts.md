---
title: Importazione in blocco dei contatti esterni in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Informazioni su come gli amministratori possono utilizzare PowerShell di Exchange Online e un file CSV per importare in blocco i contatti esterni nell'elenco indirizzi globale.
ms.openlocfilehash: 4d0b1a826583a032fd27c216367e99a6b7f8b371
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636344"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importazione in blocco dei contatti esterni in Exchange Online

**Questo articolo è per gli amministratori. Si sta tentando di importare i contatti nella propria cassetta postale? Vedere [Importare contatti in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
L'azienda ha molti contatti aziendali esistenti che si desidera includere nella rubrica condivisa (denominato anche elenco indirizzi globale) in Exchange Online? Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, proprio come con gli utenti all'interno dell'azienda? In tal caso, è possibile utilizzare PowerShell di Exchange Online e un file CSV (con valori delimitati da virgole) per importare in blocco i contatti esterni in Exchange Online. Si tratta di un processo in tre passaggi:
  
[Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Passaggio 2: Creare i contatti esterni con PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni](#step-3-add-information-to-the-properties-of-the-external-contacts)

Dopo aver completato questi passaggi per importare i contatti, è possibile eseguire queste attività aggiuntive:
  
- [Aggiungere altri contatti esterni](#add-more-external-contacts)
  
- [Nascondere i contatti esterni dalla rubrica condivisa](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni

Il primo passaggio consiste nel creare un file CSV contenente informazioni su ogni contatto esterno che si desidera importare in Exchange Online. 
  
1. Copiare il testo seguente in un file di testo in NotePad e salvarlo sul desktop come file CSV utilizzando il suffisso del nome file csv. ad esempio, ExternalContacts.csv.
    
    > [!TIP]
    > Se la lingua contiene caratteri speciali (ad esempio **å,** **ä** e **ö** in svedese) salvare il file CSV con codifica UTF-8 o Unicode quando si salva il file in NotePad. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    Nella prima riga, o riga di intestazione, del file CSV sono elencate le proprietà dei contatti che possono essere utilizzate quando vengono importati in Exchange Online. Ogni nome di proprietà è separato da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un singolo contatto esterno. 
    
    > [!NOTE]
    > Questo testo include dati di esempio che puoi eliminare. Non eliminare o modificare la prima riga (intestazione). Contiene tutte le proprietà per i contatti esterni. 
  
2. Aprire il file CSV in Microsoft Excel per modificare il file CSV perché è molto più facile usare Excel per modificare il file CSV.
    
3. Creare una riga per ogni contatto che si desidera importare in Exchange Online. Popolare il maggior numero possibile di celle. Queste informazioni verranno visualizzate nella rubrica condivisa per ogni contatto. 
    
    > [!IMPORTANT]
    >  Le proprietà seguenti( che sono i primi quattro elementi nella riga di intestazione) sono necessarie per creare un contatto esterno e devono essere popolate nel file CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Il comando di PowerShell eseguito nel passaggio 2 utilizzerà i valori per queste proprietà per creare i contatti. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Passaggio 2: Creare i contatti esterni con PowerShell

Il passaggio successivo consiste nell'usare il file CSV creato nel passaggio 1 e PowerShell per importare in blocco i contatti esterni elencati nel file CSV in Exchange Online. 
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Assicurarsi di utilizzare il nome utente e la password per l'account amministratore globale quando ci si connette a PowerShell di Exchange Online. 
    
2. Dopo aver connesso PowerShell a Exchange Online, passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop` .
    
3. Eseguire il comando seguente per creare i contatti esterni:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    La creazione dei nuovi contatti potrebbe richiedere del tempo, a seconda del numero di contatti da importare. Al termine dell'esecuzione del comando, PowerShell visualizza un elenco dei nuovi contatti creati. 
    
4. Per visualizzare i nuovi contatti esterni, accedere all'interfaccia di amministrazione di Exchange (EAC), quindi fare clic su **Destinatari** \> **Contatti.** 
    
    > [!TIP]
    > Per istruzioni sulla connessione all'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=328197) 
  
5. Se necessario, fare **clic su** Aggiorna per aggiornare l'elenco e visualizzare i contatti esterni importati. 
    
    I contatti importati verranno visualizzati nella rubrica condivisa in Outlook e Outlook sul Web.
    
    > [!NOTE]
    > È anche possibile visualizzare i contatti nell'interfaccia di amministrazione di Microsoft 365 andando a **Contatti** \> **degli utenti.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni

Dopo aver eseguito il comando nel passaggio 2, i contatti esterni vengono creati, ma non contengono alcuna informazione sul contatto o sull'organizzazione, ovvero le informazioni della maggior parte delle celle nel file CSV. Questo perché quando si creano nuovi contatti esterni, vengono popolate solo le proprietà necessarie. Non c'è da preoccuparsi se non hai tutte le informazioni inserite nel file CSV. Se non è presente, non verrà aggiunto.
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad esempio `C:\Users\Administrator\desktop` .
    
3. Eseguire i due comandi seguenti per aggiungere le altre proprietà del file CSV ai contatti esterni creati nel passaggio 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Il  _parametro Manager_ potrebbe essere problematico. Se la cella è vuota nel file CSV, verrà visualizzato un errore e nessuna delle informazioni sulle proprietà verrà aggiunta al contatto. Se non è necessario specificare un manager, basta eliminare  ` -Manager $_.Manager ` dal comando PowerShell precedente. 
  
    Anche in questo caso, l'aggiornamento dei contatti potrebbe richiedere del tempo, a seconda del numero di contatti importati nel passaggio 1. 
    
4. Per verificare che le proprietà siano state aggiunte ai contatti: 
    
1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.
    
2. Fare clic su un contatto e quindi **sull'icona** ![ Modifica per visualizzare le proprietà del ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) contatto. 
    
È tutto. Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella rubrica di Outlook e Outlook sul Web.
  
## <a name="add-more-external-contacts"></a>Aggiungere altri contatti esterni

È possibile ripetere i passaggi da 1 a 3 per aggiungere nuovi contatti esterni in Exchange Online. Gli utenti dell'azienda possono semplicemente aggiungere una nuova riga nel file CSV per il nuovo contatto. È quindi possibile eseguire i comandi di PowerShell dai passaggi 2 e 3 per creare e aggiungere informazioni ai nuovi contatti.
  
> [!NOTE]
> Quando si esegue il comando per creare nuovi contatti, potrebbe essere visualizzato un errore che indica che i contatti creati in precedenza esistono già. Tuttavia, viene creato qualsiasi nuovo contatto aggiunto al file CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Nascondere i contatti esterni dalla rubrica condivisa>

Alcune società possono utilizzare solo contatti esterni in modo che possano essere aggiunti come membri dei gruppi di distribuzione. In questo scenario, potrebbero voler nascondere i contatti esterni dalla rubrica condivisa. Ecco come:
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Per nascondere un singolo contatto esterno, eseguire il comando seguente.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Ad esempio, per nascondere Pilar Pinilla dalla rubrica condivisa, eseguire questo comando:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Per nascondere tutti i contatti esterni dalla rubrica condivisa, eseguire questo comando:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Dopo averli nascosti, i contatti esterni non vengono visualizzati nella rubrica condivisa, ma è comunque possibile aggiungerli come membri di un gruppo di distribuzione.
