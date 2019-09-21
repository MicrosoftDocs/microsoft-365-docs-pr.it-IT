---
title: Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
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
ms.openlocfilehash: e354bb137e114a7d11bff97be0c1109becb54f84
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084563"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection

È possibile impostare filtri di contenuto a livello aziendale per la posta indesiderata e i messaggi in blocco utilizzando i criteri di filtro contenuto spam predefiniti. Vedere [configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md) e [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) su come impostare i criteri di filtro dei contenuti. 
  
Se si desiderano ulteriori opzioni per filtrare i messaggi in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nei messaggi di posta elettronica in blocco. Tutti i messaggi che contengono queste caratteristiche verranno contrassegnati come posta indesiderata. L'utilizzo di queste regole consente di ridurre la quantità di posta indesiderata ricevuta dall'organizzazione.

> [!IMPORTANT]
> Prima di creare le regole del flusso di posta documentate questo argomento, si consiglia di leggere innanzitutto [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md) e [valori a livello di reclamo in blocco](bulk-complaint-level-values.md).<br> Le procedure indicate di seguito consentono di contrassegnare un messaggio come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole esclusivamente a destinatari specifici nell'organizzazione. In questo modo, le impostazioni di filtro della posta elettronica in blocco aggressive possono essere applicate a pochi utenti fortemente mirati, mentre gli altri utenti (che per lo più ricevono la posta elettronica di massa a cui hanno effettuato l'iscrizione) non sono interessati. 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base ai modelli di testo

1. Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.
    
2. Fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.
    
3. Specificare un nome per la regola.
    
4. Fare clic su **Altre opzioni**. In **applica la regola se**, selezionare **l'** \> oggetto o il corpo o l'oggetto corpo **corrisponde a questi modelli di testo**.
    
5. Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine: 
    
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
    
   L'elenco di cui sopra non è un insieme esaustivo di espressioni regolari presenti nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze. Tuttavia, si tratta di un buon punto di partenza.<br>La ricerca di parole o di modelli di testo nell'oggetto o in altri campi di intestazione del messaggio si verifica *dopo* la decodifica del messaggio dal metodo MIME Content Transfer Encoding utilizzato per la trasmissione del messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi. 
    
6. In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.
    
7. Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.
    
   L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
    
   Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta indesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata. 
  
   Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).
    
8. Salvare la regola.
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base alle frasi

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.
    
2. Fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.
    
3. Specificare un nome per la regola.
    
4. Fare clic su **Altre opzioni**. In **applica la regola se**, selezionare **l'** \> oggetto o il corpo del soggetto o **del corpo include una o più delle seguenti parole**.
    
5. Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine: 
    
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
    
   Questo elenco non è un insieme esaustivo di frasi trovate nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze. Tuttavia, si tratta di un buon punto di partenza.
    
6. In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.
    
7. Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.
    
   L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
    
   Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta indesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata. 
  
   Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).

8. Salvare la regola.

## <a name="for-more-information"></a>Ulteriori informazioni

[Differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Valori di livello di reclamo in blocco](bulk-complaint-level-values.md)

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)

[Opzioni di filtro della posta indesiderata avanzate](advanced-spam-filtering-asf-options.md)
