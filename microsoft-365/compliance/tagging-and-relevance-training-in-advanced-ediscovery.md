---
title: Formazione su tagging e pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sui passaggi per contrassegnare e quindi utilizzare un esempio di formazione di 40 file durante la fase di formazione sulla rilevanza di Advanced eDiscovery.
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769221"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a>Formazione su tagging e pertinenza in Advanced eDiscovery
  
In questo articolo viene descritta la procedura per l'utilizzo del modulo di formazione sulla rilevanza in Advanced eDiscovery.
  
Dopo aver completato la valutazione in Advanced eDiscovery e aver inserito la fase di formazione sulla rilevanza, nella scheda Tag per il tagging viene inserito un esempio di formazione di 40 file.
  
## <a name="performing-relevance-training"></a>Esecuzione della formazione sulla rilevanza

1. Nella scheda **Tag \>** di pertinenza il riquadro Tagging viene visualizzato per impostazione predefinita nel riquadro sinistro e i file di esempio vengono visualizzati uno alla volta per il tagging.

    ![Pannello Tag di pertinenza](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Nella scheda **Tag** viene visualizzato il nome visualizzato del file. Può trattarsi del percorso, dell'oggetto del messaggio di posta elettronica, del titolo o del nome definito dall'utente. L'ID, il percorso del file o il percorso di testo possono essere copiati facendo clic con il pulsante destro del mouse sul percorso del file.

    Le  statistiche di tagging della scheda Tag mostrano il numero di esempio del file (nella parte superiore del riquadro sinistro), il numero del file attualmente visualizzato fuori dal totale dei file nell'esempio (nella parte inferiore del riquadro destro) e il numero totale corrente di file contrassegnati nell'esempio (nella parte inferiore del riquadro sinistro), che cambia man mano che tagi i file. Questo vale per qualsiasi tagging per pertinenza eseguito, sia in valutazione, formazione, preparazione o test.

    Le icone che indicano l'esistenza di commenti, tag e file di famiglia vengono visualizzate nella visualizzazione file in una barra sopra il file.

2. Determinare la pertinenza del file per il caso e contrassegnare il file utilizzando i pulsanti di icona dell'opzione tagging o i tasti di scelta rapida, come illustrato nella tabella seguente:

   |**Opzione di tagging**|**Descrizione**|**Scelta rapida da tastiera**|**Aggiunta di tag in blocco ai tasti di scelta rapida (per più problemi)**|
   |-----|-----|-----|-----|
   |R  <br/> |Pertinente  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |NR  <br/> |Non rilevante  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Ignora  <br/> |Ignora  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Quando esistono più problemi per un file, dopo aver contrassegnato un problema, la selezione passa al problema successivo (se presente).  

   - Le parole chiave definite dall'amministratore o dal responsabile del caso durante l'evidenziazione delle parole chiave (parole chiave evidenziate per impostazione di pertinenza) verranno visualizzate (in colori specificati) per identificare i file rilevanti durante l'aggiunta di \> tag. Se una parola chiave ha una sottolineatura doppia, è possibile fare clic per visualizzare una descrizione comando con la descrizione della parola chiave.

     Facoltativamente, nella scheda **Tag** fare clic su **Impostazioni tag** per impostare le opzioni seguenti:

      ![Impostazioni Tag di pertinenza](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Tag in** blocco: utilizzare questa opzione per  assegnare più problemi a un file selezionando Tutti per impostare il  tag per il file selezionato per tutti i problemi (sostituisce i problemi già contrassegnati) o selezionando Il resto per applicare il tag ai problemi senza tag rimanenti. L'opzione selezionata rimane attiva per tutti i casi di questo utente fino a quando non viene modificata da tale utente (l'impostazione è per utente per tutti i casi dell'utente).

   - **Tag automatico:** selezionare questa casella di controllo per impostare altri problemi per un file come non rilevanti dopo un singolo tagging pertinente.

   - **Avanzamento automatico:** selezionare questa casella di controllo per spostare la selezione del file visualizzato nel file successivo quando si contrassegna l'ultimo problema o solo quello senza tag.

    I file ignorati non verranno considerati ai fini della formazione per pertinenza e del punteggio di pertinenza.

3. I commenti a testo libero, associati a un file,  possono essere visualizzati e modificati tramite l'opzione Commento nell'elenco a discesa del riquadro sinistro. (facoltativo)

4. Le linee guida per il tagging possono essere visualizzate selezionando l'opzione Linee guida per il **tagging** nell'elenco a discesa del riquadro sinistro.

5. Dopo aver completato il tagging di tutti i file nell'elenco e aver calcolato i risultati, fare clic su **Calcola.** Viene **visualizzata** la scheda Traccia.  

## <a name="working-with-the-sample-files-list"></a>Uso dell'elenco dei file di esempio

L'elenco dei file di esempio consente di visualizzare un elenco dei file in un esempio di formazione ed eseguire varie azioni su uno o più file. Nella scheda **Tag** di rilevanza, nel riquadro sinistro dei file di esempio viene visualizzato un elenco di file di esempio per l'elaborazione con processi di valutazione, formazione, aggiornamento e \>  incoerenze. 
  
1. Nella scheda **Tag di \> pertinenza** selezionare i file di esempio nell'elenco a discesa del riquadro sinistro. I file di esempio sono elencati nel riquadro sinistro.

    ![Elenco di file campione per Tag di pertinenza](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Selezionare un campione o un numero di file specifico immettendo o selezionandone il numero nelle **caselle Esempio** **o File.**

   - Un numero di sequenza di file è elencato nella colonna sinistra dell'elenco dei file visualizzati nella **scheda** Tag. Facendo clic sull'intestazione, l'ordine originale visualizzato dei file torna all'ordine originale.

   - Facendo clic su una riga di file, il relativo contenuto viene visualizzato nel riquadro destro.

   - Spostarsi tra i file nell'esempio corrente utilizzando le opzioni della barra dei menu inferiore. Sono inoltre disponibili i tasti di scelta rapida di spostamento:
  
     - Per passare al primo file dell'esempio: `Shift + Ctrl + <`

     - Per passare al file precedente nell'esempio: `Shift + <`

     - Per passare al file successivo nell'esempio: `Shift + >`

     - Per passare all'ultimo file dell'esempio: `Shift + Ctrl + >`
