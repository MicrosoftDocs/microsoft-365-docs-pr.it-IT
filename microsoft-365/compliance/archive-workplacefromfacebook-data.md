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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati da Workplace da Facebook, archiviato nel sito Merge1 di Veritas, in Microsoft 365. La configurazione di un connettore richiede l'utilizzo di Veritas Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365 in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 25221b1d71fe106f0f6dcf9c629414aeb0de8709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163830"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Configurare un connettore per archiviare Workplace dai dati di Facebook

Utilizzare un connettore Veritas nel centro Microsoft 365 conformità per importare e archiviare i dati da Workplace da Facebook alle cassette postali degli utenti nell'Microsoft 365 aziendale. Veritas fornisce un connettore [Workplace da Facebook](https://globanet.com/workplace/) configurato per acquisire elementi dall'origine dati di terze parti (regolarmente) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio chat, allegati, post e video da Workplace in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati di Workplace nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'uso del connettore Workplace da Facebook per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Panoramica dell'archiviazione di Workplace dai dati di Facebook

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di Workplace in Microsoft 365.

![Archiviazione del flusso di lavoro per Workplace dai dati di Facebook](../media/WorkplaceConnectorWorkflow.png)

1. L'organizzazione collabora con Workplace da Facebook per configurare e configurare un sito di Workplace.

2. Una volta ogni 24 ore, gli elementi di Workplace vengono copiati nel sito Veritas Merge1. Il connettore converte anche il contenuto di questi elementi in un formato di messaggio di posta elettronica.

3. Il connettore Workplace from Facebook creato nel Centro conformità di Microsoft 365, si connette ogni giorno a Veritas Merge1 e trasferisce gli elementi di Workplace in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel passaggio 3. Viene creata una sottocartella nella cartella Posta in arrivo denominata **Workplace da Facebook** e gli elementi di Workplace vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento workplace contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante di chat o post.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://globanet.com/ms-connectors-contact) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- Creare un'integrazione personalizzata in per recuperare i dati da Workplace tramite API per https://my.workplace.com/work/admin/apps/ conformità ed eDiscovery.

   Durante la creazione dell'integrazione, la piattaforma Workplace genera un set di credenziali univoche utilizzate per generare token utilizzati per l'autenticazione. Questi token vengono usati nella configurazione guidata del connettore Workplace da Facebook nel passaggio 2. Per istruzioni dettagliate su come creare le applicazioni, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- L'utente che crea l'area di lavoro dal connettore Facebook nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Di importazione delle cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nel Centro Microsoft 365 conformità. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Passaggio 1: Configurare Workplace da Facebook Connector

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft 365 e creare un connettore per i dati di Workplace.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fai clic su **Connettori dati** Workplace da  >  **Facebook.**

2. Nella pagina **Workplace from Facebook** product description fare clic su Add **connector.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore Workplace da Facebook nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare Workplace dal connettore Facebook nel sito Merge1. Per informazioni su come configurare Workplace dal connettore Facebook, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro Microsoft 365 conformità.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore nel Centro Microsoft 365 conformità, attenersi alla seguente procedura:

1. Nella pagina **Mapping utenti esterni a Microsoft 365** utenti, abilitare il mapping automatico degli utenti. Gli elementi Workplace includono una proprietà denominata *Email* che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Passaggio 4: Monitorare Workplace da Facebook Connector

Dopo aver creato il connettore Workplace da Facebook, è possibile visualizzare lo stato del connettore nel Centro Microsoft 365 conformità.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore **Area di lavoro da Facebook** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene informazioni sui dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.