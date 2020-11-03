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
ms.openlocfilehash: 0817e6441540086bf679c6533b1bad2e4087b4b9
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841458"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Abilitare l'analisi dell'utilizzo di Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365 Usage Analytics non è ancora disponibile per la community di Microsoft 365 US Government.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365

Per iniziare a utilizzare l'analisi di utilizzo di Microsoft 365, è necessario prima di tutto rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365 e quindi avviare l'app modello in Power BI.
  
### <a name="get-power-bi"></a>Ottenere Power BI

Se non si dispone già di Power BI, è possibile [iscriversi a Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleziona **prova gratis** per iscriversi a una versione di valutazione o **Acquista ora** per ottenere Power bi Pro.
  
  
È anche possibile espandere **Prodotti** per acquistare una versione di Power BI. 

> [!NOTE]
> È necessaria una licenza Power BI Pro per l'installazione, la personalizzazione e la distribuzione di un'app modello. Per ulteriori informazioni, vedere [prerequisiti](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Per condividere i dati, sia lei che le persone con cui si condividono i dati, è necessaria una licenza Power BI Pro o il contenuto deve trovarsi in un'area di lavoro in un [servizio Power bi Premium](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Abilitazione dell'app modello

Per abilitare l'app modello, è necessario eseguire una delle operazioni seguenti: 
- **Amministratore globale**
- **Lettore di report**
- **Amministratore di Exchange**
- **Amministratore di Skype for business**
- **Amministratore di SharePoint** 
  
Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) . 
  
1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
    
2. Nella pagina **utilizzo** individuare la scheda **Microsoft 365 Usage Analytics** e quindi fare clic su **Avvia** .
    
3. Nel riquadro rapporti che si apre, impostare **rendere disponibili i dati di Microsoft 365 Usage Analytics for Power bi** to **on** \> **Save** . 
  
Il processo di raccolta dei dati verrà completato in due o 48 ore, a seconda delle dimensioni del tenant. Il pulsante **Vai a Power bi** verrà abilitato (non più grigio) quando la raccolta dati è stata completata. 
    
### <a name="start-the-template-app"></a>Avviare l'app modello

Per avviare l'app modello, è necessario essere un **amministratore globale** , un **lettore di report** , un **amministratore di Exchange** , un amministratore **di Skype for business** o un **amministratore di SharePoint** . 
  
1. Copiare l'ID tenant e selezionare **Vai a Power bi** .
    
2.  Dopo aver scaricato Power BI, eseguire l'accesso. Quindi **Seleziona app** -> per **ottenere app** dal menu di spostamento.    
  
3. Nella scheda **app** Digitare Microsoft 365 nella casella di ricerca e quindi selezionare **Analisi utilizzo Microsoft 365** \> **ottenerlo subito** .

    [![Seleziona Ottieni subito](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Dopo l'installazione dell'app. Selezionare il riquadro per aprirlo.

5.  Selezionare **Esplora app** per visualizzare l'app con dati di esempio. Scegliere **Connect** per connettere l'app ai dati dell'organizzazione.

6.  Scegliere **Connect** , nella schermata **connetti a Microsoft 365 Usage Analytics** , quindi digitare l'ID tenant (senza trattini) copiato nel passaggio (1), quindi selezionare **Avanti** .
    
7. Nella schermata successiva, selezionare **OAuth2** come accesso al **Metodo** \> **di** autenticazione. Se si sceglie qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.
    
    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Dopo aver creato un'istanza dell'app modello, il Dashboard Microsoft 365 Usage Analytics sarà disponibile in Power BI sul Web. Il caricamento iniziale del dashboard richiederà da 2 a 30 minuti.
  
Le aggregazioni a livello di tenant saranno disponibili in tutti i report. I **dettagli a livello di utente diventeranno disponibili solo dopo il 1 ° o 15 ° giorno del mese di calendario dopo l'opt-in** . Ciò avrà un impatto su tutti i report in attività utente. Per suggerimenti su come visualizzare e utilizzare i report, vedere [esplorazione e utilizzo dei report in Microsoft 365 Usage Analytics](navigate-and-utilize-reports.md) .
    
## <a name="make-the-collected-data-anonymous"></a>Rendere anonimi i dati raccolti

Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale. In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, nei report e nell'app modello.
  
1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni** \> **organizzazione** e quindi in scheda **Servizi** scegliere **report** .
    
2. Selezionare **report** , quindi scegliere di **visualizzare gli identificatori anonimi** . Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.
  
3. Selezionare **Salva modifiche** .
