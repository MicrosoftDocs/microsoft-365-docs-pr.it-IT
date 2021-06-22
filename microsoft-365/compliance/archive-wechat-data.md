---
title: Configurare un connettore per archiviare i dati di WeChat in Microsoft 365
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
description: Configurare e usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati di WeChat in Microsoft 365.
ms.openlocfilehash: e610b58421c2d84402010c9a5d5ad33ec6da5b04
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054612"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>Configurare un connettore per archiviare i dati di WeChat

Usa il connettore TeleMessage nel Centro conformità Microsoft 365 per importare e archiviare le chiamate, le chat, gli allegati, i file e i messaggi richiamati di WeChat e WeCom. Dopo aver configurato e configurato un connettore, il connettore si connette all'account TeleMessage dell'organizzazione e importa la comunicazione mobile dei dipendenti tramite l'archivio WeChat Di TeleMessage nelle cassette postali in Microsoft 365.

Dopo aver archiviato i dati del connettore WeChat Archiver nelle cassette postali degli utenti, è possibile applicare ai dati di comunicazione WeChat le funzionalità di conformità di Microsoft 365 quali conservazione per controversia legale, eDiscovery, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione Microsoft 365. Ad esempio, è possibile cercare le comunicazioni WeChat utilizzando Ricerca contenuto o associare la cassetta postale che contiene i dati del connettore WeChat Archiver a un responsabile in un Advanced eDiscovery caso. L'utilizzo di un connettore WeChat Archiver per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme alle normative e ai criteri normativi di governance aziendale.

## <a name="overview-of-archiving-wechat-communication-data"></a>Panoramica dell'archiviazione dei dati di comunicazione WeChat

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati delle comunicazioni WeChat in Microsoft 365.

![Flusso di lavoro di archiviazione per i dati di WeChat Archiver](../media/WeChatConnectorWorkflow.png)

1. L'organizzazione collabora con TeleMessage per configurare un connettore WeChat Archiver.

2. In tempo reale, i dati WeChat dell'organizzazione vengono copiati nel sito TeleMessage.

3. Il connettore WeChat Archiver creato nel Centro conformità Microsoft 365 si connette al sito TeleMessage ogni giorno e trasferisce i messaggi di posta elettronica dalle 24 ore precedenti a un'area Archiviazione di Azure sicura nel cloud Microsoft.

4. Il connettore importa gli elementi di comunicazione mobile nella cassetta postale di un utente specifico. Verrà creata una nuova cartella denominata WeChat Archiver nella cassetta postale dell'utente specifico e gli elementi verranno importati in essa. Il connettore esegue il mapping utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente.* Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica. Oltre al mapping automatico degli utenti utilizzando il valore della proprietà Indirizzo di posta elettronica *dell'utente,* è anche possibile definire un mapping personalizzato caricando un file di mapping CSV. Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo Microsoft 365 corrispondente per ogni utente. Se si abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore guarderà innanzitutto il file di mapping personalizzato. Se non trova un utente Microsoft 365 valido corrispondente al numero di cellulare di un utente, il connettore utilizzerà la proprietà Dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica. Se il connettore non trova un utente Microsoft 365 valido nel file di mapping personalizzato o nella proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica, *l'elemento* non verrà importato.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Utilizzare TeleMessage per configurare un connettore di archiviazione WeChat. Per ulteriori informazioni, vedere [Activating the TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).

- Configurare un connettore TeleMessage per Microsoft 365 e ottenere un account di amministrazione aziendale valido. Per ulteriori informazioni, vedere [Order Microsoft 365 Mobile Archiving.](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)

- Registrare tutti gli utenti che richiedono l'archiviazione WeChat nell'account TeleMessage con lo stesso indirizzo di posta elettronica utilizzato per l'account Microsoft 365'utente.

- Dovrai installare l'app Tencent WeCom sui telefoni cellulari degli utenti dell'organizzazione e attivarla. L'app WeCom consente agli utenti di comunicare e chattare con altri utenti di WeChat e WeCom.

- All'utente che crea un connettore WeChat Archiver nel Centro conformità Microsoft 365 deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- Questo connettore dati è disponibile in GCC nel cloud Microsoft 365 us government. Le applicazioni e i servizi di terze parti possono comportare l'archiviazione, la trasmissione e l'elaborazione dei dati dei clienti dell'organizzazione in sistemi di terze parti esterni all'infrastruttura di Microsoft 365 e pertanto non coperti dagli impegni di conformità e protezione dei dati di Microsoft 365. Microsoft non fa alcuna rappresentazione che utilizzi questo prodotto per connettersi ad applicazioni di terze parti implica che tali applicazioni di terze parti siano conformi a FEDRAMP.

## <a name="create-a-wechat-archiver-connector"></a>Creare un connettore WeChat Archiver

Seguire i passaggi descritti in questa sezione per creare un connettore WeChat Archiver nella Centro conformità Microsoft 365. Il connettore utilizza le informazioni fornite per connettersi al sito TeleMessage e trasferire i dati delle comunicazioni WeChat alle cassette postali degli utenti corrispondenti in Microsoft 365.

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **WeChat Archiver**.

2. Nella pagina **Descrizione prodotto WeChat Archiver,** fare clic su **Aggiungi connettore**

3. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

4. Nella pagina **Accesso a TeleMessage,** in Passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti.**

    - **Nome utente**: nome utente TeleMessage.

    - **Password**: la password di TeleMessage.

5. Dopo aver creato il connettore, è possibile chiudere la finestra popup per passare alla pagina successiva.

6. Nella pagina **Mapping utenti** abilitare il mapping automatico degli utenti. Puoi anche caricare un file CSV di mapping utente personalizzato.

7. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

8. Passare alla scheda **Connettori** nella **pagina Connettori dati** per visualizzare l'avanzamento del processo di importazione per il nuovo connettore.

## <a name="known-issues"></a>Problemi noti

- Al momento non è possibile importare allegati o elementi di dimensioni superiori a 10 MB. Il supporto per gli elementi più grandi sarà disponibile in un secondo momento.
