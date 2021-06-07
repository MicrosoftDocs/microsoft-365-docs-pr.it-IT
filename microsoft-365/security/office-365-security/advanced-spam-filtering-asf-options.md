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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle impostazioni asf (Advanced Spam Filter) disponibili nei criteri di protezione da posta indesiderata in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 12f193ef61205e8568341c774b957ce4a9dd7988
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779423"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Impostazioni avanzate del filtro posta indesiderata (ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Le impostazioni ASF attualmente disponibili nei criteri di protezione da posta indesiderata stanno per essere deprecate. Si consiglia di non utilizzare queste impostazioni nei criteri di protezione da posta indesiderata. La funzionalità di queste impostazioni ASF viene incorporata in altre parti dello stack di filtro. Per ulteriori informazioni, vedere Impostazioni dei criteri di protezione da posta indesiderata [di EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

In tutte Microsoft 365, le impostazioni asf (Advanced Spam Filter) nei criteri di protezione da posta indesiderata in EOP consentono agli amministratori di contrassegnare i messaggi come posta indesiderata in base a proprietà dei messaggi specifiche. ASF si rivolge in modo specifico a queste proprietà perché si trovano comunemente nella posta indesiderata. A seconda della proprietà, i rilevamenti ASF contrassegneranno il messaggio come **Posta** indesiderata o **Alta probabilità di posta indesiderata.**

> [!NOTE]
> L'abilitazione di una o più impostazioni ASF è un approccio aggressivo al filtro posta indesiderata. Non è possibile segnalare i messaggi filtrati da ASF come falsi positivi. È possibile identificare i messaggi filtrati da ASF in base a:
>
> - Notifiche periodiche di quarantena della posta indesiderata dell'utente finale.
> - Presenza dei messaggi filtrati in quarantena.
> - Campi `X-CustomSpam:` X-header specifici che vengono aggiunti ai messaggi come descritto in questo articolo.

