---
title: Gestione utenti di posta in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP).
ms.openlocfilehash: d445bceb9e796c11c40ab778ed3d056df0f4c44b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084726"
---
# <a name="manage-mail-users-in-eop"></a>Gestire utenti di posta in Exchange Online Protection

La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP). In EOP è possibile gestire gli utenti in diversi modi.
  
- Utilizzare la sincronizzazione della directory per gestire gli utenti di posta: se in azienda sono presenti account utente in un ambiente di Active Directory locale, è possibile sincronizzarli con Azure Active Directory (AD), dove una copia di tali account è memorizzata nel cloud. Durante la sincronizzazione degli account utente esistenti su Azure Active Directory, è possibile visualizzare tali utenti nel riquadro **Destinatari** nell'interfaccia di amministrazione di Exchange (EAC). Si consiglia di utilizzare la sincronizzazione delle directory. 

- Utilizzare il valore EAC per gestire gli utenti di posta: aggiungere e gestire gli utenti di posta direttamente in EAC. Si tratta del modo più semplice per aggiungere utenti di posta elettronica ed è utile per aggiungere un utente alla volta.

- Utilizzare Windows PowerShell remoto per gestire gli utenti di posta elettronica: aggiungere e gestire utenti di posta elettronica eseguendo Windows PowerShell remoto. Questo metodo è utile per aggiungere più record e creare script.

> [!NOTE]
> È possibile aggiungere utenti nell'interfaccia di amministrazione di Microsoft 365, ma questi utenti non possono essere utilizzati come destinatari della posta.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).

- Tenere presente che quando si creano utenti di posta elettronica utilizzando i cmdlet di PowerShell di Exchange Online Protection, è possibile che si verifichi la limitazione.

- I comandi di PowerShell riportati in questo argomento utilizzano un metodo di elaborazione batch che genera un ritardo di propagazione di alcuni minuti prima che i risultati dei comandi siano visibili.

- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizzare la sincronizzazione della directory per gestire gli utenti di posta

Nella presente sezione vengono fornite informazioni sulla gestione degli utenti di posta elettronica utilizzando la sincronizzazione della directory.
  
> [!NOTE]
> Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale. Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud. <br/><br/> La sincronizzazione della directory è consigliata per l'utilizzo con le caratteristiche seguenti: <br/><br/>• **Outlook safe sender e gli elenchi di mittenti bloccati**: quando vengono sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di posta indesiderata nel servizio. Ciò consente agli utenti di gestire i propri elenchi di utenti attendibili o bloccati a livello di organizzazione o a livello di singolo utente. <br/><br/>• **Directory based Edge Blocking (DBEB)**: per ulteriori informazioni su DBEB, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). <br/><br/>• **Quarantena della posta indesiderata dell'utente finale**: per accedere alla quarantena della posta indesiderata dell'utente finale, gli utenti finali devono disporre di un ID utente e una password di Office 365 validi. I clienti EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi. <br/><br/>• **Regole del flusso di posta**: quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare regole del flusso di posta (note anche come regole di trasporto) che si rivolgono a utenti specifici e/o gruppi senza dover aggiungerli manualmente tramite l'EAC o Exchange Online Protection PowerShell. Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://go.microsoft.com/fwlink/?LinkId=507569) tramite la sincronizzazione delle directory.
  
