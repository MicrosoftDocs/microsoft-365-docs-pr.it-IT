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
description: Gli amministratori possono ottenere informazioni sulla funzionalità Allegati sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab3fd89c02186dfbdb6c9a3d754a4902d8b945f8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246381"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Allegati sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Allegati sicuri in [Microsoft Defender per Office 365](defender-for-office-365.md) offre un ulteriore livello di protezione per gli allegati di posta elettronica che sono già stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP).](anti-malware-protection.md) In particolare, gli allegati sicuri utilizzano un ambiente virtuale per archiviare gli allegati nei messaggi di posta elettronica prima di essere recapitati ai destinatari (un processo noto come _detonazione)._

La protezione degli allegati sicuri per i messaggi di posta elettronica è controllata dai criteri Allegati sicuri. Non esiste un criterio allegati sicuri predefinito, quindi per ottenere la protezione degli allegati sicuri, è necessario creare **uno o più criteri allegati sicuri.** Per istruzioni, vedi [Configurare i criteri allegati sicuri in Defender per Office 365](set-up-safe-attachments-policies.md).

Nella tabella seguente vengono descritti gli scenari per gli allegati sicuri nelle organizzazioni di Microsoft 365 e Office 365 che includono Microsoft Defender per Office 365 (in altre parole, la mancanza di licenze non è mai un problema negli esempi).

<br>

****

|Scenario|Risultato|
|---|---|
|L'organizzazione Microsoft 365 E5 non dispone di criteri allegati sicuri configurati.|Pat non è protetto da allegati sicuri. <p> Un amministratore deve creare almeno un criterio Allegati sicuri per la protezione degli allegati sicuri per essere attivo. Inoltre, le condizioni del criterio devono includere Pat se Pat deve essere protetto da allegati sicuri.|
|L'organizzazione di Lee ha un criterio allegati sicuri che si applica solo ai dipendenti finanziari. Lee è un membro del reparto vendite.|Lee non è protetto da allegati sicuri. <p> I dipendenti finanziari sono protetti da allegati sicuri, mentre i dipendenti delle vendite (e altri dipendenti) non lo sono.|
|Ieri, un amministratore dell'organizzazione di Jean ha creato un criterio allegati sicuri che si applica a tutti i dipendenti. All'inizio di oggi, Jean ha ricevuto un messaggio di posta elettronica che includeva un allegato.|Jean è protetto da allegati sicuri. <p> In genere, l'applicazione di un nuovo criterio richiede circa 30 minuti.|
|L'organizzazione di Chris dispone di criteri allegati sicuri di lunga data per tutti gli utenti dell'organizzazione. Chris riceve un messaggio di posta elettronica con un allegato e quindi inoltra il messaggio ai destinatari esterni.|Chis è protetto da allegati sicuri. <p> Se anche i destinatari esterni dispongono di criteri allegati sicuri nell'organizzazione, i messaggi inoltrati sono soggetti a tali criteri.|
|

