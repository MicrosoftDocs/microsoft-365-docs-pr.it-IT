---
title: Configurare un connettore per archiviare i dati di LinkedIn in Office 365 (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore nativo per importare i dati da una pagina società di LinkedIn a Office 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per poter utilizzare le funzionalità di conformità, ad esempio i criteri di conservazione legale, ricerca contenuto e mantenimento, per gestire la conformità dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: bd11102a15396132cb192d8b0a4cc9a0dfca5645
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615626"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>Configurare un connettore per archiviare i dati di LinkedIn in Office 365 (anteprima)

La funzionalità del connettore per l'archiviazione dei dati da LinkedIn Company Pages in Office 365 è in anteprima.

Utilizzare un connettore nativo nel centro sicurezza & compliance in Office 365 per importare e archiviare i dati dalle pagine dell'azienda LinkedIn. Dopo aver configurato e configurato un connettore, l'utente si connette all'account della pagina della società specifica di LinkedIn una volta ogni 24 ore. Il connettore converte i messaggi inviati alla pagina della società in un messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Office 365.

Dopo che i dati della pagina della società LinkedIn sono archiviati in una cassetta postale, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Office 365 ai dati di LinkedIn. Ad esempio, è possibile cercare questi elementi utilizzando la ricerca contenuto o associare la cassetta postale di archiviazione a un custode in un caso di eDiscovery avanzato. La creazione di un connettore per l'importazione e l'archiviazione dei dati di LinkedIn in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="before-you--begin"></a>Prima di iniziare

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta.

- All'utente che crea un connettore di pagina di LinkedIn Company deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questo ruolo è necessario per accedere alla pagina di **archiviazione dei dati di terze parti** nel centro sicurezza & conformità. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

- È necessario disporre delle credenziali di accesso (indirizzo di posta elettronica o numero di telefono e password) di un account utente di LinkedIn che è un amministratore della pagina della società LinkedIn che si desidera archiviare. Queste credenziali vengono utilizzate per accedere a LinkedIn quando si configura il connettore.

## <a name="create-a-linkedin-connector"></a>Creare un connettore LinkedIn

1. Andare a <https://protection.office.com> e selezionare **Importa data governance \> ** , quindi selezionare **archivia dati di terze parti**.

2. Nella pagina **archivio dati di terze parti** selezionare **Aggiungi un connettore**e quindi fare clic su **LinkedIn**.

3. Nella pagina **condizioni del servizio** selezionare **accetta**.

4. Nella pagina **Accedi con LinkedIn** , seleziona **Accedi con LinkedIn**.

   Viene visualizzata la pagina di accesso di LinkedIn.

   ![Pagina di accesso di LinkedIn](media/LinkedInSigninPage.png)

5. Nella pagina di accesso a LinkedIn, immettere l'indirizzo di posta elettronica (o il numero di telefono) e la password per l'account LinkedIn associato alla pagina società che si desidera archiviare e quindi selezionare **Accedi**.

   Viene visualizzata una pagina della procedura guidata con un elenco di tutte le pagine società di LinkedIn associate all'account a cui è stato effettuato l'accesso. È possibile configurare un connettore solo per una pagina dell'azienda. Se nell'organizzazione sono presenti più pagine dell'azienda LinkedIn, è necessario creare un connettore per ognuno di essi.

   ![Viene visualizzata una pagina con un elenco delle pagine dell'azienda LinkedIn](media/LinkedInSelectCompanyPage.png)

6. Selezionare la pagina società da cui si desidera archiviare gli elementi e quindi fare clic su **Avanti**.

7. Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età. Selezionare un'età e quindi fare clic su **Avanti**.

8. Nella pagina **Imposta account di archiviazione** Digitare l'indirizzo di posta elettronica di una cassetta postale di Office 365 in cui verranno importati gli elementi di LinkedIn e quindi selezionare **Avanti**. Gli elementi vengono importati nella cartella posta in arrivo in questa cassetta postale.

9. Esaminare le impostazioni del connettore e quindi fare clic su **Salva** per completare la configurazione del connettore.

Dopo aver creato il connettore, è possibile tornare alla pagina di **archiviazione dei dati di terze parti** (selezionare **Aggiorna** , se necessario, per aggiornare l'elenco dei connettori) a visualizzare il nuovo connettore. Il valore nella colonna **stato** è in **attesa di inizio**. L'avvio del processo di importazione iniziale richiede fino a 24 ore. Dopo la prima esecuzione del connettore e le importazioni degli elementi di LinkedIn, il connettore verrà eseguito una volta ogni 24 ore e importerà eventuali nuovi elementi creati nella pagina società di LinkedIn nelle 24 ore precedenti.

Per visualizzare ulteriori dettagli, selezionare il connettore nell'elenco nella pagina **archivia dati di terze parti** per visualizzarne la pagina. In **stato**, l'intervallo di date visualizzato indica il filtro di età che è stato selezionato quando è stato creato il connettore. 

## <a name="more-information"></a>Ulteriori informazioni

- Gli elementi di LinkedIn vengono importati nella cartella posta in arrivo nella cassetta postale di archiviazione in Office 365. Vengono visualizzati come messaggi di posta elettronica. Il nome visualizzato del mittente del messaggio è il nome della pagina della società LinkedIn. L'indirizzo di posta elettronica effettivo del mittente è l'indirizzo di posta elettronica della cassetta postale di archiviazione. Il nome della pagina società è inoltre preaccodato alla riga dell'oggetto. 

- A causa del comportamento precedente, è possibile cercare le `from` proprietà `subject` o la posta elettronica quando si utilizza uno strumento di Microsoft eDiscovery per cercare gli elementi di LinkedIn archiviati in Office 365. Ad esempio, se il nome della pagina società è "Contoso Company page", è possibile utilizzare una delle coppie *proprietà: valore* seguenti nella query di ricerca con parole chiave:
   
   > from: "Contoso Company page"

    Oppure

   > oggetto: "pagina azienda Contoso"

- Per semplificare l'individuazione o la gestione degli elementi di LinkedIn importati in Office 365, il proprietario della cassetta postale di archiviazione (o tutti gli utenti che hanno assegnato l'autorizzazione FullAccess) può impostare una regola di posta in arrivo per spostare gli elementi da una pagina società di LinkedIn a una cartella specifica. Questa operazione è utile se la cassetta postale di archiviazione viene utilizzata per archiviare gli elementi importati da origini dati di terze parti diverse. Ad esempio, è possibile creare una regola di posta in arrivo che sposta tutti gli elementi che contengono il nome di una specifica pagina di LinkedIn società nel campo oggetto in una cartella specifica.