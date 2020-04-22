---
title: Usare le utilità di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Informazioni sulle utilità in Advanced eDiscovery, tra cui log del caso, dati di cancellazione, errori di processo, modifica della pertinenza e analisi della trasparenza.  '
ms.openlocfilehash: d4495920110916fdd5b07201d50080605ba177b1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633391"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a>Usare le utilità di Advanced eDiscovery (classico)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Le utilità visualizzate e disponibili in Advanced eDiscovery dipendono dai ruoli contesto e utente.
  
## <a name="case-log"></a>Registro case

Il registro dei casi fornisce un elenco dettagliato delle attività di elaborazione delle applicazioni, che possono essere utilizzate per la verifica, la risoluzione dei problemi e per l'indirizzamento di errori e avvisi. Il registro può essere generato e archiviato localmente nell'host o nel server oppure inviato direttamente a un indirizzo di posta elettronica.
  
Il file di registro può essere scaricato anche nel computer del client. L'opzione download client può essere abilitata o disabilitata in base alla configurazione e al ruolo utente.
  
1. Sulla barra dei menu, fare clic sull'icona **cremagliera** . 
    
2. Nella scheda **utilità di impostazioni \> e utilità** Selezionare ** \> installazione log dei casi**.
    
3. Selezionare il **livello di registrazione** come indicato di seguito: 
    
  - **Standard**: include i dati di log di base. Questa opzione è in genere necessaria per il monitoraggio e deve essere utilizzata se non diversamente consigliato.
    
  - **Minimal**: utilizzato per casi molto grandi e restituisce solo i dati più recenti.
    
4. Fare clic su **Run case log**. Il log viene generato e viene visualizzato il percorso. Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro Stato attività.
    
## <a name="clear-data"></a>Cancellare i dati

Se è necessario eliminare o reinizializzare i dati del caso, è necessario inizializzare l'istanza del database. L'utilità Cancella dati consente di eliminare tutte le voci specificate dal database del caso, dai file di testo, dalla cartella del caso e dai risultati accumulati. La funzione può essere eseguita solo da un amministratore.
  
> [!IMPORTANT]
> Questa azione non è reversibile e cancellerà tutti i tag di pertinenza e l'analisi eseguiti dall'esperto. Salvare un backup dei dati, se necessario. Utilizzare questa opzione con estrema attenzione. L'eliminazione dei file contrassegnati e classificati può influire sui risultati della pertinenza. 
  
1. Sulla barra dei menu, fare clic sull'icona **cremagliera** . 
    
2. Nella scheda **utilità di impostazioni \> e utilità** Selezionare **Annulla installazione dati \> **.
    
3. Selezionare un'opzione per l'inizializzazione delle informazioni:
    
  - **Pertinenza**: Elimina tutti i lavori in pertinenza, tra cui la definizione dei carichi e l'associazione dei file ai carichi. Elimina tutti gli esempi e il tagging.
    
  - **Quasi duplicati e thread di posta elettronica**: consente di eliminare tutte le informazioni di analisi di quasi duplicati e thread di posta elettronica.
    
  - **Temi**: Elimina i dati correlati ai temi.
    
  - **Esporta cronologia**: Elimina le informazioni sulla cronologia dei batch di esportazione.
    
4. Fare clic su **Pulisci dati**. I dati del caso sono deselezionati. Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro **stato attività** . 
    
## <a name="modify-relevance"></a>Modifica pertinenza

In questa sezione viene descritto come ignorare o eseguire il rollback di un esempio di pertinenza.
  
1. Sulla barra dei menu, fare clic sull'icona **cremagliera** . 
    
2. Nella scheda **utilità di impostazioni \> e utilità** Selezionare **modifica pertinenza**.
    
3. Selezionare una delle opzioni seguenti: 
    
  - **Ignora il campione corrente-per l'utente corrente**: questo tag, come **Ignora**, tutti i file senza tag nell'esempio Open case dell'utente che esegue l'utilità. L'elaborazione della pertinenza non verrà eseguita nei file contrassegnati come **Ignora**.
    
  - **Ignora campione corrente-tutti gli esempi aperti**: questo tag, come **Ignora**, tutti i file senza tag in tutti gli esempi aperti per tutti gli utenti. Questa opzione non è consigliata se gli utenti sono attualmente tagging campioni.
    
  - **Rollback ultimo esempio**: viene eseguito il rollback dell'ultimo esempio di Training relativo alla pertinenza completata, indipendentemente dal fatto che sia prima o dopo il processo di calcolo. Il rollback di un esempio di catch-up non è consentito.
    
4. Fare clic su **Esegui** per eseguire. 
    
## <a name="transparency-analysis"></a>Analisi della trasparenza

L'utilità di analisi della trasparenza attiva una visualizzazione dettagliata dei file e il relativo punteggio di pertinenza assegnato. Il rapporto può essere utilizzato come verifica di integrità o per confrontare la pertinenza di un file definito da un revisore umano rispetto alla pertinenza assegnata da Advanced eDiscovery. 
  
Oltre ai punteggi di pertinenza, Advanced eDiscovery calcola e assegna i pesi delle parole chiave che considerano il contesto di parole chiave. La stessa parola di un file può essere assegnata a pesi diversi, in base al contesto e alla posizione. Ogni parola chiave è contrassegnata usando una scala crescente di colore che spazia dal giallo all'arancio scuro e dalle diverse sfumature di grigio. La codifica a colori viene utilizzata per indicare visivamente il contributo positivo o negativo relativo alla parola al Punteggio di pertinenza. 
  
In uno scenario con più problemi, è possibile generare un report di analisi della trasparenza per ogni problema.
  
1. Sulla barra dei menu, fare clic sull'icona **cremagliera** . 
    
2. Nella scheda **Utilità impostazioni e \> utilità** selezionare **installazione analisi \> trasparenza**.
    
3. In * * file ID * *, immettere l'ID file del file da elaborare.
    
4. Nell'elenco **problema** selezionare il problema pertinente. 
    
5. Fare clic su **analisi trasparenza**. Al termine, viene visualizzato il rapporto analisi trasparenza per il file, che Mostra come i colori delle parole chiave contrassegnate sono correlati al Punteggio di pertinenza generale.
    
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Definizione delle impostazioni del case e del tenant](define-case-and-tenant-settings-in-advanced-ediscovery.md)