Ottenere le autorizzazioni necessarie e preparare la sincronizzazione della directory, come descritto in [Preparazione della sincronizzazione della directory](https://go.microsoft.com/fwlink/p/?LinkId=308908).
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Per sincronizzare le directory degli utenti con Azure Active Directory Connect (AAD Connect)

Per sincronizzare gli utenti con Azure Active Directory (AAD), è necessario innanzitutto **attivare la sincronizzazione della directory**, come descritto in [Activate Synchronization directory](https://go.microsoft.com/fwlink/p/?LinkId=308909).

La successiva è l'installazione e la configurazione di un computer locale per l'esecuzione di AAD Connect (se non è già presente una--una cosa degna di essere verificata in anticipo). La [configurazione di AAD Connect, l'argomento Express Way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) spiega come configurare e sincronizzare gli account da locale AD Azure ad con AAD Connect.

Tuttavia, prima di eseguire tale operazione, accertarsi di [rispettare i prerequisiti](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)e [scegliere il tipo di installazione](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation). Il collegamento precedente è un breve articolo relativo all'installazione espressa. Se necessario, è possibile trovare anche articoli su [installazioni personalizzate](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)o [l'autenticazione pass-through](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) .

> [!IMPORTANT]
> Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.

Dopo aver configurato la sincronizzazione, accertarsi di verificare che EOP sia sincronizzato correttamente. In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.

## <a name="use-the-eac-to-manage-mail-users"></a>Utilizzare il valore EAC per gestire gli utenti di posta

In questa sezione vengono fornite informazioni sull'aggiunta e la gestione degli utenti di posta elettronica direttamente in EAC.
  
### <a name="use-the-eac-to-add-a-mail-user"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per aggiungere un utente di posta elettronica

1. Per creare un utente di posta elettronica, andare a **Destinatari** \> **Contatti** in EAC, quindi fare clic su **Nuovo +**.

2. Nella pagina **Nuovo utente di posta**, immettere le informazioni dell'utente, incluse le seguenti: 

   ****

   |**Proprietà utente della posta**|**Descrizione**|
   |:-----|:-----|
   |**Nome**, **Iniziali**, and **Cognome**|Digitare il nome completo dell'utente nelle caselle appropriate.|
   |**Nome visualizzato**|Digitare un nome, utilizzando un massimo di 64 caratteri. Per impostazione predefinita, questa casella contiene i nomi nelle caselle **Nome**, **Iniziali** e **Cognome**. Il nome visualizzato è obbligatorio.  |
   |**Alias**|Digitare un alias univoco per l'utente, utilizzando un massimo di 64 caratteri. L'alias è obbligatorio.|
   |**Indirizzo di posta elettronica esterno**|Digitare l'indirizzo di posta elettronica esterno dell'utente.|
   |**ID utente**|Digitare il nome utilizzato dall'utente di posta per accedere al servizio. Il nome di accesso dell'utente è costituito da un nome utente a sinistra del simbolo @ e da un suffisso a destra del simbolo. In genere, il suffisso è costituito dal nome di dominio in cui risiede l'account utente.|
   |**Nuova password**|Digitare la password utilizzata dall'utente di posta per accedere al servizio. Verificare che la password immessa sia conforme ai requisiti di lunghezza, complessità e cronologia del dominio in cui viene creato l'account utente.|
   |**Conferma password**|Digitare nuovamente la password per confermarla.|

3. Fare clic su **Salva** per creare il nuovo utente di posta elettronica. Il nuovo utente viene visualizzato nell'elenco utenti.

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per modificare o rimuovere un utente di posta elettronica

- Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**. Nell'elenco degli utenti, fare clic sull'utente che si desidera visualizzare o modificare, quindi selezionare **modifica** ![icona](../media/ITPro-EAC-EditIcon.gif) modifica per aggiornare le impostazioni utente in base alle esigenze. È possibile modificare il nome utente, l'alias o le informazioni di contatto e registrare le informazioni dettagliate sul ruolo dell'utente nell'organizzazione. È inoltre possibile selezionare un utente e quindi scegliere **Rimuovi** ![icona](../media/ITPro-EAC-RemoveIcon.gif) Rimuovi per eliminarlo. 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Utilizzare PowerShell di Exchange Online Protection per gestire gli utenti di posta elettronica

In questa sezione vengono fornite informazioni sull'aggiunta e sulla gestione degli utenti di posta elettronica mediante l'utilizzo di Windows PowerShell remoto.
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a>Utilizzo di EOP PowerShell per aggiungere un utente di posta elettronica
  
In questo esempio viene utilizzato il cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) per creare un account utente abilitato alla posta elettronica per Jeffrey Zeng in EOP con i seguenti dettagli:
  
- Il nome è Jeffrey e il cognome è Zeng.

- Il nome è Jeffrey e il nome visualizzato è Jeffrey Zeng.

- L'alias è jeffreyz.

- L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.

- La firma di Office 365 nel nome è jeffreyz@contoso.onmicrosoft.com.

- La password è Pa$$word1.

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

Per verificare la corretta esecuzione, eseguire il comando riportato di seguito per visualizzare le informazioni sul nuovo utente di posta elettronica Jeffrey Zeng:
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>Utilizzo di EOP PowerShell per modificare le proprietà di un utente di posta elettronica
  
Utilizzare i cmdlet di [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) per visualizzare o modificare le proprietà degli utenti di posta elettronica.
  
In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
Per verificare che l'operazione abbia avuto esito positivo, utilizzare il cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) per verificare le modifiche. (Tenere presente che è possibile visualizzare più proprietà per più contatti di posta elettronica).
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

Nell'esempio precedente in cui la proprietà Company è stata impostata su Contoso per tutti gli utenti di posta, utilizzare il comando seguente per verificare le modifiche:
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a>Utilizzo di EOP PowerShell per rimuovere un utente di posta elettronica
  
In questo esempio viene utilizzato il cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) per eliminare l'utente Jeffrey Zeng:
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **Per verificare che è corretto**
  
Per verificare che l'operazione abbia avuto esito positivo, eseguire il cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) per verificare che l'utente di posta non sia più presente.
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
