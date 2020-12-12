---
title: Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come utilizzare le regole del flusso di posta (regole di trasporto) per identificare e filtrare la posta in blocco (Gray mail) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b029e805147218551ba6ff80fb5abfda3fbfef7f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658638"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Usare le regole del flusso di posta per filtrare la posta inviata in blocco in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per l'analisi dei messaggi in ingresso per la posta indesiderata e per l'invio di massa Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Se si desiderano ulteriori opzioni per filtrare la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare i messaggi come posta indesiderata. Per ulteriori informazioni sulla posta in blocco, vedere [Qual è la differenza tra posta elettronica indesiderata e posta elettronica](what-s-the-difference-between-junk-email-and-bulk-email.md) in blocco e [livello di reclamo in blocco (BCL) in EOP](bulk-complaint-level-values.md).

In questo argomento viene illustrato come creare queste regole del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection. In particolare, è necessario il ruolo **regole di trasporto** , assegnato ai gruppi di ruoli Gestione **organizzazione**, gestione **conformità** (amministratori globali) e **Records Management** per impostazione predefinita.

  Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Autorizzazioni in Exchange Online Protection autonomo](feature-permissions-in-eop.md)
  - [Utilizzo dell'interfaccia di amministrazione di Exchange modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Per aprire EAC in EOP autonomo, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:

  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- L'elenco delle parole e dei modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere le voci in base alle esigenze. Tuttavia, sono un buon punto di partenza.

- La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.

- Le procedure seguenti contrassegnano un messaggio di massa come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare il filtro aggressivo su alcuni utenti di alto livello, mentre gli altri utenti (che principalmente ricevono la posta elettronica in blocco) non sono interessati.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Utilizzo di EAC per creare regole del flusso di posta che filtrano la posta elettronica in blocco

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: configurare una delle impostazioni seguenti per cercare il contenuto nei messaggi utilizzando espressioni regolari (Regex) o parole o frasi:

     - **L'oggetto o il corpo** \> l' **oggetto o il corpo corrisponde a questi modelli di testo**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) . Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .

       Al termine, fare clic su **OK**.

     - **L'oggetto o il corpo** \> l' **oggetto o il corpo include una di queste parole**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) . Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .

       Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**. Nella finestra di dialogo **specifica SCL** visualizzata, configurare una delle seguenti impostazioni:

     - Per contrassegnare i messaggi come **posta indesiderata**, selezionare **6**. L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).

     - Per contrassegnare i messaggi come **posta indesiderata con elevata sicurezza** selezionare **9**. L'azione configurata per il filtro di protezione da posta indesiderata con **sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Move Message to junk email Folder**).

    Per ulteriori informazioni sui valori SCL, vedere [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).

   Al termine, fare clic su **Salva**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Utilizzo di PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco

Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In questo esempio viene creata una nuova regola denominata "filtro posta elettronica in blocco" che utilizza lo stesso elenco di espressioni regolari di precedenza nell'argomento per impostare i messaggi come **posta indesiderata**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In questo esempio viene creata una nuova regola denominata "Bulk Email Filtering-Words" che utilizza lo stesso elenco di parole di precedenza nell'argomento per impostare i messaggi come **posta indesiderata con elevata attendibilità**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \>  \> selezionare la regola \> fare clic su **Modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e verificare le impostazioni.

- In PowerShell, sostituire \<Rule Name\> con il nome della regola ed eseguire il comando riportato di seguito per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Da un account esterno, inviare un messaggio di prova a un destinatario coinvolto che contiene una delle frasi o modelli di testo e verificare i risultati.
