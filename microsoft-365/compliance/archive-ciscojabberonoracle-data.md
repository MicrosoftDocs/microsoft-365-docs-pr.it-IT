---
title: Configurare un connettore per archiviare Cisco Jabber sui dati Oracle in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati da Cisco Jabber su Oracle per Microsoft 365.
ms.openlocfilehash: 8c8e95a9a96767aa227c463c96b04a30d8aac7dc
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054637"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Configurare un connettore per archiviare Cisco Jabber nei dati Oracle

Utilizzare un connettore Veritas nell'Centro conformità Microsoft 365 per importare e archiviare i dati dalla piattaforma Cisco Jabber sulla piattaforma Oracle alle cassette postali degli utenti nell'Microsoft 365 organizzazione. Veritas fornisce un [connettore Cisco Jabber](https://www.veritas.com/insights/merge1/jabber) su Oracle configurato per acquisire elementi dall'origine dati di terze parti (regolarmente) e importare tali elementi in Microsoft 365. Il connettore converte il contenuto, ad esempio operazioni su file, commenti e contenuti condivisi da Cisco Jabber su Oracle in un formato di messaggio di posta elettronica e quindi importa tali elementi nella cassetta postale dell'utente in Microsoft 365.

Dopo l'archiviazione di Cisco Jabber sui dati Oracle nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo di un connettore Cisco Jabber su Oracle per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Panoramica dell'archiviazione di Cisco Jabber sui dati Oracle

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare Cisco Jabber sui dati Oracle in Microsoft 365.

![Flusso di lavoro di archiviazione per Cisco Jabber su dati Oracle](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. L'organizzazione collabora con Cisco Jabber su Oracle per configurare un Cisco Jabber nel sito Oracle.

2. Una volta ogni 24 ore, gli elementi Cisco Jabber su Oracle vengono copiati nel sito Veritas Merge1. Il connettore converte anche Cisco Jabber sugli elementi Oracle in un formato di messaggio di posta elettronica.

3. Il connettore Cisco Jabber su Oracle creato nel Centro conformità Microsoft 365, si connette ogni giorno al sito Veritas Merge1 e trasferisce il contenuto di Jabber in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel [passaggio 3.](#step-3-map-users-and-complete-the-connector-setup) Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Cisco Jabber in Oracle** e gli elementi vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni elemento Jabber contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante dell'elemento.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Merge1 per i connettori Microsoft. A tale scopo, contattare [il supporto tecnico Veritas.](https://www.veritas.com/content/support/en_US) È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore Cisco Jabber su Oracle nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Passaggio 1: Configurare il connettore Cisco Jabber su Oracle

Il primo passaggio consiste nell'accedere alla pagina **Connettori** dati nell'Centro conformità Microsoft 365 e creare un connettore per i dati jabber.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **Cisco Jabber in Oracle.**

2. Nella pagina Descrizione del prodotto **Cisco Jabber su Oracle** fare clic su Aggiungi **connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Passaggio 2: Configurare Cisco Jabber su Oracle nel sito Veritas Merge1

Il secondo passaggio consiste nel configurare il connettore Cisco Jabber su Oracle nel sito Veritas Merge1. Per informazioni su come configurare il connettore Cisco Jabber su Oracle, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore Centro conformità Microsoft 365 visualizzata.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

Per mappare gli utenti e completare la configurazione del connettore Centro conformità Microsoft 365, attenersi alla seguente procedura:

1. Nella pagina **Mappa Cisco Jabber su utenti Oracle** Microsoft 365 utenti, abilitare il mapping automatico degli utenti. Gli elementi Cisco Jabber su Oracle includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un Microsoft 365 utente, gli elementi vengono importati nella cassetta postale dell'utente.

2. Fare **clic** su Avanti, rivedere le impostazioni e quindi passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Passaggio 4: monitorare il connettore Cisco Jabber su Oracle

Dopo aver creato il connettore Cisco Jabber su Oracle, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.

1. Vai a <https://compliance.microsoft.com/> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare **Cisco Jabber** sul connettore Oracle per visualizzare la pagina a comparsa, che contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
