---
title: Creare, testare e ottimizzare i criteri di prevenzione della perdita dei dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: In questo articolo viene illustrato come creare, testare e ottimizzare un criterio DLP in base alle esigenze dell'organizzazione.
ms.openlocfilehash: 9b43899969ab0fdc5d67b051db36c0b245f7811e
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663193"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Creare, testare e ottimizzare i criteri di prevenzione della perdita dei dati

La prevenzione della perdita dei dati consente di impedire la condivisione involontaria o accidentale di informazioni riservate.

DLP esamina i messaggi di posta elettronica e i file per informazioni riservate, ad esempio un numero di carta di credito. Utilizzando DLP è possibile rilevare informazioni riservate ed eseguire azioni quali:

- Registrare l'evento a scopo di controllo
- Visualizzare un avviso per l'utente finale che invia il messaggio di posta elettronica o condivide il file
- Bloccare attivamente la condivisione di file o di posta elettronica

## <a name="permissions"></a>Autorizzazioni

I membri del team conformità addetti alla creazione dei criteri DLP necessitano delle autorizzazioni per accedere al Centro conformità. Per impostazione predefinita, l'amministratore tenant potrà concedere l'accesso ai responsabili della conformità e ad altre persone. attenersi alla seguente procedura:
  
1. Creare un gruppo in Microsoft 365 e aggiungervi i responsabili della conformità.
    
2. Creare un gruppo di ruoli nella pagina **Autorizzazioni** del Centro sicurezza e conformità. 

3. Durante la creazione del gruppo di ruoli, utilizzare la sezione **Selezione** ruoli per aggiungere il ruolo seguente al gruppo di ruoli: **Dlp Compliance Management.**
    
4. Usare la sezione **Scegli membri** per aggiungere il gruppo di Microsoft 365 creato in precedenza al gruppo di ruoli.

Utilizzare il **ruolo Gestione conformità DLP** di sola visualizzazione per creare un gruppo di ruoli con privilegi di sola visualizzazione per i criteri DLP e i report DLP.

