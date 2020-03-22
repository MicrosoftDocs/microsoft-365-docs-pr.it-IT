---
title: Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta in Exchange Online Protection per il filtro della posta elettronica in blocco.
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895048"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco in Office 365

Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) messaggi in ingresso per la posta indesiderata e di massa (nota anche come posta grigia). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

Se si desiderano ulteriori opzioni per filtrare la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare i messaggi come posta indesiderata. Per ulteriori informazioni sulla posta in blocco, vedere [Qual è la differenza tra posta elettronica indesiderata e posta elettronica](what-s-the-difference-between-junk-email-and-bulk-email.md) in blocco e [livello di reclamo in blocco (BCL) in Office 365](bulk-complaint-level-values.md).

In questo argomento viene illustrato come creare queste regole del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online. In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di Exchange Online Protection autonomo, vedere [connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:

  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- L'elenco delle parole e dei modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere le voci in base alle esigenze. Tuttavia, sono un buon punto di partenza.

- La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.

- Le procedure seguenti contrassegnano un messaggio di massa come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare il filtro aggressivo su alcuni utenti di alto livello, mentre gli altri utenti (che principalmente ricevono la posta elettronica in blocco) non sono interessati.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Utilizzo di EAC per creare regole del flusso di posta che filtrano la posta elettronica in blocco

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **Add** ![clic su Aggiungi](../../media/ITPro-EAC-AddIcon.png) icona e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: configurare una delle impostazioni seguenti per cercare il contenuto nei messaggi utilizzando espressioni regolari (Regex) o parole o frasi:

     - **L'oggetto o il corpo del corpo** \> o dell'oggetto **corrisponde a questi modelli di testo**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti,](../../media/ITPro-EAC-AddIcon.png)fare clic su **Aggiungi** ![icona e ripetere il numero di volte necessario.

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica. Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.

       Al termine, fare clic su **OK**.

     - **L'oggetto o il corpo dell'oggetto** \> o **del corpo include una di queste parole**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic](../../media/ITPro-EAC-AddIcon.png)su **Aggiungi** ![icona e ripetere il numero di volte necessario.

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

      Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica. Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.

       Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti**: selezionare **modifica le proprietà** \> del messaggio **impostare il livello di probabilità di posta indesiderata (SCL)**. Nella finestra di dialogo **specifica SCL** visualizzata, configurare una delle seguenti impostazioni:

     - Per contrassegnare i messaggi come **posta indesiderata**, selezionare **6**. L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).

     - Per contrassegnare i messaggi come **posta indesiderata con elevata sicurezza** selezionare **9**. L'azione configurata per il filtro di protezione da posta indesiderata con **sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Move Message to junk email Folder**).

    Per ulteriori informazioni sui valori SCL, vedere [livello di probabilità di posta indesiderata (SCL) in Office 365](spam-confidence-levels.md).

   Al termine, fare clic su **Salva**

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a>Utilizzo di PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco

Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In questo esempio viene creata una nuova regola denominata "filtro posta elettronica in blocco" che utilizza lo stesso elenco di espressioni regolari di precedenza nell'argomento per impostare i messaggi come **posta indesiderata**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In questo esempio viene creata una nuova regola denominata "Bulk Email Filtering-Words" che utilizza lo stesso elenco di parole di precedenza nell'argomento per impostare i messaggi come **posta indesiderata con elevata attendibilità**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a **regole** \> del **flusso** \> di **Edit** ![posta selezionare la](../../media/ITPro-EAC-EditIcon.png)regola \> fare clic su Modifica icona modifica e verificare le impostazioni.

- In PowerShell, sostituire \<il nome\> della regola con il nome della regola ed eseguire il comando seguente per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Da un account esterno, inviare un messaggio di prova a un destinatario coinvolto che contiene una delle frasi o modelli di testo e verificare i risultati.
