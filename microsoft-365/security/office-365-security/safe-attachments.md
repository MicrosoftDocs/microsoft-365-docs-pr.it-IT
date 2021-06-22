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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Gli amministratori possono conoscere la funzionalità Cassaforte allegati in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 127d862d235abc4cd81f62679b97077c7a80bd70
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054387"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Cassaforte Allegati in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cassaforte Gli allegati in [Microsoft Defender per Office 365](defender-for-office-365.md) offre un ulteriore livello di protezione per gli allegati di posta elettronica che sono già stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP).](anti-malware-protection.md) In particolare, Cassaforte allegati utilizza un ambiente virtuale per archiviare gli allegati nei messaggi di posta elettronica prima di essere recapitati ai destinatari (un processo noto come _detonazione)._

Cassaforte La protezione degli allegati per i messaggi di posta elettronica è controllata Cassaforte criteri allegati. Non esiste un criterio Cassaforte allegati predefiniti, pertanto per ottenere la protezione degli allegati Cassaforte, è necessario creare uno o più criteri Cassaforte **allegati.** Per istruzioni, vedi [Configurare i criteri Cassaforte allegati in Defender per Office 365](set-up-safe-attachments-policies.md).

Nella tabella seguente vengono descritti gli scenari per gli allegati Cassaforte nelle organizzazioni Microsoft 365 e Office 365 che includono Microsoft Defender per Office 365 (in altre parole, la mancanza di licenze non è mai un problema negli esempi).

<br>

****

|Scenario|Risultato|
|---|---|
|L'organizzazione Microsoft 365 E5 non dispone di criteri Cassaforte allegati configurati.|Pat non è protetto da Cassaforte allegati. <p> Un amministratore deve creare almeno un criterio Cassaforte allegati per Cassaforte protezione degli allegati sia attiva. Inoltre, le condizioni del criterio devono includere Pat se Pat deve essere protetto da Cassaforte allegati.|
|L'organizzazione di Lee dispone di un criterio Cassaforte allegati che si applica solo ai dipendenti finanziari. Lee è un membro del reparto vendite.|Lee non è protetto da Cassaforte allegati. <p> I dipendenti finanziari sono protetti da Cassaforte allegati, mentre i dipendenti delle vendite (e altri dipendenti) non lo sono.|
|Ieri, un amministratore dell'organizzazione di Jean ha creato un criterio Cassaforte allegati che si applica a tutti i dipendenti. All'inizio di oggi, Jean ha ricevuto un messaggio di posta elettronica che includeva un allegato.|Jean è protetto da Cassaforte allegati. <p> In genere, l'applicazione di un nuovo criterio richiede circa 30 minuti.|
|L'organizzazione di Chris dispone di criteri Cassaforte allegati per tutti gli utenti dell'organizzazione. Chris riceve un messaggio di posta elettronica con un allegato e quindi inoltra il messaggio ai destinatari esterni.|Chis è protetto da Cassaforte allegati. <p> Se i destinatari esterni hanno anche Cassaforte allegati nell'organizzazione, i messaggi inoltrati sono soggetti a tali criteri.|
|

