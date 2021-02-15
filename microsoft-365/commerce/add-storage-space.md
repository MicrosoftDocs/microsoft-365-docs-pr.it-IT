---
title: Aggiungere spazio di archiviazione per l'abbonamento
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni su come aggiungere e ridurre l'archiviazione dei file nell'abbonamento a Microsoft 365. Con spazio di archiviazione file aggiuntivo, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114908"
---
# <a name="add-storage-space-for-your-subscription"></a>Aggiungere spazio di archiviazione per l'abbonamento

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo. Se office **365 Extra File Storage** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo. Per altre informazioni, vedere [Il piano è idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> Se l'abbonamento è stato acquistato tramite contratti multilicenza o un provider di servizi di configurazione, non è possibile acquistare **Office 365 Extra File Storage** per l'organizzazione direttamente da Microsoft. Contattare il proprio rappresentante o partner per assistenza.

## <a name="before-you-begin"></a>Informazioni preliminari

Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o di SharePoint. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).

## <a name="view-available-storage"></a>Visualizzare lo spazio di archiviazione disponibile

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione di SharePoint passare alla pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Siti</a> attivi e accedere con un account che dispone delle autorizzazioni di amministratore [per](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) l'organizzazione.

2. Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento. Se l'organizzazione ha configurato Multi-Geo in Office 365, la barra mostra anche la quantità di spazio di archiviazione usato in tutte le posizioni geografiche.

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.

::: moniker-end

::: moniker range="o365-germany"

1. Accedere come amministratore globale o di SharePoint e quindi selezionare il riquadro https://portal.office.de Amministrazione per aprire l'interfaccia di amministrazione. Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore di Microsoft 365 nell'organizzazione.

2. Nel riquadro sinistro, in **Interfaccia di amministrazione,** selezionare **SharePoint.** Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.

3. Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.

4. Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.

::: moniker-end

::: moniker range="o365-21vianet"

1. Accedere come amministratore globale o di SharePoint e quindi selezionare il riquadro https://login.partner.microsoftonline.cn/ Amministrazione per aprire l'interfaccia di amministrazione. Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore di Microsoft 365 nell'organizzazione.

2. Nel riquadro sinistro, in **Interfaccia di amministrazione,** selezionare **SharePoint.** Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.

3. Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.

4. Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.  

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.

::: moniker-end

Dopo aver identificato la quantità di spazio di archiviazione in uso, è possibile aggiungerne altro o rimuoverlo dall'abbonamento. Per scoprire quanto costerà aggiungere spazio di archiviazione, segui i passaggi descritti in questo articolo ed esamina le informazioni sui prezzi prima dell'acquisto.
  
Per informazioni sull'impostazione dei limiti di archiviazione per le raccolte siti, vedere [Gestire i limiti di archiviazione delle raccolte siti.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)
  
## <a name="add-storage-to-your-subscription"></a>Aggiungere spazio di archiviazione all'abbonamento

Se non è stato ancora acquistato spazio di archiviazione aggiuntivo per l'abbonamento, è possibile farlo.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Servizi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">di acquisto della</a> fatturazione.
2. Nella parte inferiore della **pagina Acquisto di** servizi selezionare Componenti **aggiuntivi.**
3. Selezionare Spazio di archiviazione file aggiuntivo di **Office 365.**
4. Nella pagina Spazio di archiviazione file aggiuntivo di **Office 365,** se visualizzata, scegliere l'abbonamento di base, quindi immettere il numero di gigabyte di archiviazione che si desidera aggiungere.
5. Selezionare **Estrai ora.**
6. Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**
7. Nella pagina **Completa ordine** verificare il totale. Se è necessario apportare modifiche, selezionare **Modifica ordine.** Se l'ordine richiede una verifica del credito, selezionare la casella di controllo. Al termine, selezionare Place **order** \> **Go to Admin Home.**

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Sottoscrizioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">fatturazione.</a>  

2. Nella pagina **Sottoscrizioni** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **Componenti aggiuntivi.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Se i componenti aggiuntivi non sono visualizzati e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC).**
  
