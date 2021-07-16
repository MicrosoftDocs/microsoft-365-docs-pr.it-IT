---
title: Configurare un connettore per archiviare i dati ice Connessione Chat in Microsoft 365
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
description: Informazioni su come configurare e usare un connettore ICE Connessione Chat DataParser 17a-4 per importare e archiviare i dati ice Connessione Chat in Microsoft 365.
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454482"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a>Configurare un connettore per archiviare i dati ice Connessione Chat

Utilizzare [ICE DataParser](https://www.17a-4.com/ice-dataparser/) da 17a-4 LLC per importare e archiviare i dati da ICE Connessione Chat alle cassette postali degli utenti nell'organizzazione Microsoft 365 locale. DataParser include un connettore ICE Chat configurato per acquisire elementi da un'origine dati di terze parti e importare tali elementi in Microsoft 365. Il connettore ICE DataParser converte i dati ice Connessione Chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali degli utenti in Microsoft 365.

Dopo l'archiviazione dei dati ice Connessione Chat nelle cassette postali degli utenti, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione e conformità delle comunicazioni. L'utilizzo di un connettore ICE DataParser per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-ice-chat-data"></a>Panoramica dell'archiviazione dei dati di ICE Chat

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore dati per archiviare i dati ice Connessione Chat in Microsoft 365.

![Flusso di lavoro di archiviazione Connessione dati di Chat ice da 17a a 4](../media/ICEChatDataParserConnectorWorkflow.png)

1. L'organizzazione collabora con 17a-4 per configurare Ice DataParser.

2. A intervalli regolari, ICE Connessione gli elementi di Chat vengono raccolti da DataParser. DataParser converte anche il contenuto di un messaggio in un formato di messaggio di posta elettronica.

3. Il connettore ICE DataParser creato nel Centro conformità Microsoft 365 si connette a DataParser e trasferisce i messaggi in una posizione Archiviazione di Azure sicura nel cloud Microsoft.

4. Nelle cassette postali degli utenti viene creata una sottocartella nella cartella Posta in arrivo denominata **ICE DataParser** e gli elementi ice Connessione Chat vengono importati in tale cartella. Il connettore determina in quale cassetta postale importare gli elementi utilizzando il valore della *proprietà Email.* Ogni elemento ICE Connessione Chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Creare un account DataParser per i connettori Microsoft. A tale scopo, contattare [17a-4 LLC](https://www.17a-4.com/contact/). È necessario accedere a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore ICE DataParser nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-an-ice-dataparser-connector"></a>Passaggio 1: Configurare un connettore ICE DataParser

Il primo passaggio consiste nell'accedere alla pagina Connettori dati nel Centro conformità Microsoft 365 e creare un connettore 17a-4 per i dati ice Connessione Chat.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati** ICE  >  **DataParser**.

2. Nella pagina **Descrizione prodotto ICE DataParser** fare clic su **Aggiungi connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedi al tuo account 17a-4 e completa i passaggi della connessione guidata ICE DataParser.

## <a name="step-2-configure-the-ice-dataparser-connector"></a>Passaggio 2: Configurare il connettore ICE DataParser

Utilizzare il supporto 17a-4 per configurare il connettore ICE DataParser.

## <a name="step-3-map-users"></a>Passaggio 3: mappare gli utenti

Il connettore ICE DataParser mappa automaticamente gli utenti ai propri Microsoft 365 di posta elettronica prima di importare i dati in Microsoft 365.

## <a name="step-4-monitor-the-ice-dataparser-connector"></a>Passaggio 4: Monitorare il connettore ICE DataParser

Dopo aver creato un connettore ICE DataParser, è possibile visualizzare lo stato del connettore nella Centro conformità Microsoft 365.

1. Vai a <https://compliance.microsoft.com> e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il connettore ICE DataParser creato per visualizzare la pagina a comparsa, contenente le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
