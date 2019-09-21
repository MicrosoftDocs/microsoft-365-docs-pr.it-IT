---
title: Importare in blocco i contatti esterni in Exchange Online
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
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083253"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Importare in blocco i contatti esterni in Exchange Online

**Questo articolo è per gli amministratori. Si sta tentando di importare i contatti nella propria cassetta postale? Vedere [importare i contatti in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
L'azienda dispone di un numero elevato di contatti aziendali esistenti che si desidera includere nella rubrica condivisa (denominato anche elenco indirizzi globale) in Exchange Online? Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, proprio come è possibile con gli utenti all'interno dell'azienda? In tal caso, è possibile utilizzare PowerShell di Exchange Online e un file CSV (con valori delimitati da virgole) per importare in blocco i contatti esterni in Exchange Online. Si tratta di un processo in tre fasi:
  
[Passaggio 1: creare un file CSV contenente informazioni sui contatti esterni](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Passaggio 2: creare i contatti esterni con PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Passaggio 3: aggiungere informazioni alle proprietà dei contatti esterni](#step-3-add-information-to-the-properties-of-the-external-contacts)

Dopo aver completato questa procedura per importare i contatti, è possibile eseguire queste attività aggiuntive:
  
- [Aggiungere altri contatti esterni](#add-more-external-contacts)
  
- [Nascondere i contatti esterni dalla rubrica condivisa](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Passaggio 1: creare un file CSV contenente informazioni sui contatti esterni

Il primo passaggio consiste nel creare un file CSV che contiene informazioni su ogni contatto esterno che si desidera importare in Exchange Online. 
  
1. Copiare il testo seguente in un file di testo in blocco note e salvarlo sul desktop come file CSV utilizzando un suffisso del nome file CSV. ad esempio, ExternalContacts. csv.
    
    > [!TIP]
    > Se la lingua contiene caratteri speciali, ad esempio **å**, **ä**e **ö** in svedese, salvare il file CSV con UTF-8 o altra codifica Unicode quando si salva il file nel blocco note. 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    La prima riga, o riga di intestazione, del file CSV elenca le proprietà dei contatti che è possibile utilizzare quando vengono importati in Exchange Online. Ogni nome di proprietà è separato da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un singolo contatto esterno. 
    
    > [!NOTE]
    > Questo testo include dati di esempio, che è possibile eliminare. Ma non eliminare o modificare la prima riga (intestazione). Contiene tutte le proprietà dei contatti esterni. 
  
2. Aprire il file CSV in Microsoft Excel per modificare il file CSV, perché è molto più facile usare Excel per modificare il file CSV.
    
3. Creare una riga per ogni contatto che si desidera importare in Exchange Online. Inserire il numero di celle possibile. Queste informazioni vengono visualizzate nella rubrica condivisa per ogni contatto. 
    
    > [!IMPORTANT]
    >  Le proprietà seguenti, che sono i primi quattro elementi della riga di intestazione, sono necessarie per creare un contatto esterno e devono essere inserite nel file CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. Il comando di PowerShell eseguito nel passaggio 2 utilizzerà i valori per queste proprietà per creare i contatti. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Passaggio 2: creare i contatti esterni con PowerShell

Il passaggio successivo consiste nell'utilizzare il file CSV creato nel passaggio 1 e PowerShell per importare in blocco i contatti esterni elencati nel file CSV in Exchange Online. 
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Assicurarsi di utilizzare il nome utente e la password per l'account di amministratore globale di Office 365 quando ci si connette a PowerShell di Exchange Online. 
    
2. Dopo aver connesso PowerShell a Exchange Online, passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad esempio `C:\Users\Administrator\desktop`.
    
3. Per creare i contatti esterni, eseguire il comando riportato di seguito:

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Potrebbe essere necessario un po' di tempo per creare i nuovi contatti, a seconda del numero di importazione. Al termine dell'esecuzione del comando, PowerShell Visualizza un elenco dei nuovi contatti che sono stati creati. 
    
4. Per visualizzare i nuovi contatti esterni, accedere all'interfaccia di amministrazione di Exchange (EAC) e quindi fare clic su **destinatari** \> **contatti**. 
    
    > [!TIP]
    > Per istruzioni sulla connessione a EAC, vedere interfaccia di [amministrazione di Exchange in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Se necessario **, fare clic su** ![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare l'elenco e vedere i contatti esterni che sono stati importati. 
    
    I contatti importati verranno visualizzati nella rubrica condivisa in Outlook e Outlook sul Web.
    
    > [!NOTE]
    > È inoltre possibile visualizzare i contatti nell'interfaccia di amministrazione di Microsoft 365 accedendo ai **contatti** **degli utenti** \> . 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Passaggio 3: aggiungere informazioni alle proprietà dei contatti esterni

Dopo aver eseguito il comando nel passaggio 2, vengono creati i contatti esterni, ma non contengono alcuna informazione del contatto o dell'organizzazione, ovvero le informazioni provenienti dalla maggior parte delle celle nel file CSV. Ciò è dovuto al fatto che, quando si creano nuovi contatti esterni, vengono inserite solo le proprietà obbligatorie. Non si preoccupi se non si dispone di tutte le informazioni inserite nel file CSV. Se non è presente, non verrà aggiunta.
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad esempio `C:\Users\Administrator\desktop`.
    
3. Eseguire i due comandi seguenti per aggiungere le altre proprietà dal file CSV ai contatti esterni creati nel passaggio 2.
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Il parametro _Manager_ potrebbe essere problematico. Se la cella è vuota nel file CSV, verrà visualizzato un messaggio di errore e nessuna delle informazioni sulle proprietà verrà aggiunta al contatto. Se non è necessario specificare un Manager, è sufficiente eliminare ` -Manager $_.Manager ` il comando PowerShell precedente. 
  
    Anche in questo caso, potrebbe essere necessario un po' di tempo per aggiornare i contatti, a seconda del numero di importati nel passaggio 1. 
    
4. Per verificare che le proprietà siano state aggiunte ai contatti: 
    
1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.
    
2. Fare clic su un contatto e **** ![quindi fare clic](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) su Modifica icona modifica per visualizzare le proprietà del contatto. 
    
È tutto. Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella Rubrica Outlook e Outlook sul Web.
  
## <a name="add-more-external-contacts"></a>Aggiungere altri contatti esterni

È possibile ripetere i passaggi da 1 a passaggio 3 per aggiungere nuovi contatti esterni in Exchange Online. L'utente o gli utenti dell'azienda possono semplicemente aggiungere una nuova riga nel file CSV per il nuovo contatto. È quindi possibile eseguire i comandi di PowerShell del passaggio 2 e del passaggio 3 per creare e aggiungere informazioni ai nuovi contatti.
  
> [!NOTE]
> Quando si esegue il comando per creare nuovi contatti, è possibile che venga visualizzato un messaggio di errore che indica che i contatti creati precedentemente sono già esistenti. Tuttavia, viene creato un nuovo contatto aggiunto al file CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Nascondere i contatti esterni dalla rubrica condivisa>

Alcune aziende possono utilizzare i contatti esterni solo in modo che possano essere aggiunti come membri dei gruppi di distribuzione. In questo scenario, è possibile che si desideri nascondere i contatti esterni dalla rubrica condivisa. Ecco come:
  
1.  Connettere PowerShell all'organizzazione di Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Per nascondere un singolo contatto esterno, eseguire il comando riportato di seguito.
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    Ad esempio, per nascondere Pilar Pinilla dalla rubrica condivisa, eseguire il comando seguente:

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. Per nascondere tutti i contatti esterni dalla rubrica condivisa, eseguire il comando seguente:

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Dopo averli nascosti, i contatti esterni non vengono visualizzati nella rubrica condivisa, ma è comunque possibile aggiungerli come membri di un gruppo di distribuzione.
