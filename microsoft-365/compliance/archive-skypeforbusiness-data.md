---
title: Configurare un connettore per archiviare Skype for Business dati in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati da Skype for Business a Microsoft 365.
ms.openlocfilehash: 93128af0c7f305cb2bef55efd5520de77555a222
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054836"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data-preview"></a>Configurare un connettore per archiviare Skype for Business dati (anteprima)

Utilizzare un connettore Veritas nell'Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma Skype for Business alle cassette postali degli utenti nell'Microsoft 365 organizzazione. Veritas fornisce un [connettore di](https://www.veritas.com/en/au/insights/merge1/skype-for-business) Skype for Business configurato per acquisire elementi dall'origine dati di terze parti (a intervalli regolari) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio i messaggi tra utenti, chat persistenti e messaggi di conferenza da Skype for Business in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo Skype for Business dati archiviati nelle cassette postali degli utenti, è possibile applicare Microsoft 365 di conformità, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo Skype for Business connettore per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-skype-for-business-data"></a>Panoramica dell'archiviazione Skype for Business dati

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati Skype for Business in Microsoft 365.

![Flusso di lavoro di archiviazione per Skype for Business dati](../media/SkypeforBusinessConnectorWorkflow.png)

1. L'organizzazione collabora con Skype for Business per configurare un sito Skype for Business locale.

2. Una volta ogni 24 ore, Skype for Business elementi vengono copiati nel sito Veritas Merge1. Il connettore converte inoltre Skype for Business elementi in un formato di messaggio di posta elettronica.

3. Il connettore di Skype for Business creato nel Centro conformità Microsoft 365, si connette ogni giorno al sito Veritas Merge1 e trasferisce il contenuto Skype for Business in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Una sottocartella nella cartella Posta **in arrivo** denominata Skype for Business viene creata nelle cassette postali degli utenti e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni Skype for Business contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Creare un account Merge1 per i connettori Microsoft. A tale scopo, contattare [il supporto tecnico Veritas.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore di Skype for Business nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Di importazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Passaggio 1: Configurare il connettore di Skype for Business

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nell'Centro conformità Microsoft 365 e creare un connettore per Skype for Business dati.

1. Passare a <https://compliance.microsoft.com> e fare clic su **Connettori**  >  **dati Skype for Business**.

2. Nella **pagina** Skype for Business descrizione del prodotto fare clic **su Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare la Skype for Business nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore Skype for Business nel sito Veritas Merge1. Per informazioni su come configurare il connettore Skype for Business, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore Centro conformità Microsoft 365 visualizzata.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina **Mapping Skype for Business utenti a Microsoft 365 utenti,** abilitare il mapping automatico degli utenti. Gli Skype for Business includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Passaggio 4: Monitorare il connettore Skype for Business

Dopo aver creato il Skype for Business, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.

1. Vai a <https://compliance.microsoft.com/> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il Skype for Business per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore. 

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
