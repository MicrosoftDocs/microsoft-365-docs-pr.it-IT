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
description: Informazioni su come gli amministratori possono & utilizzare un connettore nativo per importare dati da una pagina aziendale linkedin a Microsoft 365.
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906146"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurare un connettore per archiviare i dati di LinkedIn

Utilizzare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine di LinkedIn Company. Dopo aver configurato e configurato un connettore, si connette all'account per la pagina specifica di LinkedIn Company una volta ogni 24 ore. Il connettore converte i messaggi inseriti nella pagina Società in un messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo aver archiviato i dati della pagina LinkedIn Company in una cassetta postale, è possibile applicare ai dati di LinkedIn le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione In-Place, controllo e criteri di conservazione di Microsoft 365. Ad esempio, è possibile cercare questi elementi utilizzando Ricerca contenuto o associare la cassetta postale di archiviazione a un responsabile in un caso advanced eDiscovery. La creazione di un connettore per importare e archiviare i dati di LinkedIn in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- All'utente che crea un connettore LinkedIn Company Page deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Questa operazione è necessaria per aggiungere connettori nella pagina **Connettori dati** nel Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

- È necessario disporre delle credenziali di accesso (indirizzo di posta elettronica, numero di telefono e password) di un account utente LinkedIn che sia un amministratore della pagina aziendale di LinkedIn che si desidera archiviare. Queste credenziali vengono utilizzate per accedere a LinkedIn durante la configurazione del connettore.

- Il connettore LinkedIn può importare un totale di 200.000 elementi in un solo giorno. Se sono presenti più di 200.000 elementi LinkedIn in un giorno, nessuno di questi elementi verrà importato in Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Creare un connettore LinkedIn

1. Passare a <https://compliance.microsoft.com> e quindi fare clic su **Connettori dati**  >  **LinkedIn Pagine società**.

2. Nella pagina **del prodotto Pagine società LinkedIn** fare clic su Aggiungi **connettore.**

3. Nella pagina **Condizioni per il servizio** selezionare **Accetta**.

4. Nella pagina **Accedi con LinkedIn** fare clic **su Accedi con LinkedIn.**

   Viene visualizzata la pagina di accesso di LinkedIn.

   ![Pagina di accesso LinkedIn](../media/LinkedInSigninPage.png)

5. Nella pagina di accesso di LinkedIn immettere l'indirizzo di posta elettronica (o il numero di telefono) e la password per l'account LinkedIn associato alla pagina aziendale che si desidera archiviare e quindi fare clic su **Accedi**.

   Viene visualizzata una pagina della procedura guidata con un elenco di tutte le pagine società LinkedIn associate all'account a cui è stato eseguito l'accesso. Un connettore può essere configurato solo per una pagina aziendale. Se l'organizzazione dispone di più pagine società LinkedIn, è necessario creare un connettore per ognuna di queste.

   ![Viene visualizzata una pagina con un elenco di Pagine società LinkedIn](../media/LinkedInSelectCompanyPage.png)

6. Selezionare la pagina della società da cui si desidera archiviare gli elementi e quindi fare clic su **Avanti.**

7. Nella pagina **Scegli percorso di** archiviazione fare clic nella casella, selezionare l'indirizzo di posta elettronica di una cassetta postale di Microsoft 365 in cui verranno importati gli elementi di LinkedIn e quindi fare clic su **Avanti.** Gli elementi vengono importati nella cartella Posta in arrivo in questa cassetta postale.

8. Fare **clic su** Avanti per esaminare le impostazioni del connettore e quindi fare clic su **Fine** per completare la configurazione del connettore.

Dopo aver creato il connettore,  è possibile tornare alla pagina Connettori dati per visualizzare  l'avanzamento del processo di importazione per il nuovo connettore (selezionare Aggiorna se necessario per aggiornare l'elenco dei connettori). Il valore nella colonna **Stato** è **In attesa di avvio.** L'avvio del processo di importazione iniziale richiede fino a 24 ore. Dopo la prima esecuzione del connettore e l'importazione degli elementi LinkedIn, il connettore verrà eseguito una volta ogni 24 ore e importerà eventuali nuovi elementi creati nella pagina della società LinkedIn nelle 24 ore precedenti.

Per visualizzare ulteriori dettagli, selezionare il connettore nell'elenco nella pagina **Connettori dati** per visualizzare la pagina a comparsa. In **Stato** l'intervallo di date visualizzato indica il filtro validità selezionato al momento della creazione del connettore.

## <a name="more-information"></a>Ulteriori informazioni

Gli elementi LinkedIn vengono importati nella sottocartella LinkedIn nella posta in arrivo della cassetta postale di archiviazione in Microsoft 365. Vengono visualizzati come messaggi di posta elettronica.