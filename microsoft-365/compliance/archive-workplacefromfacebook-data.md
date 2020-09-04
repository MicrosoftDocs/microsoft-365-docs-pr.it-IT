---
title: Configurare un connettore per l'archiviazione dei luoghi di lavoro dai dati di Facebook in Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore per l'importazione e l'archiviazione dei dati dal luogo di lavoro da Facebook, archiviati nel sito Merge1 di Globanet, in Microsoft 365. La configurazione di un connettore richiede l'utilizzo di Globanet questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: b57ad60133fdb7cee7db24781755bda032b10a89
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362005"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data-preview"></a>Configurare un connettore per l'archiviazione sul posto di lavoro da Facebook Data (anteprima)

Utilizzare un connettore di Globanet nel centro conformità di Microsoft 365 per importare e archiviare i dati dal luogo di lavoro da Facebook alle cassette postali degli utenti nell'organizzazione Microsoft 365. Globanet fornisce un [posto di lavoro dal connettore Facebook](https://globanet.com/workplace/) configurato per acquisire elementi dall'origine dati di terze parti (su base regolare) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio chat, allegati, post e video dal luogo di lavoro a un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo che i dati sul posto di lavoro vengono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione e etichette e conformità della comunicazione. L'utilizzo di area di lavoro dal connettore Facebook per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Panoramica del luogo di lavoro di archiviazione da Facebook Data

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati sul posto di lavoro in Microsoft 365.

![Flusso di lavoro per l'archiviazione per il luogo da Facebook](../media/WorkplaceConnectorWorkflow.png)

1. L'organizzazione lavora con il luogo di lavoro da Facebook per impostare e configurare un sito di lavoro.

2. Una volta ogni 24 ore, gli elementi provenienti dal luogo di lavoro vengono copiati nel sito Merge1 di Globanet. Il connettore converte anche il contenuto di tali elementi in un formato di messaggio di posta elettronica.

3. Il luogo di lavoro dal connettore Facebook creato nel centro conformità Microsoft 365, si connette a Globanet Merge1 ogni giorno e trasferisce gli elementi di lavoro in una posizione di archiviazione sicura di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà di *posta elettronica* del mapping automatico degli utenti, come descritto nel passaggio 3. Viene creata una sottocartella nella cartella posta in arrivo denominata **luogo di lavoro da Facebook** e gli elementi di lavoro vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della proprietà di *posta elettronica* . Tutti gli elementi di lavoro contengono questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni chat o post partecipante.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 accettando i termini e le condizioni per il luogo di lavoro dal connettore Facebook. In questa sezione è necessario contattare il [supporto clienti di Globanet](https://globanet.com/contact-us/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- Creare un'integrazione personalizzata per https://my.workplace.com/work/admin/apps/ recuperare i dati dal luogo di lavoro tramite API per la conformità e gli scopi di eDiscovery.

   Quando si crea l'integrazione, la piattaforma sul luogo di lavoro genera un set di credenziali univoche utilizzate per generare token utilizzati per l'autenticazione. Questi token vengono utilizzati nella procedura guidata di configurazione del connettore Facebook del passaggio 2. Per istruzioni dettagliate su come creare le applicazioni, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- L'utente che crea il luogo di lavoro dal connettore Facebook nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **dei connettori dati** nel centro conformità di Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Passaggio 1: configurare il luogo di lavoro dal connettore Facebook

Il primo passaggio consiste nell'accedere alla pagina **dei connettori dati** nel centro conformità di Microsoft 365 e creare un connettore per i dati sul posto di lavoro.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **connettori dati**  >  **sul posto di lavoro da Facebook**.

2. Nella pagina **area di lavoro da Facebook** Descrizione prodotto fare clic su **Aggiungi connettore**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti**.

5. Accedere al proprio account di Merge1 per configurare il connettore.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>Passaggio 2: configurare il luogo di lavoro dal connettore Facebook nel sito Merge1 di Globanet

Il secondo passaggio consiste nel configurare il luogo di lavoro dal connettore Facebook nel sito Merge1. Per informazioni su come configurare il luogo di lavoro dal connettore Facebook, vedere [Merge1 di terze parti dei connettori utente](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Dopo aver fatto clic su **salva & fine**, è possibile tornare al centro conformità di Microsoft 365 alla pagina **mapping utenti** nella procedura guidata del connettore.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per eseguire il mapping degli utenti e completare il connettore configurato nel centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina mapping **utenti esterni a Microsoft 365** , abilitare il mapping automatico degli utenti. Gli elementi di lavoro includono una proprietà denominata *posta elettronica* che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Nella pagina **consenso amministratore** fare clic sul pulsante **Fornisci consenso** . L'utente verrà reindirizzato al sito Microsoft. Fare clic su **accetta** per fornire il consenso.
  
   L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Microsoft 365 e quindi accettare la richiesta di consenso. Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di amministratore globale per accettare la richiesta.

3. Fare clic su **Avanti**, esaminare le impostazioni, quindi passare alla pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Passaggio 4: monitorare il luogo di lavoro dal connettore Facebook

Dopo aver creato il luogo di lavoro dal connettore Facebook, è possibile visualizzare lo stato del connettore nel centro conformità di Microsoft 365.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **connettori dati** nel NAV sinistro.

2. Fare clic sulla scheda **connettori** e quindi selezionare il connettore di **lavoro da Facebook** per visualizzare la pagina del riquadro a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **stato connettore con origine**fare clic sul collegamento **Scarica log** per aprire o salvare il registro di stato del connettore. Questo log contiene informazioni sui dati che sono stati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento, non è supportato l'importazione di allegati di dimensioni superiori a 10 MB, ma il supporto per gli elementi di grandi dimensioni sarà disponibile in una data successiva.
