---
title: Impostazioni ASF in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle impostazioni del filtro di posta indesiderata (Advanced Spam Filter) disponibili nei criteri di protezione da posta indesiderata in Exchange Online Protection (EOP).
ms.openlocfilehash: 3ac2b45cc03327f47bd73efe54e78312cbda4bb6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615253"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Impostazioni avanzate per il filtro della posta indesiderata in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Le impostazioni ASF attualmente disponibili nei criteri di protezione da posta indesiderata sono in fase di divenire obsolete. Si consiglia di non utilizzare queste impostazioni nei criteri di protezione da posta indesiderata. La funzionalità di queste impostazioni ASF è incorporata in altre parti dello stack di filtro. Per ulteriori informazioni, vedere Impostazioni dei criteri di protezione da [posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

In tutte le organizzazioni Microsoft 365, le impostazioni dei filtri per la posta indesiderata avanzate nei criteri di protezione da posta indesiderata in EOP consentono agli amministratori di contrassegnare i messaggi come posta indesiderata in base alle proprietà del messaggio ASF specifica specificamente queste proprietà perché sono comunemente presenti in posta indesiderata. A seconda della proprietà, i rilevamenti ASF contrassegnano il messaggio come **posta indesiderata** o **posta indesiderata con elevata attendibilità**.

> [!NOTE]
> L'abilitazione di una o più impostazioni ASF è un approccio aggressivo al filtro di posta indesiderata. Non è possibile segnalare i messaggi filtrati da ASF come falsi positivi. È possibile identificare i messaggi che sono stati filtrati tramite ASF:
>
> - Notifiche di quarantena della posta indesiderata degli utenti finali periodiche.
>
> - La presenza di messaggi filtrati in quarantena.
>
> - I `X-CustomSpam:` campi X-header specifici che vengono aggiunti ai messaggi come descritto in questo argomento.

