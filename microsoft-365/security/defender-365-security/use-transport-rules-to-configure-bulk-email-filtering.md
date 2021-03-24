---
title: Usare le regole del flusso di posta per filtrare la posta elettronica in blocco
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a utilizzare le regole del flusso di posta (regole di trasporto) per identificare e filtrare la posta in blocco (posta grigia) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061850"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Usare le regole del flusso di posta per filtrare la posta inviata in blocco in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP utilizza i criteri di protezione da posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per analizzare i messaggi in ingresso alla ricerca di posta indesiderata e posta in blocco (nota anche come posta grigia). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Se si desidera che più opzioni filtrano la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare tali messaggi come posta indesiderata. Per ulteriori informazioni sulla posta in blocco, vedere Qual è la differenza tra posta indesiderata e posta elettronica in [blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) e Livello di reclamo in blocco [(BCL) in EOP](bulk-complaint-level-values.md).

In questo argomento viene illustrato come creare queste regole del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection. In particolare, è necessario il ruolo **Regole** di trasporto, assegnato ai gruppi  di ruoli **Gestione** **organizzazione,** Gestione conformità (amministratori globali) e Gestione record per impostazione predefinita.

  Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Autorizzazioni in Exchange Online Protection autonomo](feature-permissions-in-eop.md)
  - [Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per aprire l'interfaccia di amministrazione di Exchange in Exchange Online, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/Exchange/exchange-admin-center) Per aprire l'interfaccia di amministrazione di Exchange in EOP autonomo, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e in EOP autonomo, vedere i seguenti argomenti:

  - [Regole del flusso di posta (regole di trasporto) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Azioni delle regole del flusso di posta in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- L'elenco di parole e modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere voci in base alle esigenze. Tuttavia, sono un buon punto di partenza.

- La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.

- Le procedure seguenti contrassegnano un messaggio in blocco come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare un filtro aggressivo su alcuni utenti altamente mirati, mentre il resto degli utenti (che ottengono principalmente la posta elettronica in blocco per cui si sono registrati) non sono interessati.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare regole del flusso di posta che filtrano la posta elettronica in blocco

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **clic su** Aggiungi Icona Aggiungi e quindi selezionare Crea una nuova ![ ](../../media/ITPro-EAC-AddIcon.png) **regola.**

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome descrittivo univoco per la regola.

   - Fare **clic su Altre opzioni.**

   - **Applicare questa regola se**: Configurare una delle impostazioni seguenti per cercare il contenuto dei messaggi utilizzando espressioni regolari (RegEx) o parole o frasi:

     - **Oggetto o corpo** \> **l'oggetto** o il corpo  corrisponde a questi modelli di testo: nella finestra  di dialogo Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.

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

      Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica. Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.

       Al termine, fare clic su **OK**.

     - **Oggetto o corpo** \> **l'oggetto** o il corpo include  una di queste parole: nella finestra di dialogo  Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.

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

      Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica. Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.

       Al termine, fare clic su **OK**.

   - **Eseguire le operazioni seguenti:** Selezionare **Modifica le proprietà del messaggio** impostare il livello di probabilità di posta indesiderata \> **(SCL).** Nella finestra **di dialogo Specifica SCL** visualizzata configurare una delle impostazioni seguenti:

     - Per contrassegnare i messaggi **come posta** indesiderata, selezionare **6**. L'azione configurata per  i verdetti del filtro posta indesiderata nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è Sposta messaggio nella cartella Posta **indesiderata**).

     - Per contrassegnare i messaggi **come posta indesiderata con confidenza elevata,** selezionare **9**. L'azione configurata per  i verdetti di filtro della posta indesiderata ad alta probabilità nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è Sposta messaggio nella cartella Posta **indesiderata**).

    Per ulteriori informazioni sui valori SCL, vedere [Spam confidence level (SCL) in EOP.](spam-confidence-levels.md)

   Al termine, fare clic su **Salva**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Utilizzare PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco

Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In questo esempio viene creata una nuova regola denominata "Bulk email filtering - RegEx" che utilizza lo stesso elenco di espressioni regolari riportato in precedenza nell'argomento per impostare i messaggi come **Posta indesiderata.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In questo esempio viene creata una nuova regola denominata "Bulk email filtering - Words" che utilizza lo stesso elenco di parole riportato in precedenza nell'argomento per impostare i messaggi come posta indesiderata con **alta probabilità.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta Regole selezionare la regola fare clic \>  \> su \> **Modifica** Icona Modifica e verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In PowerShell, \<Rule Name\> sostituire con il nome della regola ed eseguire il comando seguente per verificare le impostazioni:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Da un account esterno, inviare un messaggio di prova a un destinatario interessato contenente una delle frasi o dei modelli di testo e verificare i risultati.