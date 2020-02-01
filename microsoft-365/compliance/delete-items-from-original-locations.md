---
title: Eliminare elementi dalla posizione originale
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come utilizzare lo strumento nuovo data Investigation (Preview) nel centro sicurezza & conformità per eliminare gli elementi dai percorsi originali.
ms.openlocfilehash: 2efb57fa2e35cffd3cca5e8f44b648018f0daf1b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595321"
---
# <a name="delete-items-from-their-original-location-preview"></a>Eliminare gli elementi dal percorso originale (anteprima)

La caratteristica per eliminare gli elementi dal percorso originale è in anteprima.

Se si utilizzano indagini sui dati, è possibile eliminare gli elementi dai percorsi originali. Questo significa che è possibile eliminare gli elementi da cassette postali di Exchange, siti di SharePoint e account di OneDrive nell'organizzazione. Poiché gli elementi sono stati raccolti come prova, sono presenti copie degli elementi conservati nel set di prove per ulteriori indagini o come riferimento.

## <a name="before-you-begin"></a>Prima di iniziare

- Per eliminare gli elementi, è necessario assegnare il ruolo di **ricerca ed eliminazione** nel centro sicurezza & Compliance. Questo ruolo viene assegnato per impostazione predefinita al gruppo di ruoli investigatore dati incorporato.

- La procedura descritta in questo argomento presuppone che sia stata eseguita una ricerca associata a un'indagine e che i risultati della ricerca siano stati aggiunti a un set di evidenze. Dopo che i risultati della ricerca sono stati evidenziati, è possibile selezionare uno o più elementi da eliminare. Per ulteriori informazioni, vedere [Search for data in an Investigation](search-for-data.md).

- È importante tenere presente che vengono eliminati solo gli elementi presenti nei percorsi di contenuto originale, ad esempio le cassette postali di Exchange, i siti di SharePoint e gli account di OneDrive. Questi elementi non vengono eliminati dal set di evidenze. Ciò è dovuto al fatto che gli elementi di un set di evidenze sono copie dell'originale. Questi elementi vengono copiati quando sono stati aggiunti i risultati di una ricerca a un set di evidenze.

## <a name="delete-items"></a>Eliminare elementi

Per eliminare gli elementi dal percorso originale, eseguire la procedura seguente:

1. Nello strumento **indagini dati** aprire l'analisi dei dati contenente gli elementi che si desidera eliminare e quindi fare clic sulla scheda **Evidence** .

2. Selezionare gli elementi che si desidera eliminare. È possibile selezionare tutti gli elementi nel set di evidenze oppure selezionare solo un sottoinsieme di elementi.

   > [!NOTE]
   > Se si selezionano gli allegati di un messaggio di posta elettronica o di un file allegato a un documento in SharePoint e OneDrive, l'elemento padre verrà selezionato ed eliminato anche quando l'elemento viene eliminato dal percorso originale. Analogamente, se si seleziona un elemento con allegati, l'elemento padre e tutti gli allegati vengono eliminati.
 
2. Fare clic su **azione** e quindi su **Elimina elementi da percorsi originali**.

   ![Fare clic su azione e quindi su Elimina elementi da percorsi originali](media/DataInvestigationsDeleteItems1.png)

