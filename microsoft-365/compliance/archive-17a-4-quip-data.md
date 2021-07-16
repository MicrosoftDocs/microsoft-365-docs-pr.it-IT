---
title: Configurare un connettore per archiviare i dati quip in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore Quip DataParser da 17a-4 per importare e archiviare i dati quip in Microsoft 365.
ms.openlocfilehash: e3379e238b0142522d4161149fd38892843e6eae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454446"
---
# <a name="set-up-a-connector-to-archive-quip-data"></a>Configurare un connettore per archiviare i dati quip

Utilizzare [Quip DataParser](https://www.17a-4.com/quip-dataparser/) da 17a-4 LLC per importare e archiviare i dati da Quip alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale. DataParser include un connettore Quip configurato per acquisire elementi da un'origine dati di terze parti e importare tali elementi in Microsoft 365. Il connettore Quip DataParser converte i dati quip in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo aver archiviato i dati quip nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore Quip per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-quip-data"></a>Panoramica dell'archiviazione dei dati quip

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare i dati quip in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati quip da 17a a 4](../media/QuipDataParserConnectorWorkflow.png)

1. L'organizzazione collabora con 17a-4 per configurare Quip DataParser.

2. A intervalli regolari, gli elementi Quip vengono raccolti da DataParser. DataParser converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.

3. Il connettore Quip DataParser creato nel Centro conformità Microsoft 365 si connette a DataParser e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **Quip DataParser** e gli elementi Quip vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento Quip contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Creare un account DataParser per i connettori Microsoft. A tale scopo, contattare [17a-4 LLC](https://www.17a-4.com/contact/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore Quip DataParser nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-a-quip-dataparser-connector"></a>Passaggio 1: Configurare un connettore Quip DataParser

Il primo passaggio consiste nell'accedere alla pagina Connettori dati nel Centro conformità Microsoft 365 e creare un connettore 17a-4 per i dati quip.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **Quip DataParser**.

2. Nella pagina **Descrizione prodotto Quip DataParser** fare clic su **Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedi al tuo account 17a-4 e completa i passaggi della procedura guidata di connessione Quip DataParser.

## <a name="step-2-configure-the-quip-dataparser-connector"></a>Passaggio 2: Configurare il connettore Quip DataParser

Utilizzare il supporto 17a-4 per configurare il connettore Quip DataParser.

## <a name="step-3-map-users"></a>Passaggio 3: mappare gli utenti

Il connettore Quip DataParser mappa automaticamente gli utenti ai propri Microsoft 365 di posta elettronica prima di importare i dati in Microsoft 365.

## <a name="step-4-monitor-the-quip-dataparser-connector"></a>Passaggio 4: Monitorare il connettore Quip DataParser

Dopo aver creato un connettore Quip DataParser, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda** Connettori e quindi selezionare il connettore Quip DataParser creato per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
