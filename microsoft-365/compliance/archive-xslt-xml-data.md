---
title: Configurare un connettore per archiviare i dati XSLT/XML in Microsoft 365
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
description: Gli amministratori possono configurare un connettore per importare e archiviare i dati XSLT/XML da Veritas in Microsoft 365. Questo connettore consente di archiviare i dati da origini dati di terze parti in Microsoft 365, in modo da poter utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163760"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Configurare un connettore per archiviare i dati XSLT/XML

Utilizzare un connettore Veritas nel Centro conformità Microsoft 365 per importare e archiviare i dati dall'origine della pagina Web alle cassette postali degli utenti nell'organizzazione di Microsoft 365. Veritas offre un connettore [XSLT/XML](https://globanet.com/xslt-xml) che consente lo sviluppo rapido di file creati utilizzando XSLT (Extensible Style sheet Language Transformations) per trasformare i file XML in altri formati di file (ad esempio HTML o testo) che possono essere importati in Microsoft 365. Il connettore converte il contenuto di un elemento dall'origine XSLT/XML in un formato di messaggio di posta elettronica e quindi importa l'elemento convertito nelle cassette postali di Microsoft 365.

Dopo aver archiviato i dati XSLT/XML nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, criteri di conservazione ed etichette di conservazione. L'utilizzo di un connettore XSLT/XML per importare e archiviare dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="overview-of-archiving-xsltxml-data"></a>Panoramica dell'archiviazione dei dati XSLT/XML

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di origine XSLT/XML in Microsoft 365.

![Flusso di lavoro di archiviazione per dati XSLT/XML](../media/XSLT-XMLConnectorWorkflow.png)

1. L'organizzazione collabora con l'origine XSLT/XML per configurare un sito XSLT/XML.

2. Una volta ogni 24 ore, i messaggi di chat dall'origine XSLT/XML vengono copiati nel sito Veritas Merge1. Il connettore converte anche il contenuto in un formato di messaggio di posta elettronica.

3. Il connettore XSLT/XML creato nel Centro conformità Microsoft 365 si connette ogni giorno al sito Veritas Merge1 e trasferisce i messaggi in una posizione sicura di Archiviazione di Azure nel cloud Microsoft.

4. Il connettore importa gli elementi dei messaggi convertiti nelle cassette postali di utenti specifici utilizzando il valore della proprietà *Email* del mapping automatico degli utenti, come descritto nel passaggio 3. Nelle cassette postali degli utenti viene creata una nuova sottocartella nella cartella Posta in arrivo denominata **XSLT/XML** e gli elementi del messaggio vengono importati in tale cartella. Il connettore esegue questa operazione utilizzando il valore della *proprietà Email.* Ogni messaggio contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio.

## <a name="before-you-begin"></a>Prima di iniziare

- Creare un account Veritas Merge1 per i connettori Microsoft. Per creare questo account, contattare il [supporto tecnico Veritas.](https://www.veritas.com/content/support/) Si accederà a questo account quando si crea il connettore nel passaggio 1.

- L'utente che crea il connettore XSLT/XML nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-set-up-an-xsltxml-connector"></a>Passaggio 1: Configurare un connettore XSLT/XML

Il primo passaggio consiste  nell'accedere ai connettori dati nel Centro conformità Microsoft 365 e creare un connettore per i dati XSLT/XML.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **Connettori dati**  >  **XSLT/XML.**

2. Nella pagina **Descrizione prodotto XSLT/XML** fare clic **su Aggiungi nuovo connettore.**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.**

5. Accedere all'account Merge1 per configurare il connettore.

## <a name="step-2-configure-an-xsltxml-connector"></a>Passaggio 2: Configurare un connettore XSLT/XML

Il secondo passaggio consiste nel configurare il connettore XSLT/XML nel sito Merge1. Per informazioni su come configurare il connettore XSLT/XML nel sito Veritas Merge1, vedere [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).

Dopo aver fatto **clic su Salva & fine,** viene visualizzata la pagina **Mapping** utenti nella procedura guidata del connettore nel Centro conformità Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

1. Per mappare gli utenti e completare la configurazione del connettore nel Centro conformità Microsoft 365, eseguire la procedura seguente:

2. Nella pagina **Mapping utenti XSLT/XML agli utenti di Microsoft 365** abilitare il mapping automatico degli utenti. Gli elementi XSLT/XML includono una proprietà denominata *Email*, che contiene gli indirizzi di posta elettronica per gli utenti dell'organizzazione. Se il connettore può associare questo indirizzo a un utente di Microsoft 365, gli elementi vengono importati nella cassetta postale dell'utente.

3. Fare **clic** su Avanti, rivedere le impostazioni e passare alla pagina **Connettori** dati per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Passaggio 4: Monitorare il connettore XSLT/XML

Dopo aver creato il connettore XSLT/XML, è possibile visualizzare lo stato del connettore nel Centro conformità Microsoft 365.

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Fare clic **sulla scheda Connettori** e quindi selezionare il **connettore XSLT/XML** per visualizzare la pagina a comparsa. Questa pagina contiene le proprietà e le informazioni sul connettore.

3. In **Stato connettore con origine** fare clic sul collegamento Scarica **registro** per aprire (o salvare) il registro di stato per il connettore. Questo registro contiene i dati importati nel cloud Microsoft.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.