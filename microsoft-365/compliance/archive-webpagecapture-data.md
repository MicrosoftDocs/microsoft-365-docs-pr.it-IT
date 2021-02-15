---
title: Configurare un connettore per archiviare i dati delle pagine Web in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati di acquisizione di pagine Web da Globanet in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuti e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619822"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Configurare un connettore per archiviare i dati delle pagine Web

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine Web alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Globanet fornisce un [connettore di](https://globanet.com/webpage-capture) acquisizione pagine Web che acquisisce pagine Web specifiche (e tutti i collegamenti in tali pagine) in un sito Web specifico o in un intero dominio. Il connettore converte il contenuto della pagina Web in formato PDF, PNG o personalizzato, quindi allega i file convertiti a un messaggio di posta elettronica e quindi importa tali elementi di posta elettronica nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato il contenuto delle pagine Web nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'uso di un connettore di acquisizione di pagine Web per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-webpage-data"></a>Panoramica dell'archiviazione dei dati delle pagine Web

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare il contenuto delle pagine Web in Microsoft 365.

![Archiviazione del flusso di lavoro per i dati delle pagine Web](../media/WebPageCaptureConnectorWorkflow.png)

1. L'organizzazione collabora con l'origine della pagina Web per configurare un sito di acquisizione pagine Web.

2. Una volta ogni 24 ore, gli elementi delle origini della pagina Web vengono copiati nel sito Globanet Merge1. Il connettore converte e allega anche il contenuto di una pagina Web in un messaggio di posta elettronica.

3. Il connettore di acquisizione pagine Web creato nel Centro conformità Microsoft 365, si connette al sito Globanet Merge1 ogni giorno e trasferisce gli elementi della pagina Web in un percorso sicuro di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi delle pagine Web convertite nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto [nel passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli  utenti viene creata una sottocartella nella cartella Posta in arrivo denominata Acquisizione pagine Web e gli elementi della pagina Web vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento della pagina Web contiene questa proprietà, che viene popolata con gli indirizzi di posta elettronica forniti quando si configura il connettore di acquisizione pagine Web [nel passaggio 2.](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare questo account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact/) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- È necessario utilizzare il supporto di Globanet per configurare un formato di file personalizzato in cui convertire gli elementi della pagina Web. Per ulteriori informazioni, vedere il Manuale dell'utente di Merge1 Third-Party Connectors in 

- L'utente che crea il connettore di acquisizione pagine Web nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-webpage-capture-connector"></a>Passaggio 1: Configurare il connettore di acquisizione pagine Web

Il primo passaggio consiste nell'accedere ai **connettori** dati e creare un connettore per i dati di origine della pagina Web.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su Acquisizione pagina Web   >  **connettori dati.**

2. Nella pagina **di descrizione del prodotto Acquisizione** pagina Web fare clic su Aggiungi **connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore, quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>Passaggio 2: Configurare il connettore di acquisizione pagine Web nel sito Globanet Merge1

Il secondo passaggio consiste nel configurare il connettore di acquisizione pagine Web nel sito Globanet Merge1. Per informazioni su come configurare il connettore di acquisizione di pagine Web, vedere [guida all'utente Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, seguire la procedura seguente:

1. Nella pagina **Mappa pagina Web Acquisire utenti a utenti di Microsoft 365** abilitare il mapping automatico degli utenti. Gli elementi di acquisizione della pagina Web includono una proprietà denominata *Posta* elettronica, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-webpage-capture-connector"></a>Passaggio 4: Monitorare il connettore di acquisizione pagine Web

Dopo aver creato il connettore di acquisizione pagine Web, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore **di acquisizione pagine** Web per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene i dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