Nelle sezioni seguenti vengono descritte le impostazioni e le opzioni ASF disponibili nei criteri di protezione da posta indesiderata nel Centro sicurezza Microsoft 365 e in PowerShell di Exchange Online o PowerShell EOP autonomo ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) e [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Abilitare, disabilitare o testare le impostazioni ASF

Per ogni impostazione ASF, nei criteri di protezione da posta indesiderata sono disponibili le opzioni seguenti:

- **On**: ASF aggiunge il campo X-header corrispondente al messaggio e contrassegna il messaggio come Posta indesiderata **(SCL** 5 o 6 per Aumentare le impostazioni del punteggio di posta indesiderata [)](#increase-spam-score-settings)o Posta indesiderata alta **(SCL** 9 per Le impostazioni di Contrassegna come posta [indesiderata](#mark-as-spam-settings)).
- **Disattivato**: l'impostazione ASF è disabilitata. Questo è il valore predefinito ed è consigliabile non modificarlo.
- **Test**: ASF aggiunge il campo X-header corrispondente al messaggio. Ciò che accade al messaggio è determinato dal **valore della** modalità test (*TestModeAction*):
  - **Nessuno:** il recapito dei messaggi non è interessato dal rilevamento ASF. Il messaggio è ancora soggetto ad altri tipi di filtro e regole in EOP.
  - **Aggiungi testo X-header predefinito (*AddXHeader*):** il valore X-header `X-CustomSpam: This message was filtered by the custom spam filter option` viene aggiunto al messaggio. È possibile utilizzare questo valore nelle regole di Posta in arrivo o nelle regole del flusso di posta (note anche come regole di trasporto) per influire sul recapito del messaggio.
  - **Invia messaggio Ccn (*BccMessage*):** gli indirizzi di posta elettronica specificati (il valore del parametro *TestModeBccToRecipients* in PowerShell) vengono aggiunti al campo Ccn del messaggio e il messaggio viene recapitato agli altri destinatari Ccn. Nel Centro sicurezza è possibile separare più indirizzi di posta elettronica con un punto e virgola (;). In PowerShell, più indirizzi di posta elettronica vengono separati da virgole.

  **Note**:

  - La modalità test non è disponibile per le impostazioni ASF seguenti:
    - **Filtro ID mittente condizionale: non riuscito** (*MarkAsSpamFromAddressAuthFail*)
    - **Backscatter NDR**(*MarkAsSpamNdrBackscatter*)
    - **Record SPF: hard fail** (*MarkAsSpamSpfRecordHardFail*)
  - La stessa azione della modalità di test viene applicata *a tutte* le impostazioni ASF impostate su **Test**. Non è possibile configurare azioni in modalità test diverse per impostazioni ASF diverse.

## <a name="increase-spam-score-settings"></a>Aumentare le impostazioni del punteggio di posta indesiderata

Le impostazioni ASF seguenti impostano il livello di probabilità di posta indesiderata (SCL) dei messaggi rilevati su 5 o 6, che corrisponde al verdetto del filtro posta indesiderata e all'azione corrispondente nei criteri di protezione da posta indesiderata. 

<br>

****

|Impostazione dei criteri di protezione da posta indesiderata|Descrizione|X-header aggiunto|
|---|---|---|
|**Collegamenti immagine a siti Web remoti** <p> *IncreaseScoreWithImageLinks*|I messaggi che contengono collegamenti tag HTML a siti remoti ,ad esempio `<Img>` http, vengono contrassegnati come posta indesiderata.|`X-CustomSpam: Image links to remote sites`|
|**Indirizzo IP numerico in URL** <p> *IncreaseScoreWithNumericIps*|I messaggi che contengono URL basati su numeri (in genere indirizzi IP) vengono contrassegnati come posta indesiderata.|`X-CustomSpam: Numeric IP in URL`|
|**Reindirizzamento URL ad altra porta** <p> *IncreaseScoreWithRedirectToOtherPort*|I messaggi contenenti collegamenti ipertestuali che reindirizzano a porte TCP diverse da 80 (HTTP), 8080 (HTTP alternativo) o 443 (HTTPS) vengono contrassegnati come posta indesiderata.|`X-CustomSpam: URL redirect to other port`|
|**Collegamenti a siti Web .biz o .info** <p> *IncreaseScoreWithBizOrInfoUrls*|I messaggi che `.biz` contengono o collegamenti nel corpo del messaggio vengono `.info` contrassegnati come posta indesiderata.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Contrassegnare come impostazioni di posta indesiderata

Le impostazioni ASF seguenti impostano il livello di probabilità di posta indesiderata dei messaggi rilevati su 9, che corrisponde al verdetto **del** filtro di protezione da posta indesiderata ad alta probabilità e all'azione corrispondente nei criteri di protezione da posta indesiderata.

<br>

****

|Impostazione dei criteri di protezione da posta indesiderata|Descrizione|X-header aggiunto|
|---|---|---|
|**Messaggi vuoti** <p> *MarkAsSpamEmptyMessages*|I messaggi senza oggetto, senza contenuto nel corpo del messaggio e senza allegati vengono contrassegnati come posta indesiderata ad alta probabilità.|`X-CustomSpam: Empty Message`|
|**Tag incorporati in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|I messaggi che contengono `<embed>` tag HTML vengono contrassegnati come posta indesiderata ad alta probabilità. <p> Questo tag consente l'incorporamento di diversi tipi di documenti in un documento HTML, ad esempio suoni, video o immagini.|`X-CustomSpam: Embed tag in html`|
|**JavaScript o VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|I messaggi che usano JavaScript o Visual Basic Script Edition in HTML sono contrassegnati come posta indesiderata ad alta probabilità. <p> Questi linguaggi di script vengono utilizzati nei messaggi di posta elettronica per fare in modo che si verifichino automaticamente azioni specifiche.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Tag Form in HTML** <p> *MarkAsSpamFormTagsInHtml*|I messaggi che contengono `<form>` tag HTML vengono contrassegnati come posta indesiderata ad alta probabilità. <p> Questo tag viene utilizzato per creare moduli sito Web. I messaggi pubblicitari inviati tramite posta elettronica includono spesso questo tag per la richiesta di informazioni al destinatario.|`X-CustomSpam: Form tag in html`|
|**Tag Frame o iframe in HTML** <p> *MarkAsSpamFramesInHtml*|I messaggi che contengono `<frame>` o tag HTML vengono `<iframe>` contrassegnati come posta indesiderata ad alta probabilità. <p> Questi tag vengono utilizzati nei messaggi di posta elettronica per formattare la pagina per la visualizzazione di testo o grafica.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Bug Web in HTML** <p> *MarkAsSpamWebBugsInHtml*|Un *bug Web* (noto anche come web *beacon)* è un elemento grafico (spesso piccolo come un pixel per pixel) che viene utilizzato nei messaggi di posta elettronica per determinare se il messaggio è stato letto dal destinatario. <p> I messaggi che contengono bug Web vengono contrassegnati come posta indesiderata ad alta probabilità. <p> Le newsletter legittime potrebbero usare bug Web, anche se molti considerano questa un'invasione della privacy. |`X-CustomSpam: Web bug`|
|**Tag Object in HTML** <p> *MarkAsSpamObjectTagsInHtml*|I messaggi che contengono `<object>` tag HTML vengono contrassegnati come posta indesiderata ad alta probabilità. <p> Questo tag consente l'esecuzione di plug-in o applicazioni in una finestra HTML.|`X-CustomSpam: Object tag in html`|
|**Parole riservate** <p> *MarkAsSpamSensitiveWordList*|Microsoft gestisce un elenco dinamico ma non modificabile di parole associate a messaggi potenzialmente offensivi. <p> I messaggi che contengono parole dell'elenco di parole riservate nell'oggetto o nel corpo del messaggio vengono contrassegnati come posta indesiderata con alta probabilità.|`X-CustomSpam: Sensitive word in subject/body`|
|**Record SPF: non riuscito** <p> *MarkAsSpamSpfRecordHardFail*|I messaggi inviati da un indirizzo IP non specificato nel record SPF Sender Policy Framework (SPF) in DNS per il dominio di posta elettronica di origine vengono contrassegnati come posta indesiderata con alta probabilità. <p> La modalità test non è disponibile per questa impostazione.|`X-CustomSpam: SPF Record Fail`|
|**Filtro ID mittente non riuscito** <p> *MarkAsSpamFromAddressAuthFail*|I messaggi che non riescono a eseguire un controllo dell'ID mittente condizionale vengono contrassegnati come posta indesiderata. <p> Questa impostazione combina un controllo SPF con un controllo dell'ID mittente per proteggere le intestazioni dei messaggi che contengono mittenti contraffatti. <p> La modalità test non è disponibile per questa impostazione.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* è un inutile rapporto di mancato recapito (noto anche come rapporti di mancato recapito o messaggi di mancato recapito) causato dai mittenti contraffatti nei messaggi di posta elettronica. Per ulteriori informazioni, vedere [Backscatter messages ed EOP.](backscatter-messages-and-eop.md) <p> Non è necessario configurare questa impostazione negli ambienti seguenti, perché vengono recapitati IndR legittimi e il backscatter è contrassegnato come posta indesiderata: <ul><li>Microsoft 365 le organizzazioni con Exchange Online cassette postali.</li><li>Organizzazioni di posta elettronica locali in cui instradare la posta elettronica *in* uscita tramite EOP.</li></ul> <p> Negli ambienti EOP autonomi che proteggono la posta elettronica in ingresso nelle cassette postali locali, l'attivazione o la disattivazione di questa impostazione ha il risultato seguente: <ul><li> **On**: I nomi di mancato recapito legittimi vengono recapitati e il backscatter viene contrassegnato come posta indesiderata.</li><li>**Disattivato:** i messaggi di mancato recapito legittimi e i backscatter passano attraverso il normale filtro della posta indesiderata. La maggior parte dei nomi di mancato recapito legittimi verrà recapitata al mittente del messaggio originale. Alcuni, ma non tutti, i backscatter sono contrassegnati come posta indesiderata ad alta probabilità. Per definizione, il backscatter può essere recapitato solo al mittente contraffatto, non al mittente originale.</li></ul> <p> La modalità test non è disponibile per questa impostazione.|`X-CustomSpam: Backscatter NDR`|
|
