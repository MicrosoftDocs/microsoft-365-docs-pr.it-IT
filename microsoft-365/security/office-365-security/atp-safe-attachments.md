---
title: Allegati sicuri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: Gli amministratori possono conoscere la funzionalità allegati sicuri in Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: 6ff356f34f3e44752b5ad7f5fa433a8c72cd5083
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326532"
---
# <a name="safe-attachments-in-office-365-atp"></a>Allegati sicuri in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Allegati sicuri in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) fornisce un ulteriore livello di protezione per gli allegati di posta elettronica che sono già stati analizzati dalla [protezione antimalware in Exchange Online Protection (EOP)](anti-malware-protection.md). In particolare, gli allegati sicuri utilizzano un ambiente virtuale per controllare gli allegati nei messaggi di posta elettronica prima di essere recapitati ai destinatari (processo noto come _detonazione_).

Protezione degli allegati sicuri per i messaggi di posta elettronica è controllata da criteri allegati sicuri. Non esiste alcun criterio di allegati sicuri predefinito, **per ottenere la protezione degli allegati sicuri, è necessario creare uno o più criteri per gli allegati sicuri**. Per istruzioni, vedere [configurare i criteri per gli allegati sicuri in ATP](set-up-atp-safe-attachments-policies.md).

Nella tabella seguente vengono descritti gli scenari per gli allegati sicuri in Microsoft 365 e le organizzazioni di Office 365 che includono ATP (in altre parole, la mancanza di licenze non è mai un problema negli esempi).

****

|Scenario|Risultato|
|---|---|
|L'organizzazione Microsoft 365 E5 di Pat non dispone di criteri allegati sicuri configurati.|Pat non è protetto da allegati sicuri. <br/><br/> Un amministratore deve creare almeno un criterio di allegati sicuri per la protezione degli allegati sicuri come attiva. Inoltre, le condizioni del criterio devono includere Pat se Pat deve essere protetto da allegati sicuri.|
|L'organizzazione di Lee ha un criterio di allegati sicuri che si applica solo ai dipendenti finanziati. Lee è un membro del reparto vendite.|Lee non è protetto da allegati sicuri. <br/><br/> I dipendenti finanziari sono protetti da allegati sicuri, ma i dipendenti di vendita (e altri dipendenti) non lo sono.|
|Ieri, un amministratore dell'organizzazione di Jean ha creato un criterio di allegati sicuri che si applica a tutti i dipendenti. Prima di oggi, Jean ha ricevuto un messaggio di posta elettronica che includeva un allegato.|Jean è protetto da allegati sicuri. <br/><br/> In genere, sono necessari circa 30 minuti per rendere effettive le nuove regole.|
|L'organizzazione di Chris ha criteri per gli allegati sicuri di lunga data per tutti gli utenti dell'organizzazione. Chris riceve un messaggio di posta elettronica che contiene un allegato e quindi inoltra i messaggi a destinatari esterni.|Chi è protetto da allegati sicuri. <br/><br/> Se i destinatari esterni dispongono anche di criteri per gli allegati sicuri nell'organizzazione, i messaggi inoltrati sono soggetti a tali criteri.|
|

