---
title: Abilitare l'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Informazioni su come avviare la raccolta dei dati per il tenant utilizzando l'app modello di analisi di utilizzo di Microsoft 365 in Power BI.
ms.openlocfilehash: fa0973521f5a5e7e8b9b0fda161a5b4779d64c68
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401507"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Abilitare l'analisi dell'utilizzo di Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365 Usage Analytics è disponibile anche per la community di Microsoft 365 US Government.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365

Per iniziare a utilizzare l'analisi di utilizzo di Microsoft 365, è necessario prima di tutto rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365 e quindi avviare l'app modello in Power BI.
  
### <a name="get-power-bi"></a>Ottenere Power BI

Se non si dispone già di Power BI, è possibile [iscriversi a Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleziona **prova gratis** per iscriversi a una versione di valutazione o **Acquista ora** per ottenere Power bi Pro.
  
  
È anche possibile espandere **Prodotti** per acquistare una versione di Power BI. 

> [!NOTE]
> È necessaria una licenza Power BI Pro per l'installazione, la personalizzazione e la distribuzione di un'app modello. Per ulteriori informazioni, vedere [prerequisiti](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

È necessaria una licenza Power BI Pro per condividere il contenuto e le persone con cui condividerlo o il contenuto deve trovarsi in un'area di lavoro con una [capacità Premium](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Abilitazione dell'app modello

Per abilitare l'app modello, è necessario essere un **amministratore globale**, un **lettore di report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**. 
  
Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) . 
  
1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
    
2. Nella pagina **utilizzo** individuare la scheda **Microsoft 365 Usage Analytics** e quindi fare clic su **Avvia**.
    
3. Nel riquadro rapporti che si apre, impostare **rendere disponibili i dati di Microsoft 365 Usage Analytics for Power bi** to **on** \> **Save**. 
  
In questo modo viene avviato il processo di raccolta dei dati e il completamento verrà eseguito tra 2 e 48 ore, a seconda delle dimensioni del tenant. Il pulsante **Vai a Power bi** verrà abilitato (non più grigio) quando la raccolta dati è stata completata. 
    
### <a name="initiate-the-template-app"></a>Avviare l'app modello

Per avviare l'app modello, è necessario essere un **amministratore globale**, un lettore di **report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**. 
  
1. Copiare l'ID tenant e selezionare **Vai a Power bi**.
    
2.  Dopo aver scaricato Power BI, eseguire l'accesso. Seleziona app->Ottieni app dal menu di spostamento.    
  
3. Nella scheda **app** Digitare Microsoft 365 nella casella di ricerca e quindi selezionare **Analisi utilizzo Microsoft 365** \> **ottenerlo subito**.

    [![Seleziona Ottieni subito](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Dopo l'installazione dell'app. Fare clic sul riquadro per aprirlo.

5.  Fare clic su **Esplora app** per visualizzare l'app con dati di esempio. Fare clic su **Connetti** per connettere l'app ai dati dell'organizzazione.

6.  Dopo aver fatto clic su **Connetti**, nella schermata **connetti a Microsoft 365 Usage Analytics** digitare l'ID tenant (senza trattini) copiato nel passaggio (1) e quindi selezionare **Avanti**.
    
7. Nella schermata successiva, selezionare **OAuth2** come accesso al **Metodo** \> **di**autenticazione. Se si sceglie qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. Dopo aver creato un'istanza dell'app modello, il Dashboard Microsoft 365 Usage Analytics sarà disponibile in Power BI sul Web. Il caricamento iniziale del dashboard richiederà da 2 a 30 minuti.
  
Le aggregazioni a livello di tenant saranno disponibili in tutti i report. I **dettagli a livello di utente diventeranno disponibili solo dopo il 1 ° o 15 ° giorno del mese di calendario dopo l'opt-in**. Questo influirà su tutti i report in attività utente (vedere [navigare e utilizzare i report di analisi di utilizzo di Microsoft 365](navigate-and-utilize-reports.md) per suggerimenti su come visualizzare e utilizzare questi report).
    
## <a name="make-the-collected-data-anonymous"></a>Rendere anonimi i dati raccolti

Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale. In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, nei report e nell'app modello.
  
1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni** \> **organizzazione**e quindi in scheda **Servizi** scegliere **report**.
    
2. Selezionare **report**, quindi scegliere di **visualizzare gli identificatori anonimi**. Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.
  
3. Selezionare **Salva modifiche**.