Per altre informazioni, vedere [Concedere agli utenti l'accesso al Centro conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie per creare e applicare un criterio DLP per non applicare i criteri.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Come vengono rilevate le informazioni riservate dalla prevenzione della perdita dei dati

DLP trova le informazioni riservate in base alla corrispondenza del criterio di espressione regolare (RegEx), in combinazione con altri indicatori, ad esempio la prossimità di determinate parole chiave ai modelli corrispondenti. Ad esempio, un numero di carta di credito VISA ha 16 cifre. Tuttavia, tali cifre possono essere scritte in modi diversi, ad esempio 1111-1111-1111-1111, 1111 1111 1111 1111 o 1111111111111111111111.

Qualsiasi stringa di 16 cifre non è necessariamente un numero di carta di credito, può essere un numero di ticket di un sistema help desk o un numero di serie di un componente hardware. Per distinguere tra un numero di carta di credito e una stringa di 16 cifre innocua, viene eseguito un calcolo (checksum) per verificare che i numeri corrispondano a uno schema noto dei vari marchi di carta di credito.

Se DLP trova parole chiave come "VISA" o "AMEX", vicino ai valori di data che potrebbero essere la data di scadenza della carta di credito, DLP utilizza anche questi dati per decidere se la stringa è un numero di carta di credito o meno.

In altre parole, DLP è abbastanza intelligente da riconoscere la differenza tra queste due stringhe di testo in un messaggio di posta elettronica:

- "Puoi ordinare un nuovo portatile. Usa il mio numero VISA 1111-1111-1111-1111, scade il 22/11 e inviami la data di consegna stimata quando è stata utilizzata."
- "Il mio numero di serie del portatile è 2222-2222-2222-2222 ed è stato acquistato l'11/11/2010. A proposito, il mio visto di viaggio è ancora approvato?"

Vedere [le definizioni delle entità del tipo di](sensitive-information-type-entity-definitions.md) informazioni riservate che spiegano come viene rilevato ogni tipo di informazione.

## <a name="where-to-start-with-data-loss-prevention"></a>Dove iniziare con la prevenzione della perdita di dati

Quando i rischi di perdita dei dati non sono del tutto ovvi, è difficile capire dove è necessario iniziare esattamente con l'implementazione della prevenzione della perdita dei dati. Fortunatamente, i criteri DLP possono essere eseguiti in "modalità test", consentendo di valutarne l'efficacia e l'accuratezza prima di attivarli.

I criteri DLP per Exchange Online possono essere gestiti tramite l'interfaccia di amministrazione di Exchange. Tuttavia, è possibile configurare i criteri DLP per tutti i carichi di lavoro tramite il Centro sicurezza & conformità, in modo che sia possibile utilizzarli per le dimostrazioni in questo articolo. Nel Centro sicurezza & conformità, i criteri DLP sono presenti in Criteri di **prevenzione della perdita dei**  >  **dati.** Scegliere **Crea un criterio** da avviare.

Microsoft 365 offre un'ampia gamma di [modelli di criteri DLP](what-the-dlp-policy-templates-include.md) che è possibile utilizzare per creare criteri. Supponiamo che tu sia un'azienda australiana. Puoi filtrare i modelli in Australia e scegliere Financial, Medical and Health e Privacy.

![Opzione per scegliere il paese o l'area geografica](../media/DLP-create-test-tune-choose-country.png)

Per questa dimostrazione sceglierò i dati di identificazione personale (PII) australiani, che includono i tipi di informazioni del codice fiscale australiano (TFN) e del numero di patente di guida.

![Opzione per scegliere un modello di criteri](../media/DLP-create-test-tune-choose-policy-template.png)

Assegnare un nome al nuovo criterio DLP. Il nome predefinito corrisponderà al modello di criteri DLP, ma è consigliabile scegliere un nome più descrittivo, poiché è possibile creare più criteri dallo stesso modello.

![Opzione per assegnare un nome al criterio](../media/DLP-create-test-tune-name-policy.png)

Scegliere le posizioni a cui verrà applicato il criterio. I criteri DLP possono essere applicati a Exchange Online, SharePoint Online e OneDrive for Business. Lascerà questo criterio configurato per l'applicazione a tutte le posizioni.

![Opzione per scegliere tutte le posizioni](../media/DLP-create-test-tune-choose-locations.png)

Al primo passaggio **delle impostazioni** dei criteri, accetta solo le impostazioni predefinite per il momento. È possibile personalizzare i criteri DLP, ma le impostazioni predefinite sono un ottimo punto di partenza.

![Opzioni per personalizzare il tipo di contenuto da proteggere](../media/DLP-create-test-tune-default-customization-settings.png)

Dopo aver fatto clic su Avanti,** verrà visualizzata una **pagina** impostazioni dei criteri aggiuntiva con altre opzioni di personalizzazione. Per un criterio che stai semplicemente testando, ecco dove puoi iniziare a apportare alcune modifiche.

- I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet. I suggerimenti per i criteri visualizzano avvisi agli utenti che stanno per violare un criterio DLP. Ad esempio, un utente di Outlook riceverà un avviso che indica che il file allegato contiene numeri di carta di credito e causerà il rifiuto della posta elettronica. L'obiettivo dei suggerimenti per i criteri è arrestare il comportamento non conforme prima che si verifica.
- Ho anche ridotto il numero di istanze da 10 a 1, in modo che questo criterio rilevi qualsiasi condivisione di dati personali australiani, non solo la condivisione in blocco dei dati.
- Ho anche aggiunto un altro destinatario al messaggio di posta elettronica del rapporto operazioni non consentite.

![Impostazioni aggiuntive dei criteri](../media/DLP-create-test-tune-more-policy-settings.png)

Infine, ho configurato questo criterio per l'esecuzione iniziale in modalità test. Nota che è disponibile anche un'opzione per disabilitare i suggerimenti per i criteri in modalità test. In questo modo è possibile disporre di suggerimenti per i criteri abilitati nel criterio, ma decidere se mostrarli o sopprimerli durante il test.

![Opzione per testare prima i criteri](../media/DLP-create-test-tune-test-mode.png)

Nella schermata di revisione finale fare clic **su Crea** per completare la creazione del criterio.

## <a name="test-a-dlp-policy"></a>Testare un criterio DLP

Il nuovo criterio DLP inizierà a essere attivo entro circa 1 ora. Puoi sederti e attendere che sia attivato dalla normale attività dell'utente oppure puoi provare a attivarlo manualmente. In precedenza sono stato collegato [alle definizioni delle](sensitive-information-type-entity-definitions.md)entità del tipo di informazioni riservate, che forniscono informazioni su come attivare le corrispondenze DLP.

Ad esempio, il criterio DLP creato per questo articolo rileverà i numeri di file fiscali australiani (TFN). In base alla documentazione, la corrispondenza si basa sui criteri seguenti.

![Documentazione sul numero di file fiscale australia](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Per dimostrare il rilevamento TFN in modo piuttosto smussato, un messaggio di posta elettronica con le parole "Tax file number" e una stringa di 9 cifre a distanza ravvicinata attraversa senza problemi. Il motivo per cui non attiva il criterio DLP è che la stringa di 9 cifre deve superare il checksum che indica che si tratta di un TFN valido e non solo di una stringa di numeri innocua.

![Numero di file fiscale Australia che non supera il checksum](../media/DLP-create-test-tune-email-test1.png)

In confronto, un messaggio di posta elettronica con le parole "Tax file number" e un TFN valido che supera il checksum attiverà il criterio. Per la registrazione qui, il TFN che uso è stato preso da un sito Web che genera TFN validi, ma non originali. Tali siti sono molto utili perché uno degli errori più comuni durante il test di un criterio DLP è l'utilizzo di un numero falso non valido e non supererà il checksum (e pertanto non attiverà il criterio).

![Numero di file fiscale australia che supera il checksum](../media/DLP-create-test-tune-email-test2.png)

Il messaggio di posta elettronica del rapporto operazioni non consentite include il tipo di informazioni riservate rilevate, il numero di istanze rilevate e il livello di sicurezza del rilevamento.

![Rapporto operazioni non consentite che mostra il numero di file fiscale rilevato](../media/DLP-create-test-tune-email-incident-report.png)

Se si lascia il criterio DLP in modalità test e si analizzano i messaggi di posta elettronica del rapporto operazioni non consentite, è possibile iniziare a capire l'accuratezza del criterio DLP e l'efficacia con cui verrà applicato. Oltre ai rapporti operazioni non consentite, è possibile utilizzare i report [DLP](view-the-dlp-reports.md) per visualizzare una visualizzazione aggregata delle corrispondenze dei criteri in tutto il tenant.

## <a name="tune-a-dlp-policy"></a>Ottimizzare un criterio DLP

Quando si analizzano i risultati dei criteri, potrebbe essere necessario apportare alcune modifiche al comportamento dei criteri. Come semplice esempio, è possibile determinare che un TFN nella posta elettronica non è un problema (lo è ancora, ma è possibile farlo per dimostrazione), ma due o più istanze sono un problema. Più istanze potrebbero essere uno scenario rischioso, ad esempio un dipendente che invia tramite posta elettronica un'esportazione CSV dal database delle risorse umane a una parte esterna, ad esempio un servizio di contabilità esterno. Sicuramente qualcosa che preferisci rilevare e bloccare.

Nel Centro sicurezza & conformità è possibile modificare un criterio esistente per modificare il comportamento.

![Opzione per modificare i criteri](../media/DLP-create-test-tune-edit-policy.png)
 
È possibile modificare le impostazioni della posizione in modo che il criterio sia applicato solo a carichi di lavoro specifici o a siti e account specifici.

![Opzioni per scegliere posizioni specifiche](../media/DLP-create-test-tune-edit-locations.png)

È inoltre possibile modificare le impostazioni dei criteri e modificare le regole in base alle proprie esigenze.

![Opzione per modificare la regola](../media/DLP-create-test-tune-edit-rule.png)

Quando si modifica una regola all'interno di un criterio DLP, è possibile modificare:

- Condizioni, inclusi il tipo e il numero di istanze di dati sensibili che attiveranno la regola.
- Azioni eseguite, ad esempio la limitazione dell'accesso al contenuto.
- Notifiche utente, ovvero suggerimenti per i criteri visualizzati all'utente nel client di posta elettronica o nel Web browser.
- Sostituzioni utente, che determinano se gli utenti possono scegliere di continuare comunque con la posta elettronica o la condivisione di file.
- Report operazioni non consentite, per informare gli amministratori.

![Opzioni per modificare parti di una regola](../media/DLP-create-test-tune-editing-options.png)

Per questa dimostrazione ho aggiunto notifiche utente al criterio (prestare attenzione a eseguire questa operazione senza un'adeguata formazione di sensibilizzazione degli utenti) e ho consentito agli utenti di ignorare il criterio con una motivazione aziendale o contrassegnarlo come falso positivo. Si noti che è anche possibile personalizzare il testo del messaggio di posta elettronica e del suggerimento per i criteri se si desidera includere informazioni aggiuntive sui criteri dell'organizzazione o chiedere agli utenti di contattare il supporto in caso di domande.

![Opzioni per notifiche e sostituzioni utente](../media/DLP-create-test-tune-user-notifications.png)

Il criterio contiene due regole per la gestione di volumi elevati e volumi bassi, quindi assicurati di modificare entrambe le regole con le azioni desiderate. Questa è un'opportunità per trattare i casi in modo diverso a seconda delle loro caratteristiche. Ad esempio, potresti consentire sostituzioni per violazioni di volume ridotto, ma non consentire sostituzioni per violazioni di volume elevato.

![Una regola per volume elevato e una regola per volume basso](../media/DLP-create-test-tune-two-rules.png)

Inoltre, se si desidera effettivamente bloccare o limitare l'accesso al contenuto che viola i criteri, è necessario configurare un'azione sulla regola per farlo.

![Opzione per limitare l'accesso al contenuto](../media/DLP-create-test-tune-restrict-access-action.png)

Dopo aver salvato le modifiche alle impostazioni dei criteri, è inoltre necessario tornare alla pagina delle impostazioni principale per il criterio e abilitare l'opzione per visualizzare i suggerimenti per i criteri per gli utenti mentre il criterio è in modalità test. Si tratta di un modo efficace per introdurre i criteri DLP agli utenti finali e per formare la sensibilizzazione degli utenti, senza rischiare troppi falsi positivi che influiscono sulla produttività.

![Opzione per visualizzare i suggerimenti per i criteri in modalità test](../media/DLP-create-test-tune-show-policy-tips.png)

Sul lato server (o sul lato cloud, se si preferisce), la modifica potrebbe non essere immediatamente effettiva a causa di vari intervalli di elaborazione. Se si sta apportando una modifica al criterio DLP che consente di visualizzare nuovi suggerimenti per i criteri a un utente, è possibile che l'utente non veda le modifiche immediatamente effettive nel client Outlook, che verifica la presenza di modifiche dei criteri ogni 24 ore. Se vuoi velocizzare i test, puoi usare questa correzione del Registro di sistema per cancellare l'indicatore dell'ora dell'ultimo [download dalla chiave PolicyNudges.](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451) Outlook scarierà le informazioni più recenti sui criteri al successivo riavvio e inizierà a comporre un messaggio di posta elettronica.

Se i suggerimenti per i criteri sono abilitati, l'utente inizierà a visualizzare i suggerimenti in Outlook e potrà segnalare falsi positivi quando si verificano.

![Suggerimento per i criteri con opzione per segnalare falsi positivi](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Analizzare i falsi positivi

I modelli di criteri DLP non sono perfetti. È probabile che si verifichino alcuni falsi positivi nell'ambiente ed è per questo che è così importante semplificare la distribuzione dlp, prendendo il tempo necessario per testare e ottimizzare adeguatamente i criteri.

Ecco un esempio di falso positivo. Questo messaggio di posta elettronica è piuttosto innocuo. L'utente fornisce il proprio numero di cellulare a qualcuno e include la firma di posta elettronica.

![Messaggio di posta elettronica che mostra informazioni falsi positivi](../media/DLP-create-test-tune-false-positive-email.png)
 
Ma l'utente vede un suggerimento per i criteri che avvisa che il messaggio di posta elettronica contiene informazioni riservate, in particolare, un numero di patente di guida australiana.

![Opzione per segnalare falsi positivi nel suggerimento per i criteri](../media/DLP-create-test-tune-policy-tip-closeup.png)

L'utente può segnalare il falso positivo e l'amministratore può esaminare il motivo per cui si è verificato. Nel messaggio di posta elettronica del rapporto operazioni non consentite, il messaggio viene contrassegnato come falso positivo.

![Rapporto operazioni non consentite che mostra falsi positivi](../media/DLP-create-test-tune-false-positive-incident-report.png)

Questo caso della patente di guida è un buon esempio da vedere. Il motivo per cui si è verificato questo falso positivo è che il tipo "Australian Driver's License" verrà attivato da qualsiasi stringa di 9 cifre (anche una che fa parte di una stringa di 10 cifre), entro 300 caratteri di prossimità alle parole chiave "sydney nsw" (senza distinzione tra maiuscole e minuscole). Pertanto, viene attivato dal numero di telefono e dalla firma di posta elettronica, solo perché l'utente si verifica a Sydney.


Un'opzione è quella di rimuovere il tipo di informazioni sulla patente australiana dal criterio. È presente perché fa parte del modello di criteri DLP, ma non è obbligato a usarlo. Se sei interessato solo ai numeri di file fiscali e non alle licenze di driver, puoi semplicemente rimuoverlo. Ad esempio, è possibile rimuoverlo dalla regola di volume basso nel criterio, ma lasciarlo nella regola di volume elevato in modo che gli elenchi di più licenze driver siano ancora rilevati.

![Opzione per eliminare il tipo di informazioni sensibili dalla regola](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
Un'altra opzione è semplicemente aumentare il numero di istanze, in modo che un volume basso di licenze di driver viene rilevato solo quando sono presenti più istanze.

![Opzione per modificare il numero di istanze](../media/DLP-create-test-tune-edit-instance-count.png)

Oltre a modificare il numero di istanze, puoi anche modificare l'accuratezza della corrispondenza (o il livello di confidenza). Se il tipo di informazioni riservate include più modelli, è possibile modificare l'accuratezza della corrispondenza nella regola, in modo che la regola corrisponda solo a modelli specifici. Ad esempio, per ridurre i falsi positivi, è possibile impostare l'accuratezza della corrispondenza della regola in modo che corrisponda solo al modello con il livello di probabilità più alto. Comprendere come viene calcolato il livello di confidenza è un po' complicato (e al di fuori dell'ambito di questo post), ma ecco una buona spiegazione di come usare il livello di probabilità per ottimizzare [le regole.](data-loss-prevention-policies.md#match-accuracy)

Infine, se si desidera ottenere anche un po' più avanzato, è possibile personalizzare qualsiasi tipo di informazione sensibile. Ad esempio, è possibile rimuovere "Sydney NSW" dall'elenco di parole chiave per il numero di patente di guida [dell'Australia,](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)per eliminare il falso positivo attivato in precedenza. Per informazioni su come eseguire questa operazione utilizzando XML e PowerShell, vedere personalizzazione di un [tipo di informazioni riservate predefinito.](customize-a-built-in-sensitive-information-type.md)

## <a name="turn-on-a-dlp-policy"></a>Attivare un criterio DLP

Quando si è soddisfatti che il criterio DLP rilevi in modo accurato ed efficace i tipi di informazioni riservate e che gli utenti finali siano pronti a gestire i criteri in essere, è possibile abilitare il criterio.

![Opzione per attivare i criteri](../media/DLP-create-test-tune-turn-on-policy.png)
 
Se si è in attesa di vedere quando il criterio avrà effetto, connettersi [a & PowerShell per](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità ed eseguire il cmdlet [Get-DlpCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy) per visualizzare DistributionStatus.

![Esecuzione del cmdlet in PowerShell](../media/DLP-create-test-tune-PowerShell.png)

Dopo aver attivare il criterio DLP, è necessario eseguire alcuni test finali per verificare che siano in corso le azioni previste per i criteri. Se si sta provando a testare elementi come i dati della carta di credito, esistono siti Web online con informazioni su come generare una carta di credito di esempio o altre informazioni personali che supereranno i checksum e attiveranno i criteri.

I criteri che consentono le sostituzioni utente presenteranno tale opzione all'utente come parte del suggerimento per i criteri.

![Suggerimento per i criteri che consente l'override dell'utente](../media/DLP-create-test-tune-override-option.png)

I criteri che limitano il contenuto presenteranno l'avviso all'utente come parte del suggerimento per i criteri e impediranno loro di inviare il messaggio di posta elettronica.

![Suggerimento per i criteri per la limitazione del contenuto](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Riepilogo

I criteri di prevenzione della perdita dei dati sono utili per le organizzazioni di tutti i tipi. Il test di alcuni criteri DLP è un esercizio a basso rischio a causa del controllo che si ha su elementi come suggerimenti per i criteri, sostituzioni dell'utente finale e report operazioni non consentite. È possibile testare in modalità non interattiva alcuni criteri DLP per vedere il tipo di violazioni già in corso nell'organizzazione, quindi creare criteri con basse percentuali di falsi positivi, informare gli utenti su ciò che è consentito e non consentito e quindi implementare i criteri DLP all'organizzazione.