Cassaforte L'analisi degli allegati avviene nella stessa area in cui si trovano Microsoft 365 dati. Per ulteriori informazioni sull'area geografica del datacenter, vedere [Dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Le funzionalità seguenti si trovano nelle impostazioni globali dei criteri Cassaforte allegati nel Microsoft 365 Defender portale. Tuttavia, queste impostazioni sono abilitate o disabilitate a livello globale e non richiedono criteri Cassaforte allegati:
>
> - [Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Sicurezza documenti in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Cassaforte Impostazioni dei criteri allegati

In questa sezione vengono descritte le impostazioni dei criteri Cassaforte allegati:

- **Cassaforte allegati risposta malware sconosciuta**: Questa impostazione controlla l'azione per Cassaforte allegati l'analisi malware nei messaggi di posta elettronica. Le opzioni disponibili sono descritte nella tabella seguente:

  <br>

  ****

  |Opzione|Effetto|Utilizzare quando si desidera:|
  |---|---|---|
  |**Disattivato**|Gli allegati non vengono analizzati per la ricerca di malware Cassaforte allegati. I messaggi vengono ancora analizzati per la ricerca di malware [dalla protezione antimalware in EOP.](anti-malware-protection.md)|Disattivare l'analisi per i destinatari selezionati. <p> Evitare ritardi non necessari nel routing della posta interna. <p> **Questa opzione non è consigliata per la maggior parte degli utenti. È consigliabile utilizzare questa opzione solo per disattivare l'Cassaforte allegati per i destinatari che ricevono solo messaggi da mittenti attendibili.**|
  |**Monitor**|Recapita i messaggi con allegati e quindi tiene traccia di ciò che accade con il malware rilevato. <p> Il recapito di messaggi sicuri potrebbe essere ritardato a causa dell'Cassaforte degli allegati.|Vedere dove viene rilevato malware nell'organizzazione.|
  |**Blocca**|Impedisce il recapito dei messaggi con allegati malware rilevati. <p> I messaggi [vengono messi in](manage-quarantined-messages-and-files.md) quarantena dove solo gli amministratori (non gli utenti) possono rivedere, rilasciare o eliminare i messaggi. <p> Blocca automaticamente le istanze future dei messaggi e degli allegati. <p> Il recapito di messaggi sicuri potrebbe essere ritardato a causa dell'Cassaforte degli allegati.|Protegge l'organizzazione da attacchi ripetuti utilizzando gli stessi allegati di malware. <p> Questo è il valore predefinito e il valore consigliato nei criteri di sicurezza predefiniti Standard [e Strict.](preset-security-policies.md)|
  |**Sostituisce**|Rimuove gli allegati di malware rilevati. <p> Notifica ai destinatari che gli allegati sono stati rimossi. <p>  I messaggi [vengono messi in](manage-quarantined-messages-and-files.md) quarantena dove solo gli amministratori (non gli utenti) possono rivedere, rilasciare o eliminare i messaggi. <p> Il recapito di messaggi sicuri potrebbe essere ritardato a causa dell'Cassaforte degli allegati.|Aumentare la visibilità per i destinatari che gli allegati sono stati rimossi a causa di malware rilevato.|
  |**Recapito dinamico**|Recapita immediatamente i messaggi, ma sostituisce gli allegati con segnaposto fino al completamento Cassaforte'analisi degli allegati. <p> Per informazioni dettagliate, vedere [la sezione Recapito dinamico nei criteri Cassaforte allegati](#dynamic-delivery-in-safe-attachments-policies) più avanti in questo articolo.|Evitare ritardi nei messaggi proteggendo i destinatari da file dannosi. <p> Consentire ai destinatari di visualizzare in anteprima gli allegati in modalità provvisoria durante l'analisi.|
  |

- Reindirizzare l'allegato  al **rilevamento:** abilitare reindirizzare e inviare l'allegato al seguente indirizzo di posta elettronica **:** Per le azioni **Blocca,** Monitor o Sostituisci, inviare messaggi contenenti allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'analisi.

  Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento. Per ulteriori informazioni, vedere [impostazioni Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Applicare la selezione precedente se si verifica il **timeout** o l'errore dell'analisi antimalware per gli allegati: l'azione specificata da **Cassaforte Allegati** risposta malware sconosciuta viene eseguita sui messaggi anche quando non è possibile completare l'analisi degli allegati di Cassaforte. Selezionare sempre questa opzione se si seleziona **Abilita reindirizzamento.** In caso contrario, i messaggi potrebbero essere persi.

- **Filtri destinatari:** è necessario specificare le condizioni e le eccezioni del destinatario che determinano a chi si applica il criterio. È possibile utilizzare queste proprietà per le condizioni e le eccezioni:
  - **Il destinatario è**
  - **Il dominio del destinatario è**
  - **Il destinatario è un membro di**

  È possibile utilizzare solo un'eccezione una volta, ma la condizione o l'eccezione può contenere più valori. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

- **Priorità:** se si creano più criteri, è possibile specificare l'ordine in cui vengono applicati. Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

  Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Recapito dinamico nei criteri Cassaforte allegati

> [!NOTE]
> Il recapito dinamico funziona solo per Exchange Online cassette postali.

L'azione Recapito dinamico nei criteri Cassaforte allegati cerca di eliminare eventuali ritardi di recapito della posta elettronica causati dall'Cassaforte allegati. Il corpo del messaggio di posta elettronica viene recapitato al destinatario con un segnaposto per ogni allegato. Il segnaposto rimane fino a quando l'allegato non viene trovato sicuro e quindi l'allegato diventa disponibile per l'apertura o il download.

Se viene rilevato che un allegato è dannoso, il messaggio viene messo in quarantena. Solo gli amministratori (non gli utenti) possono esaminare, rilasciare o eliminare i messaggi messi in quarantena Cassaforte allegati. Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

La maggior parte dei pdf e Office documenti può essere visualizzata in anteprima in modalità provvisoria mentre Cassaforte'analisi degli allegati è in corso. Se un allegato non è compatibile con il visualizzatore di anteprima recapito dinamico, i destinatari visualizzano un segnaposto per l'allegato fino al completamento Cassaforte'analisi degli allegati.

Se stai usando un dispositivo mobile e i PDF non vengono rendering nel visualizzatore di anteprima recapito dinamico nel dispositivo mobile, prova ad aprire il messaggio in Outlook sul web (in precedenza noto come Outlook Web App) usando il browser per dispositivi mobili.

Ecco alcune considerazioni per il recapito dinamico e i messaggi inoltrati:

- Se il destinatario inoltrato è protetto da un criterio allegati Cassaforte che utilizza l'opzione Recapito dinamico, il destinatario visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.
- Se il destinatario inoltrato non è protetto da un criterio allegati Cassaforte, il messaggio e gli allegati verranno recapitati senza alcun segnaposto Cassaforte allegati o allegati.

Esistono scenari in cui il recapito dinamico non è in grado di sostituire gli allegati nei messaggi. Tra questi scenari sono compresi:

- Messaggi nelle cartelle pubbliche.
- Messaggi instradati all'uscita e quindi di nuovo nella cassetta postale di un utente utilizzando regole personalizzate.
- Messaggi spostati (automaticamente o manualmente) dalle cassette postali cloud in altre posizioni, incluse le cartelle di archiviazione.
- Le regole di Posta in arrivo spostano il messaggio dalla cartella Posta in arrivo in una cartella diversa.
- Messaggi eliminati.
- La cartella di ricerca delle cassette postali dell'utente si trova in uno stato di errore.
- Exchange Online le organizzazioni in cui Exclaimer è abilitato. Per risolvere questo problema, vedere [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) messaggi crittografati.
- L'azione Recapito dinamico è stata configurata in un criterio Allegati di Cassaforte, ma il destinatario non supporta il recapito dinamico(ad esempio, il destinatario è una cassetta postale in un'organizzazione Exchange locale). Tuttavia, [Cassaforte collegamenti in Microsoft Defender per Office 365](set-up-safe-links-policies.md) è in grado di analizzare file allegati Office [](configure-global-settings-for-safe-links.md) che contengono URL (a seconda di come sono configurate le impostazioni globali per i collegamenti Cassaforte).

## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi malware

- Se si riceve un file che si desidera inviare a Microsoft per l'analisi, vedere Inviare malware e non malware [a Microsoft per l'analisi.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
- Se si riceve un messaggio di posta elettronica (con o senza allegato) che si desidera inviare a Microsoft per l'analisi, vedere Segnalare messaggi e [file a Microsoft](report-junk-email-messages-to-microsoft.md).
