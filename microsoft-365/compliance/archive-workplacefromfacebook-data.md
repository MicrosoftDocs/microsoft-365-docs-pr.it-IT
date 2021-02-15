---
title: Configurare un connettore per archiviare Workplace dai dati di Facebook in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati da Workplace da Facebook, archiviato nel sito Merge1 di Globanet, in Microsoft 365. La configurazione di un connettore richiede l'utilizzo di Globanet Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter usare funzionalità di conformità come conservazione a livello legale, ricerca di contenuti e criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 0bcea998e857365b512b2a6f773dca17a85c08f9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619852"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Configurare un connettore per archiviare Workplace dai dati di Facebook

Usare un connettore Globanet nel Centro conformità Microsoft 365 per importare e archiviare i dati da Workplace da Facebook alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Globanet fornisce un connettore [Workplace da Facebook](https://globanet.com/workplace/) configurato per acquisire elementi dall'origine dati di terze parti (regolarmente) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto come chat, allegati, post e video da Workplace in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati di Workplace nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'uso di Workplace dal connettore Facebook per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Panoramica dell'archiviazione di Workplace dai dati di Facebook

La panoramica seguente illustra il processo di utilizzo di un connettore per archiviare i dati di Workplace in Microsoft 365.

![Archiviare il flusso di lavoro per Workplace dai dati di Facebook](../media/WorkplaceConnectorWorkflow.png)

1. L'organizzazione collabora con Workplace da Facebook per configurare un sito di Workplace.

2. Una volta ogni 24 ore, gli elementi da Workplace vengono copiati nel sito Globanet Merge1. Il connettore converte inoltre il contenuto di questi elementi in un formato di messaggio di posta elettronica.

3. Il connettore Workplace da Facebook creato nel Centro conformità Microsoft 365, si connette a Globanet Merge1 ogni giorno e trasferisce gli elementi di Workplace in una posizione sicura di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel passaggio 3. Viene creata una sottocartella nella cartella Posta in arrivo denominata **Workplace da Facebook** e gli elementi di Workplace vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento di Workplace contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante di chat o post.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Globanet Merge1 per i connettori Microsoft. Per creare questo account, contattare [il supporto clienti Di Globanet.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Creare un'integrazione personalizzata in per recuperare i dati da Workplace tramite LE API per https://my.workplace.com/work/admin/apps/ scopi di conformità ed eDiscovery.

   Durante la creazione dell'integrazione, la piattaforma Workplace genera un set di credenziali univoche utilizzate per generare token utilizzati per l'autenticazione. Questi token vengono utilizzati nella configurazione guidata del connettore Workplace da Facebook nel passaggio 2. Per istruzioni dettagliate su come creare le applicazioni, vedere il manuale dell'utente [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)

- L'utente che crea l'area di lavoro dal connettore Facebook nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Passaggio 1: Configurare l'area di lavoro dal connettore Facebook

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft 365 e creare un connettore per i dati di Workplace.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati** Workplace da  >  **Facebook.**

2. Nella pagina **di descrizione del prodotto Workplace from Facebook,** fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni per il servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore, quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>Passaggio 2: Configurare l'area di lavoro dal connettore Facebook nel sito Globanet Merge1

Il secondo passaggio consiste nel configurare l'area di lavoro dal connettore Facebook nel sito Merge1. Per informazioni su come configurare Workplace dal connettore Facebook, vedere la Guida per l'utente di [Merge1 Third-Party Connectors.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)

Dopo aver fatto **clic su & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti esterni a utenti di Microsoft 365** abilitare il mapping automatico degli utenti. Gli elementi di Workplace includono una proprietà denominata *Posta* elettronica che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le  impostazioni e quindi passare alla pagina Connettori dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Passaggio 4: monitorare l'area di lavoro dal connettore Facebook

Dopo aver creato l'area di lavoro dal connettore Facebook, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori,** quindi selezionare il connettore **Workplace from Facebook** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo log contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
