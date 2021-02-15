---
title: Configurare un connettore per archiviare i dati di LinkedIn
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Informazioni su come gli amministratori possono & usare un connettore nativo per importare dati da una pagina della società LinkedIn a Microsoft 365.
ms.openlocfilehash: 9f6cb2c6d5c47559f1fda13b6d03bfed3afe6fa2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790180"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurare un connettore per archiviare i dati di LinkedIn

Usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine di LinkedIn Company. Dopo aver configurato e configurato un connettore, si connette all'account per la pagina specifica di LinkedIn Company una volta ogni 24 ore. Il connettore converte i messaggi inseriti nella pagina Società in un messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo aver archiviato i dati della pagina LinkedIn Company in una cassetta postale, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto, archiviazione In-Place, controllo e criteri di conservazione di Microsoft 365 ai dati linkedIn. Ad esempio, è possibile cercare questi elementi utilizzando Ricerca contenuto o associare la cassetta postale di archiviazione a un responsabile in un caso di Advanced eDiscovery. La creazione di un connettore per importare e archiviare i dati di LinkedIn in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- All'utente che crea un connettore Pagina società LinkedIn deve essere assegnato il ruolo importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori** dati nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

- È necessario disporre delle credenziali di accesso (indirizzo di posta elettronica, numero di telefono e password) di un account utente LinkedIn che è un amministratore della pagina della società LinkedIn che si desidera archiviare. Queste credenziali vengono utilizzate per accedere a LinkedIn durante la configurazione del connettore.

- Il connettore LinkedIn può importare un totale di 200.000 elementi in un singolo giorno. Se sono presenti più di 200.000 elementi LinkedIn in un giorno, nessuno di questi elementi verrà importato in Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Creare un connettore LinkedIn

1. Accedere alle <https://compliance.microsoft.com> pagine di LinkedIn Company **dei connettori** di dati e quindi  >  **fare clic su**.

2. Nella pagina **del prodotto Pagine aziendali di LinkedIn** fare clic su Aggiungi **connettore.**

3. Nella pagina **Condizioni per il servizio** selezionare **Accetta.**

4. Nella pagina **Accedi con LinkedIn** fare clic **su Accedi con LinkedIn.**

   Viene visualizzata la pagina di accesso di LinkedIn.

   ![Pagina di accesso di LinkedIn](../media/LinkedInSigninPage.png)

5. Nella pagina di accesso di LinkedIn immettere l'indirizzo di posta elettronica (o il numero di telefono) e la password per l'account LinkedIn associato alla pagina della società che si desidera archiviare, quindi fare clic su **Accedi.**

   Viene visualizzata una pagina della procedura guidata con un elenco di tutte le pagine della società LinkedIn associate all'account a cui è stato eseguito l'accesso. Un connettore può essere configurato solo per una pagina aziendale. Se l'organizzazione dispone di più pagine della società LinkedIn, è necessario creare un connettore per ognuna di queste.

   ![Viene visualizzata una pagina con un elenco delle pagine della società LinkedIn](../media/LinkedInSelectCompanyPage.png)

6. Selezionare la pagina della società da cui si desidera archiviare gli elementi e quindi fare clic su **Avanti.**

7. Nella pagina **Scegli** percorso di archiviazione fare clic nella casella, selezionare l'indirizzo di posta elettronica di una cassetta postale di Microsoft 365 in cui verranno importati gli elementi di LinkedIn e quindi fare clic su **Avanti.** Gli elementi vengono importati nella cartella Posta in arrivo in questa cassetta postale.

8. Fare **clic su** Avanti per esaminare le impostazioni del connettore, quindi fare clic su **Fine** per completare la configurazione del connettore.

Dopo aver creato il connettore,  è possibile tornare alla pagina Connettori dati per visualizzare  lo stato del processo di importazione per il nuovo connettore (selezionare Aggiorna se necessario per aggiornare l'elenco dei connettori). Il valore nella colonna **Stato** è In **attesa di iniziare.** L'avvio del processo di importazione iniziale richiede fino a 24 ore. Dopo la prima esecuzione del connettore e l'importazione degli elementi LinkedIn, il connettore verrà eseguito una volta ogni 24 ore e importerà eventuali nuovi elementi creati nella pagina della società LinkedIn nelle 24 ore precedenti.

Per visualizzare ulteriori dettagli, selezionare il connettore nell'elenco nella pagina **Connettori** dati per visualizzare la pagina del riquadro a comparsa. In **Stato**, l'intervallo di date visualizzato indica il filtro di validità selezionato al momento della creazione del connettore.

## <a name="more-information"></a>Altre informazioni

Gli elementi di LinkedIn vengono importati nella sottocartella LinkedIn nella posta in arrivo della cassetta postale di archiviazione in Microsoft 365. Vengono visualizzati come messaggi di posta elettronica.