3. Seleziona **Acquista componenti aggiuntivi.**

    ![Collegamento Acquista componenti aggiuntivi nella pagina Abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. Nella pagina **Acquisto di servizi,** posizionare il puntatore del mouse o toccare Archiviazione file extra di **Office 365,** quindi selezionare **Acquista ora.**
  
5. Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere un abbonamento di base. Selezionare **Estrai ora.**
  
6. Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**

7. Nella pagina **Completa ordine** selezionare **Effettuare l'ordine.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.

2. Nella pagina **Sottoscrizioni** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **Componenti aggiuntivi.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Se i componenti aggiuntivi non sono visualizzati e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC).**
  
3. Seleziona **Acquista componenti aggiuntivi.**

    ![Collegamento Acquista componenti aggiuntivi nella pagina Abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. Nella pagina **Acquisto di servizi,** posizionare il puntatore del mouse o toccare Archiviazione file extra di **Office 365,** quindi selezionare **Acquista ora.**
  
5. Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere un abbonamento di base. Selezionare **Estrai ora.**
  
6. Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**

7. Nella pagina **Completa ordine** selezionare **Effettuare l'ordine.**

::: moniker-end

## <a name="increase-or-decrease-storage"></a>Aumentare o diminuire lo spazio di archiviazione

Se è già stato acquistato spazio di archiviazione file aggiuntivo tramite il componente aggiuntivo Office **365 Extra File Storage,** è possibile usare questa procedura per aumentare o ridurre lo spazio di archiviazione aggiuntivo per l'abbonamento. È possibile ridurre lo spazio di archiviazione fino a 1 gigabyte. Per rimuovere tutto lo spazio di archiviazione aggiuntivo, [contattare il supporto](../admin/contact-support-for-business-products.md)tecnico.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'abbonamento contenente il componente aggiuntivo Di archiviazione file aggiuntivo di **Office 365.**
3. Nella sezione Componenti aggiuntivi  della pagina dei dettagli del prodotto selezionare **Gestisci componenti aggiuntivi.**
4. **Nell'elenco Componenti** aggiuntivi del riquadro  Gestisci componenti aggiuntivi scegliere Spazio di archiviazione file aggiuntivo di **Office 365.**
5. Nella casella **di** testo Quantità immettere il numero di GB di spazio di archiviazione desiderato per la sottoscrizione.
6. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.

2. Nella pagina **Abbonamenti** selezionare **Componenti aggiuntivi.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Se i componenti aggiuntivi non sono visualizzati e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC).**
  
3. In Spazio di archiviazione file aggiuntivo di **Office 365** selezionare **Cambia quantità.**

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. Nel riquadro destro immettere il numero totale di gigabyte necessari, quindi selezionare **Invia.**

    Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.

5. Selezionare **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.

2. Nella pagina **Abbonamenti** selezionare **Componenti aggiuntivi.**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > Se i componenti aggiuntivi non sono visualizzati e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC).**
  
3. In Spazio di archiviazione file aggiuntivo di **Office 365** selezionare **Cambia quantità.**

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. Nel riquadro destro immettere il numero totale di gigabyte necessari, quindi selezionare **Invia.**

    Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.

5. Selezionare **Chiudi**.

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>Quali piani sono idonei per Office 365 Extra File Storage?

Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:
  
- Office 365 Enterprise E1

- Office 365 Enterprise E2

- Office 365 Enterprise E3

- Office 365 Enterprise E4

- Office 365 Enterprise E5

- Office per il Web con SharePoint Piano 1

- Office per il Web con SharePoint Piano 2

- SharePoint Online Piano 1

- SharePoint Online Piano 2

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> Office 365 Extra File Storage è disponibile anche per i piani GCC, GCC High e DOD.

## <a name="related-content"></a>Contenuti correlati

[Gestire i limiti di archiviazione del sito](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (articolo)\
[Impostare lo spazio di archiviazione predefinito per gli utenti di OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(articolo)