Nelle sezioni seguenti vengono descritte le impostazioni e le opzioni ASF disponibili nei criteri di protezione da posta indesiderata nel centro sicurezza & conformità e in Exchange Online PowerShell o standalone EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) e [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Abilitazione, disabilitazione o test delle impostazioni ASF

Per ogni impostazione ASF, sono disponibili le seguenti opzioni nei criteri di protezione da posta indesiderata:

- **On**: ASF aggiunge il campo X-header corrispondente al messaggio e contrassegna il messaggio come **posta indesiderata** (SCL 5 o 6 per [aumentare le impostazioni del Punteggio di posta indesiderata](#increase-spam-score-settings)) o **posta indesiderata con elevata sicurezza** (SCL 9 per [Mark come impostazioni di posta indesiderata](#mark-as-spam-settings)).

- **Disattivato**: l'impostazione ASF è disattivata. Questo è il valore predefinito e si consiglia di non modificarlo.

- **Test**: ASF aggiunge il campo X-header corrispondente al messaggio. Cosa succede al messaggio è determinato dal valore **Opzioni modalità di test** (*TestModeAction*):

  - **None**: il recapito dei messaggi non è influenzato dal rilevamento ASF. Il messaggio è ancora soggetto ad altri tipi di filtro e regole in EOP.

  - **Aggiungere il testo x-header predefinito (*AddXHeader*)**: il valore di x-header `X-CustomSpam: This message was filtered by the custom spam filter option` viene aggiunto al messaggio. È possibile utilizzare questo valore nelle regole di posta in arrivo o nelle regole del flusso di posta (note anche come regole di trasporto) per influire sul recapito del messaggio.

  - **Send BCC Message (*BccMessage*)**: gli indirizzi di posta elettronica specificati (il valore del parametro *TestModeBccToRecipients* in PowerShell) vengono aggiunti al campo Ccn del messaggio e il messaggio viene recapitato ai destinatari Ccn aggiuntivi. Nel centro sicurezza & conformità è possibile separare più indirizzi di posta elettronica con punti e virgola (;). In PowerShell, separare più indirizzi di posta elettronica in base alle virgole.

  **Note**:

  - La modalità di test non è disponibile per le seguenti impostazioni ASF:

    - **Filtro ID mittente condizionale: errore** irreversibile (*MarkAsSpamFromAddressAuthFail*)
    - Backscatter del rapporto di **mancato recapito**(*MarkAsSpamNdrBackscatter*)
    - **Record SPF: errore** irreversibile (*MarkAsSpamSpfRecordHardFail*)

  - La stessa azione in modalità test viene applicata a *tutte* le impostazioni ASF che sono impostate su **test**. Non è possibile configurare diverse azioni in modalità test per diverse impostazioni ASF.

## <a name="increase-spam-score-settings"></a>Aumentare le impostazioni del Punteggio di posta

Le seguenti impostazioni ASF consentono di impostare il livello di probabilità di posta indesiderata dei messaggi rilevati su 5 o 6, che corrisponde al verdetto del filtro **posta indesiderata** e all'azione corrispondente nei criteri di protezione da posta indesiderata.

****

|Impostazione dei criteri di protezione da posta indesiderata|Descrizione|X-header aggiunto|
|---|---|---|
|**Collegamenti immagini a siti remoti** <p> *IncreaseScoreWithImageLinks*|I messaggi che contengono `<Img>` collegamenti ai tag HTML per i siti remoti (ad esempio, tramite http) sono contrassegnati come posta indesiderata.|`X-CustomSpam: Image links to remote sites`|
|**Reindirizzamento URL ad altra porta** <p> *IncreaseScoreWithRedirectToOtherPort*|Il messaggio che contiene collegamenti ipertestuali che reindirizzano alle porte TCP diverse da 80 (HTTP), 8080 (HTTP alternativo) o 443 (HTTPS) sono contrassegnati come posta indesiderata.|`X-CustomSpam: URL redirect to other port`|
|**Indirizzo IP numerico in URL** <p> *IncreaseScoreWithNumericIps*|I messaggi che contengono URL basati su numeri (in genere, gli indirizzi IP) sono contrassegnati come posta indesiderata.|`X-CustomSpam: Numeric IP in URL`|
|**URL di siti Web .biz o .info** <p> *IncreaseScoreWithBizOrInfoUrls*|I messaggi che contengono `.biz` o `.info` collegamenti nel corpo del messaggio vengono contrassegnati come posta indesiderata.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Contrassegna come impostazioni di posta indesiderata

Le seguenti impostazioni ASF consentono di impostare su 9 il livello SCL dei messaggi rilevati, che corrisponde al verdetto del filtro per la **posta indesiderata** e all'azione corrispondente nei criteri di protezione da posta indesiderata.

****

|Impostazione dei criteri di protezione da posta indesiderata|Descrizione|X-header aggiunto|
|---|---|---|
|**Messaggi vuoti** <p> *MarkAsSpamEmptyMessages*|Messaggi senza oggetto, nessun contenuto nel corpo del messaggio e nessun allegato sono contrassegnati come posta indesiderata con elevata sicurezza.|`X-CustomSpam: Empty Message`|
|**JavaScript o VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|I messaggi che utilizzano JavaScript o Visual Basic Script Edition in HTML sono contrassegnati come posta indesiderata con elevata sicurezza. <p> Questi linguaggi di script vengono utilizzati nei messaggi di posta elettronica per determinare l'esecuzione automatica di azioni specifiche.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Tag Frame o IFrame in HTML** <p> *MarkAsSpamFramesInHtml*|I messaggi che contengono `<frame>` o i `<iframe>` tag HTML sono contrassegnati come posta indesiderata con elevata sicurezza. <p> Questi tag vengono utilizzati nei messaggi di posta elettronica per formattare la pagina per la visualizzazione di testo o grafica.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Tag Object in HTML** <p> *MarkAsSpamObjectTagsInHtml*|I messaggi che contengono `<object>` tag HTML sono contrassegnati come posta indesiderata con elevata sicurezza. <p> Questo tag consente l'esecuzione di plug-in o applicazioni in una finestra HTML.|`X-CustomSpam: Object tag in html`|
|**Tag Embed in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Il messaggio che contiene `<embed>` tag HTML è contrassegnato come posta indesiderata con elevata sicurezza. <p> Questo tag consente di incorporare diversi tipi di documenti in un documento HTML (ad esempio, suoni, video o immagini).|`X-CustomSpam: Embed tag in html`|
|**Tag Form in HTML** <p> *MarkAsSpamFormTagsInHtml*|I messaggi che contengono `<form>` tag HTML sono contrassegnati come posta indesiderata con elevata sicurezza. <p> Questo tag viene utilizzato per creare moduli sito Web. I messaggi pubblicitari inviati tramite posta elettronica includono spesso questo tag per la richiesta di informazioni al destinatario.|`X-CustomSpam: Form tag in html`|
|**Bug Web in HTML** <p> *MarkAsSpamWebBugsInHtml*|Un *bug Web* (noto anche come *Web Beacon*) è un elemento grafico (spesso piccolo come un pixel di un pixel) utilizzato nei messaggi di posta elettronica per determinare se il messaggio è stato letto dal destinatario. <p> I messaggi che contengono bug Web sono contrassegnati come posta indesiderata con elevata attendibilità. <p> Le newsletter legittime possono utilizzare i bug Web, anche se molti considerano questa un'invasione della privacy. |`X-CustomSpam: Web bug`|
|**Applica elenco parole sensibili** <p> *MarkAsSpamSensitiveWordList*|Microsoft mantiene un elenco dinamico ma non modificabile di parole associate a messaggi potenzialmente offensivi. <p> I messaggi che contengono parole provenienti dall'elenco di Word sensibili nell'oggetto o nel corpo del messaggio vengono contrassegnati come posta indesiderata con elevata sicurezza.|`X-CustomSpam: Sensitive word in subject/body`|
|**Record SPF: non riuscito** <p> *MarkAsSpamSpfRecordHardFail*|I messaggi inviati da un indirizzo IP che non è specificato nel record SPF (SPF Sender Policy Framework) in DNS per il dominio di posta elettronica di origine sono contrassegnati come posta indesiderata con elevata sicurezza. <p> La modalità di test non è disponibile per questa impostazione.|`X-CustomSpam: SPF Record Fail`|
|**Filtro dell'ID mittente condizionale: non riuscito** <p> *MarkAsSpamFromAddressAuthFail*|Messaggi che non riescono a un controllo dell'ID mittente condizionale sono contrassegnati come posta indesiderata. <p> Questa impostazione consente di combinare un controllo SPF con un controllo dell'ID mittente per proteggere le intestazioni dei messaggi che contengono mittenti contraffatti. <p> La modalità di test non è disponibile per questa impostazione.|`X-CustomSpam: SPF From Record Fail`|
|**Posta indesiderata costituita da falsi rapporti di mancato recapito di NDR** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* è inutili rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) causati da mittenti contraffatti nei messaggi di posta elettronica. Per ulteriori informazioni, vedere [backscatter messages and EOP](backscatter-messages-and-eop.md). <p> Non è necessario configurare questa impostazione negli ambienti seguenti, in quanto i rapporti di mancato recapito vengono recapitati e la backscattering è contrassegnata come posta indesiderata: <ul><li>Microsoft 365 organizzazioni con cassette postali di Exchange Online.</li><li>Organizzazioni di posta elettronica locali in cui viene instradata la posta elettronica in *uscita* tramite EOP.</li></ul> <p> In ambienti EOP autonomi che proteggono la posta elettronica in arrivo nelle cassette postali locali, l'attivazione o la disattivazione di questa impostazione ha il seguente risultato: <ul><li> **On**: i rapporti di mancato recapito legittimi vengono recapitati e il backscatter è contrassegnato come posta</li><li>**Disattivato**: i rapporti di mancato recapito e backscattering legittimi passano attraverso il filtro normale. La maggior parte dei rapporti di mancato recapito legittimi verrà recapitata al mittente. Alcuni, ma non tutti, backscatter sono contrassegnati come posta indesiderata con elevata sicurezza. Per definizione, il backscatter può essere recapitato solo al mittente falsificato, non al mittente originale.</li></ul> <p> La modalità di test non è disponibile per questa impostazione.|`X-CustomSpam: Backscatter NDR`|
|