L'analisi degli allegati sicuri avviene nella stessa area in cui si trovano Microsoft 365 dati. Per ulteriori informazioni sull'area geografica del datacenter, vedere [Dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Le funzionalità seguenti si trovano nelle impostazioni globali dei criteri allegati sicuri nel Centro sicurezza & conformità. Tuttavia, queste impostazioni sono abilitate o disabilitate a livello globale e non richiedono criteri allegati sicuri:
>
> - [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).
> - [Sicurezza documenti in Microsoft 365 E5](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Impostazioni dei criteri allegati sicuri

In questa sezione vengono descritte le impostazioni dei criteri allegati sicuri:

- **Risposta malware sconosciuto allegati sicuri**: questa impostazione controlla l'azione per l'analisi malware allegati sicuri nei messaggi di posta elettronica. Le opzioni disponibili sono descritte nella tabella seguente:

  <br>

  ****

  |Opzione|Effetto|Utilizzare quando si desidera:|
  |---|---|---|
  |**Off**|Gli allegati non vengono analizzati per la ricerca di malware dagli allegati sicuri. I messaggi vengono ancora analizzati per la ricerca di malware [dalla protezione antimalware in EOP.](anti-malware-protection.md)|Disattivare l'analisi per i destinatari selezionati. <p> Evitare ritardi non necessari nel routing della posta interna. <p> **Questa opzione non è consigliata per la maggior parte degli utenti. È consigliabile utilizzare questa opzione solo per disattivare l'analisi degli allegati sicuri per i destinatari che ricevono solo messaggi da mittenti attendibili.**|
  |**Monitor**|Recapita i messaggi con allegati e quindi tiene traccia di ciò che accade con il malware rilevato. <p> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Vedere dove viene rilevato malware nell'organizzazione.|
  |**Blocca**|Impedisce il recapito dei messaggi con allegati malware rilevati. <p> I messaggi [vengono messi in](manage-quarantined-messages-and-files.md) quarantena dove solo gli amministratori (non gli utenti finali) possono rivedere, rilasciare o eliminare i messaggi. <p> Blocca automaticamente le istanze future dei messaggi e degli allegati. <p> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Protegge l'organizzazione da attacchi ripetuti utilizzando gli stessi allegati di malware. <p> Questo è il valore predefinito e il valore consigliato nei criteri di sicurezza predefiniti Standard [e Strict.](preset-security-policies.md)|
  |**Sostituisce**|Rimuove gli allegati di malware rilevati. <p> Notifica ai destinatari che gli allegati sono stati rimossi. <p>  I messaggi [vengono messi in](manage-quarantined-messages-and-files.md) quarantena dove solo gli amministratori (non gli utenti finali) possono rivedere, rilasciare o eliminare i messaggi. <p> Il recapito dei messaggi sicuri potrebbe essere ritardato a causa dell'analisi degli allegati sicuri.|Aumentare la visibilità per i destinatari che gli allegati sono stati rimossi a causa di malware rilevato.|
  |**Recapito dinamico**|Recapita immediatamente i messaggi, ma sostituisce gli allegati con segnaposto fino al completamento dell'analisi degli allegati sicuri. <p> Per informazioni dettagliate, vedere [la sezione Recapito dinamico nei criteri allegati](#dynamic-delivery-in-safe-attachments-policies) sicuri più avanti in questo articolo.|Evitare ritardi nei messaggi proteggendo i destinatari da file dannosi. <p> Consentire ai destinatari di visualizzare in anteprima gli allegati in modalità provvisoria durante l'analisi.|
  |

- Reindirizzare l'allegato  al **rilevamento:** abilitare reindirizzare e inviare l'allegato al seguente indirizzo di posta elettronica **:** Per le azioni **Blocca,** Monitor o Sostituisci, inviare messaggi contenenti allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'analisi.

  Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento. Per ulteriori informazioni, vedere [Impostazioni degli allegati sicuri.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- **Applicare la selezione** precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati: l'azione specificata da Allegati sicuri risposta **malware** sconosciuta viene eseguita sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata. Selezionare sempre questa opzione se si seleziona **Abilita reindirizzamento.** In caso contrario, i messaggi potrebbero essere persi.

- **Filtri destinatari:** è necessario specificare le condizioni e le eccezioni del destinatario che determinano a chi si applica il criterio. È possibile utilizzare queste proprietà per le condizioni e le eccezioni:
  - **Il destinatario è**
  - **Il dominio del destinatario è**
  - **Il destinatario è un membro di**

  È possibile utilizzare solo un'eccezione una volta, ma la condizione o l'eccezione può contenere più valori. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

- **Priorità:** se si creano più criteri, è possibile specificare l'ordine in cui vengono applicati. Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

  Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Recapito dinamico nei criteri allegati sicuri

> [!NOTE]
> Il recapito dinamico funziona solo per Exchange Online cassette postali.

L'azione Recapito dinamico nei criteri Allegati sicuri consente di eliminare eventuali ritardi di recapito della posta elettronica causati dall'analisi degli allegati sicuri. Il corpo del messaggio di posta elettronica viene recapitato al destinatario con un segnaposto per ogni allegato. Il segnaposto rimane fino a quando l'allegato non viene trovato sicuro e quindi l'allegato diventa disponibile per l'apertura o il download.

Se viene rilevato che un allegato è dannoso, il messaggio viene messo in quarantena. Solo gli amministratori (non gli utenti finali) possono esaminare, rilasciare o eliminare i messaggi messi in quarantena dall'analisi degli allegati sicuri. Per ulteriori informazioni, vedere [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).

La maggior parte dei pdf e Office documenti può essere visualizzata in anteprima in modalità provvisoria mentre è in corso l'analisi degli allegati sicuri. Se un allegato non è compatibile con il visualizzatore di anteprima recapito dinamico, i destinatari visualizzano un segnaposto per l'allegato fino al completamento dell'analisi degli allegati sicuri.

Se si usa un dispositivo mobile e il rendering dei PDF non viene visualizzato nel visualizzatore di anteprima recapito dinamico nel dispositivo mobile, provare ad aprire il messaggio in Outlook sul Web (in precedenza noto come Outlook Web App) usando il browser per dispositivi mobili.

Ecco alcune considerazioni per il recapito dinamico e i messaggi inoltrati:

- Se il destinatario inoltrato è protetto da un criterio Allegati sicuri che utilizza l'opzione Recapito dinamico, il destinatario visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.
- Se il destinatario inoltrato non è protetto da un criterio Allegati sicuri, il messaggio e gli allegati verranno recapitati senza l'analisi degli allegati sicuri o i segnaposto degli allegati.

Esistono scenari in cui il recapito dinamico non è in grado di sostituire gli allegati nei messaggi. Tra questi scenari sono compresi:

- Messaggi nelle cartelle pubbliche.
- Messaggi instradati all'uscita e quindi di nuovo nella cassetta postale di un utente utilizzando regole personalizzate.
- Messaggi spostati (automaticamente o manualmente) dalle cassette postali cloud in altre posizioni, incluse le cartelle di archiviazione.
- Le regole di Posta in arrivo spostano il messaggio dalla cartella Posta in arrivo in una cartella diversa.
- Messaggi eliminati.
- La cartella di ricerca delle cassette postali dell'utente si trova in uno stato di errore.
- Exchange Online le organizzazioni in cui Exclaimer è abilitato. Per risolvere questo problema, vedere [KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](s-mime-for-message-signing-and-encryption.md) messaggi crittografati.
- L'azione Recapito dinamico è stata configurata in un criterio Allegati sicuri, ma il destinatario non supporta il recapito dinamico(ad esempio, il destinatario è una cassetta postale in un'organizzazione Exchange locale). Tuttavia, [Collegamenti sicuri in Microsoft Defender per Office 365](set-up-safe-links-policies.md) è in grado di analizzare Office file allegati che contengono URL (a seconda di come sono configurate le impostazioni globali per i collegamenti sicuri). [](configure-global-settings-for-safe-links.md)

## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi malware

- Se si riceve un file che si desidera inviare a Microsoft per l'analisi, vedere Inviare malware e non malware [a Microsoft per l'analisi.](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)
- Se si riceve un messaggio di posta elettronica (con o senza allegato) che si desidera inviare a Microsoft per l'analisi, vedere Segnalare messaggi e [file a Microsoft](report-junk-email-messages-to-microsoft.md).
