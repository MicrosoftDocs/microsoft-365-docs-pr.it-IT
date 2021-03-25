---
title: Configurare un connettore per archiviare i dati red tail Speak in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati red tail Speak da Veritas a Microsoft 365. Questo connettore consente di archiviare dati da origini dati di terze parti in Microsoft 365. Dopo l'archiviazione di questi dati, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti.
ms.openlocfilehash: ee9540b4000387454eb177f864407e03abd25bc6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164150"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Configurare un connettore per archiviare i dati redtail Speak

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati da Redtail Speak alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Veritas fornisce un connettore [Redtail Speak](https://globanet.com/redtail/) configurato per acquisire gli elementi dal server SFTP dell'organizzazione in cui gli elementi vengono ricevuti da Redtail. Il connettore converte il contenuto da Redtail Speak in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo aver archiviato i dati di Redtail Speak nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo di un connettore Redtail Speak per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Panoramica dell'archiviazione dei dati Redtail Speak

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati redtail Speak in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati Redtail Speak](../media/RedtailSpeakConnectorWorkflow.png)

1. L'organizzazione collabora con Redtail Speak per configurare e configurare un gateway SMTP in cui i messaggi vengono inoltrati da Redtail Speak al server SFTP dell'organizzazione su base giornaliera.

2. Una volta ogni 24 ore, gli elementi Redtail Speak vengono copiati nel sito Veritas Merge1. Il connettore converte anche gli elementi Redtail Speak in un formato di messaggio di posta elettronica.

3. Il connettore Redtail Speak creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito Veritas Merge1 e trasferisce i messaggi in una posizione sicura di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi Redtail Speak convertiti nelle cassette postali di utenti specifici utilizzando il valore della *proprietà Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Redtail Speak** e gli elementi vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento Redtail Speak contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare un account, contattare il [Supporto clienti Veritas.](https://www.veritas.com/content/support/) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- Nel passaggio 2 è necessario specificare il server SFTP dell'organizzazione. Questo passaggio è necessario affinché Veritas Merge1 possa contattarlo per raccogliere dati Redtail Speak tramite SFTP.

- L'utente che crea il connettore di importazione Redtail Speak nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Importazione/esportazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina Connettori dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Passaggio 1: Configurare il connettore Redtail Speak

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nel Centro conformità Microsoft 365 e creare un connettore per i dati Redtail Speak.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e seleziona **Connettori dati** &gt; **Redtail Speak.**

2. Nella pagina **Redtail Speak** product description selezionare **Add new connector**.

3. Nella pagina **Condizioni per il servizio** selezionare **Accetta**.

4. Immettere un nome univoco che identifichi il connettore e quindi selezionare **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare il connettore Redtail Speak nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore Redtail Speak nel sito Merge1. Per informazioni su come configurare il connettore Redtail Speak, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Dopo aver selezionato **Salva & fine,** viene visualizzata la **pagina Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore, attenersi alla seguente procedura:

1. Nella pagina **Map Redtail Speak users to Microsoft 365 users** abilitare il mapping automatico degli utenti. Gli elementi Redtail Speak includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

2. Selezionare **Avanti**, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Passaggio 4: Monitorare il connettore Redtail Speak

Dopo aver creato il connettore Redtail Speak, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e seleziona **Connettori dati** nel riquadro di spostamento sinistro.

2. Selezionare la **scheda Connettori,** quindi selezionare il **connettore Redtail Speak** per visualizzare la pagina a comparsa. In questa pagina vengono visualizzate le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** selezionare il collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.