3. Nella pagina riquadro a comparsa verificare il numero di elementi e i documenti figlio correlati che verranno eliminati e quindi fare clic su **Elimina**.

   ![La pagina del riquadro a comparsa Visualizza il numero di elementi e tutti i documenti allegati selezionati per l'eliminazione](media/DataInvestigationsDeleteItems2.png)

   > [!NOTE]
   > Nella schermata precedente, il numero di elementi indica il numero di elementi selezionati per l'eliminazione. Il numero di documenti indica il numero totale di elementi, inclusi i file associati a un elemento padre. Ad esempio, se si seleziona un messaggio di posta elettronica e il messaggio contiene un documento di Word allegato, il numero di elementi e documenti visualizzati in **documenti selezionati sarebbe solo** **1 elementi (2 documenti)**.

È possibile monitorare lo stato del processo **Elimina elementi dal percorso originale** nella scheda **processi** . fare clic sul processo per visualizzare la pagina del riquadro a comparsa.

![Pagina riquadro a comparsa per eliminare gli elementi dal processo percorsi originali](media/DataInvestigationsDeleteItems3.png)

Quando gli elementi del processo vengono eliminati, lo stato del processo è impostato su **esito positivo**. Viene visualizzata anche la data e l'ora del processo completato.

![Processo elementi eliminati completati](media/DataInvestigationsDeleteItems4.png)

> [!NOTE]
> È possibile che venga visualizzato uno stato **parzialmente corretto** per il processo **Elimina elementi dal percorso originale** . Sono presenti diverse situazioni che determinano lo stato del processo. Per ulteriori informazioni, vedere la sezione [eliminazioni parzialmente riuscite](#partially-successful-deletions) in questo articolo.

## <a name="what-happens-when-you-delete-items"></a>Cosa succede quando si eliminano gli elementi

Al momento, quando si eliminano gli elementi dal percorso del contenuto originale, gli elementi vengono *eliminati temporaneamente*. Questo significa che gli elementi vengono spostati in una posizione speciale e conservati fino alla scadenza del periodo di conservazione degli elementi eliminati e un elemento viene contrassegnato per l'eliminazione definitiva da Office 365. Gli elementi con eliminazione temporanea significa che gli utenti possono comunque recuperare tali elementi fino alla scadenza del periodo di conservazione. Di seguito sono riportate le descrizioni su cosa accade quando gli elementi vengono eliminati temporaneamente dalle cassette postali di Exchange e dai siti di SharePoint e OneDrive for business e cosa possono fare gli utenti dopo l'eliminazione degli elementi dai percorsi originali.

- **Cassette postali:** Quando un elemento della cassetta postale viene eliminato temporaneamente, viene spostato nella cartella elementi ripristinabili nella cassetta postale. Questo comportamento è simile a quello in cui un utente elimina un elemento dalla cartella Posta eliminata o Elimina definitivamente un elemento premendo MAIUSC + CANC. A questo punto, l'utente può recuperare l'elemento fino alla scadenza del periodo di conservazione degli elementi eliminati. In Office 365, il periodo di conservazione degli elementi eliminati è di 14 giorni per impostazione predefinita, ma un amministratore può aumentare il periodo di conservazione a 30 giorni. Dopo la scadenza del periodo di conservazione, l'elemento viene spostato in una cartella nascosta (denominata cartella *Purges* ). L'elemento viene rimosso definitivamente da Office 365 alla successiva elaborazione della cassetta postale. Le cassette postali vengono elaborate una volta ogni sette giorni.

- **Siti di SharePoint e OneDrive:** Quando un file o un documento in un sito è stato eliminato temporaneamente, viene spostato nel cestino del sito (denominato anche cestino *principale* ). L'elemento rimane nel Cestino per 93 giorni (il periodo di conservazione degli elementi eliminati nei siti in Office 365). Durante il periodo di 93 giorni, gli elementi eliminati possono ancora essere recuperati da un amministratore della raccolta siti in SharePoint o dall'utente o dall'amministratore in OneDrive. È inoltre possibile eliminare gli elementi dal Cestino secondario. Quando ciò accade, gli elementi vengono spostati nel cestino per la raccolta siti, che è denominata cestino *secondario* . Il periodo di conservazione è di 93 giorni sia per i cestini del primo stadio che per quelli del secondo stadio. Questo significa che la conservazione del Cestino secondario viene avviata quando l'elemento viene inizialmente eliminato. Questo significa che il tempo totale di conservazione massimo è di 93 giorni per entrambi i cestini. Se un elemento viene eliminato dal Cestino secondario (manualmente da un amministratore o automaticamente quando scade il periodo di conservazione), non è più accessibile da parte di un amministratore.

## <a name="what-happens-if-a-content-location-is-on-hold"></a>Cosa succede se un percorso di contenuto è in attesa

In Office 365, le cassette postali e i siti possono essere inseriti in attesa o assegnati a un criterio di conservazione. Questo significa che non viene rimosso definitivamente finché il periodo di conservazione per un elemento non scade o finché non viene rimosso il blocco. Anche se si elimina un elemento dal percorso originale, è possibile che l'elemento non venga rimosso definitivamente da Office 365. Ad esempio, se una cassetta postale è in attesa, gli elementi eliminati temporaneamente vengono spostati in Purges o DiscoveryHold sottocartelle nella cartella elementi ripristinabili e conservati fino alla scadenza del periodo di conservazione o della durata del blocco. Per i siti, una copia dell'elemento che viene spostata nel Cestino viene copiata nella raccolta conservazione che viene creata quando un blocco o un criterio di conservazione viene applicato a un sito.

## <a name="partially-successful-deletions"></a>Eliminazioni parzialmente riuscite

Dopo aver completato l'esecuzione del processo di **eliminazione degli elementi dal percorso originale** , è possibile che sia stato eseguito un processo **parzialmente corretto**. In generale, questo stato indica che il processo è stato eseguito correttamente, ma non tutti gli elementi sono stati eliminati temporaneamente. Di seguito è indicato un elenco dei motivi che determinano le eliminazioni parzialmente riuscite:

- Un elemento della cassetta postale era già presente nella cartella elementi ripristinabili nella cassetta postale di origine.

- Un elemento della cassetta postale è stato eliminato dalla cartella elementi ripristinabili nella cassetta postale di origine.

- Un documento è già presente nel Cestino principale in un sito di SharePoint o OneDrive.

- Un documento è stato spostato in un altro sito di SharePoint dopo che è stato aggiunto al set di prove. In questo caso, il documento non viene spostato nel cestino nel sito in cui è stato spostato.

- Un documento è stato eliminato definitivamente in SharePoint o OneDrive (spostato nel Cestino secondario) dopo che è stato aggiunto al set di prove.