L'analisi degli allegati sicuri si verifica nella stessa area in cui si trovano i dati di Microsoft 365. Per ulteriori informazioni sulla geografia del datacenter, vedere [dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Le seguenti funzionalità sono situate nelle impostazioni globali sono dei criteri allegati sicuri nel centro sicurezza & conformità, ma queste impostazioni sono abilitate o disabilitate a livello globale e non richiedono criteri allegati sicuri:
>
> - [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).
>
> - [Documenti attendibili in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Impostazioni di criteri per gli allegati sicuri

In questa sezione vengono descritte le impostazioni dei criteri allegati sicuri:

- **Risposta malware per gli allegati sicuri**: questa impostazione consente di controllare l'azione per gli allegati sicuri che analizzano i messaggi di posta elettronica. Le opzioni disponibili sono descritte nella tabella seguente:

  ****

  |Opzione|Effetto|Utilizzare se si desidera eseguire le operazioni seguenti:|
  |---|---|---|
  |**Disattivare**|Gli allegati non vengono analizzati per gli allegati sicuri da malware. I messaggi vengono ancora analizzati per la [protezione antimalware in EOP](anti-malware-protection.md).|Disattiva l'analisi per i destinatari selezionati. <br/><br/> Impedire inutili ritardi nella distribuzione della posta interna. <br/><br/> **Questa opzione non è consigliata per la maggior parte degli utenti. È consigliabile utilizzare questa opzione solo per disattivare l'analisi degli allegati sicuri per i destinatari che ricevono solo messaggi provenienti da mittenti attendibili.**|
  |**Monitor**|Recapita messaggi con allegati e quindi tiene traccia di cosa accade con malware rilevato. <br/><br/> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Vedere dove il malware rilevato entra nell'organizzazione.|
  |**Blocca**|Impedisce la recapito dei messaggi con allegati malware rilevati. <br/><br/> I messaggi vengono [messi in quarantena](manage-quarantined-messages-and-files.md) se solo gli amministratori (non gli utenti finali) possono esaminare, rilasciare o eliminare i messaggi. <br/><br/> Blocca automaticamente le istanze future dei messaggi e degli allegati. <br/><br/> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Protegge l'organizzazione da attacchi ripetuti con gli stessi allegati di malware. <br/><br/> Questo è il valore predefinito e il valore consigliato nei [criteri di sicurezza preimpostati](preset-security-policies.md)standard e rigorosi.|
  |**Sostituisce**|Rimuove gli allegati di malware rilevati. <br/><br/> Notifica ai destinatari che gli allegati sono stati rimossi. <br/><br/>  I messaggi vengono [messi in quarantena](manage-quarantined-messages-and-files.md) se solo gli amministratori (non gli utenti finali) possono esaminare, rilasciare o eliminare i messaggi. <br/><br/> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Aumentare la visibilità ai destinatari che gli allegati sono stati rimossi a causa del malware rilevato.|
  |**Recapito dinamico**|Recapita immediatamente i messaggi, ma sostituisce gli allegati con i segnaposto fino al completamento dell'analisi degli allegati sicuri. <br/><br/> Per informazioni dettagliate, vedere la sezione criteri per il [recapito dinamico in allegati sicuri](#dynamic-delivery-in-safe-attachments-policies) più avanti in questo argomento.|Evitare ritardi nei messaggi durante la protezione dei destinatari da file dannosi <br/> <br/> Abilitazione dei destinatari all'anteprima degli allegati in modalità provvisoria durante la scansione|
  |

- **Redirect Attachment on Detection: Enable redirect** and **Send the attachment to the indirizzo di posta elettronica seguente**: per le azioni **blocca**, **monitora**o **Sostituisci** , invia messaggi che contengono allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'indagine.

  La raccomandazione per le impostazioni dei criteri standard e rigorosa consiste nell'abilitare il reindirizzamento. Per ulteriori informazioni, vedere [impostazioni degli allegati sicuri](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- **Applicare la selezione precedente se la ricerca di malware per gli allegati**non è stata eseguita o si verifica un errore: l'azione specificata dalla **risposta malware Unknown Attachments** è presa sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata. Selezionare sempre questa opzione se si seleziona **Abilita reindirizzamento**. In caso contrario, è possibile che i messaggi vengano persi.

- **Filtri destinatario**: è necessario specificare le condizioni del destinatario e le eccezioni che determinano gli utenti a cui si applica il criterio. È possibile utilizzare queste proprietà per le condizioni e le eccezioni:

  - **Il destinatario è**
  - **Il dominio del destinatario è**
  - **Il destinatario è un membro di**

  È possibile utilizzare solo un'eccezione una volta, ma la condizione o l'eccezione può contenere più valori. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

- **Priorità**: se si creano più criteri, è possibile specificare l'ordine in cui sono stati applicati. Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

  Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Recapito dinamico nei criteri allegati sicuri

> [!NOTE]
> Il recapito dinamico funziona solo per le cassette postali di Exchange Online.

L'azione di recapito dinamico nei criteri allegati sicuri cerca di eliminare eventuali ritardi di recapito della posta elettronica che potrebbero essere causati dall'analisi degli allegati sicuri. Il corpo del messaggio di posta elettronica viene recapitato al destinatario con un segnaposto per ogni allegato. Il segnaposto rimane invariato fino a quando non si trova l'allegato sicuro e quindi l'allegato diventa disponibile per l'apertura o il download.

Se si trova un allegato che è dannoso, il messaggio viene messo in quarantena. Solo gli amministratori (non gli utenti finali) possono esaminare, rilasciare o eliminare i messaggi che sono stati messi in quarantena dall'analisi degli allegati sicuri. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore](manage-quarantined-messages-and-files.md).

La maggior parte dei file PDF e i documenti di Office possono essere visualizzati in anteprima in modalità provvisoria mentre è in corso l'analisi degli allegati sicuri. Se un allegato non è compatibile con il Visualizzatore di anteprima per il recapito dinamico, i destinatari visualizzeranno un segnaposto per l'allegato fino al completamento dell'analisi degli allegati sicuri.

Se si utilizza un dispositivo mobile e i file PDF non vengono renderizzati nell'anteprima di recapito dinamico sul dispositivo mobile, provare a aprire il messaggio in Outlook sul Web (in precedenza noto come Outlook Web App) utilizzando il browser per dispositivi mobili.

Di seguito sono riportate alcune considerazioni relative al recapito dinamico e ai messaggi inoltrati:

- Se il destinatario inoltrato è protetto da un criterio degli allegati sicuri che utilizza l'opzione di recapito dinamico, il destinatario Visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.

- Se il destinatario inoltrato non è protetto da un criterio di allegati sicuri, il messaggio e gli allegati verranno recapitati senza alcun segnaposto per l'analisi o gli allegati sicuri.

## <a name="scenarios-where-safe-attachments-doesnt-scan-messages"></a>Scenari in cui gli allegati sicuri non analizzano i messaggi

Esistono scenari in cui gli allegati sicuri non sono in grado di eseguire l'analisi dei messaggi:

- Messaggi nelle cartelle pubbliche.

- Messaggi che vengono instradati fuori e quindi di nuovo nella cassetta postale di un utente utilizzando regole personalizzate.

- Messaggi che vengono spostati (automaticamente o manualmente) dalle cassette postali cloud ad altri percorsi, incluse le cartelle di archiviazione.

- Messaggi eliminati.

- La cartella di ricerca della cassetta postale dell'utente si trova in uno stato di errore.

- Organizzazioni di Exchange online in cui è abilitato l'esclamer. Per risolvere il riguardo, vedere [KB4014438](https://support.microsoft.com/help/4014438).

- [S/MIME)](s-mime-for-message-signing-and-encryption.md) messaggi crittografati.

- L'operazione di recapito dinamico è stata configurata in un criterio di allegati sicuri, ma il destinatario non supporta il recapito dinamico (ad esempio, il destinatario è una cassetta postale in un'organizzazione di Exchange locale). Tuttavia, [collegamenti sicuri in office 365 ATP](set-up-atp-safe-links-policies.md) è in grado di analizzare gli allegati dei file di Office che contengono URL (a seconda del modo in cui sono configurati i collegamenti sicuri).

## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi antimalware

- Se si riceve un file che si desidera inviare a Microsoft per l'analisi, vedere [inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

- Se si riceve un messaggio di posta elettronica (con o senza allegato) che si desidera inviare a Microsoft per l'analisi, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).
