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
description: Informazioni su come iniziare a raccogliere dati per il tenant usando l'app modello Analisi di utilizzo di Microsoft 365 in Power BI.
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913875"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Abilitare l'analisi dell'utilizzo di Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

L'analisi dell'utilizzo di Microsoft 365 non è ancora disponibile per Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365

Per iniziare a usare l'analisi dell'utilizzo di Microsoft 365, è necessario prima rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365, quindi avviare l'app modello in Power BI.
  
### <a name="get-power-bi"></a>Ottenere Power BI

Se non si dispone già di Power BI, è possibile iscriversi [a Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selezionare **Prova gratuitamente** per iscriversi a una versione di valutazione o Acquista **ora** per ottenere Power BI Pro.
  
  
È anche possibile espandere **Prodotti** per acquistare una versione di Power BI. 

> [!NOTE]
> È necessaria una licenza di Power BI Pro per installare, personalizzare e distribuire un'app modello. Per ulteriori informazioni, vedere [Prerequisiti](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Per condividere i dati, sia l'utente che le persone con cui si condividono i dati, è necessaria una licenza di Power BI Pro o il contenuto deve essere in un'area di lavoro in un servizio [Power BI premium.](/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Abilitare l'app modello

Per abilitare l'app modello, devi essere un **amministratore globale.**
  
Per [ulteriori informazioni, vedere](../add-users/about-admin-roles.md) Sui ruoli di amministratore. 
  
1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>. 
    
2. Nella pagina **Utilizzo** individuare la scheda Analisi di **utilizzo di Microsoft 365** e selezionare **Introduzione.**
    
3. Nel riquadro Report visualizzato impostare Rendi i dati disponibili per l'analisi di utilizzo di **Microsoft 365 per Power BI** su **Su** \> **salvataggio.** 
  
Il processo di raccolta dei dati verrà completato in due-48 ore a seconda delle dimensioni del tenant. Il **pulsante Vai a Power BI** verrà abilitato (non più grigio) al termine della raccolta dei dati. 
    
### <a name="start-the-template-app"></a>Avviare l'app modello

Per avviare l'app modello, è necessario essere un amministratore **globale,** un lettore di **report,** un amministratore di **Exchange,** un amministratore **di Skype for Business** o un amministratore di **SharePoint.** 
  
1. Copiare l'ID tenant e **selezionare Vai a Power BI**.
    
2.  Dopo aver scaricato Power BI, eseguire l'accesso. Seleziona **Quindi App** Ottieni -> **app** dal menu di spostamento.    
  
3. Nella scheda **App** digita Microsoft 365 nella casella di ricerca e quindi seleziona Analisi di utilizzo di **Microsoft 365** \> **Scarica ora**.

    [![Seleziona Scarica ora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Dopo l'installazione dell'app. Seleziona il riquadro per aprirlo.

5.  Seleziona **Esplora app per** visualizzare l'app con dati di esempio. Scegliere **Connetti** per connettere l'app ai dati dell'organizzazione.

6.  Scegliere **Connetti**, nella schermata **Connect to Microsoft 365 usage analytics,** quindi digitare l'ID tenant (senza trattini) copiato nel passaggio (1) e selezionare **Avanti**.
    
7. Nella schermata successiva, selezionare **OAuth2 come** **metodo di autenticazione** \> **Accedi.** Se scegli un altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.
    
    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Dopo aver creato un'istanza dell'app modello, il dashboard di analisi di utilizzo di Microsoft 365 sarà disponibile in Power BI sul Web. Il caricamento iniziale del dashboard avrà un tempo compreso tra 2 e 30 minuti.
  
Le aggregazioni a livello di tenant saranno disponibili in tutti i report dopo aver acconsentto esplicitamente. I dettagli a livello di utente saranno disponibili solo il **5 del mese di calendario successivo dopo aver scelto**. Ciò inciderà su tutti i report in Attività utente (vedere Esplorare e utilizzare i report nell'analisi dell'utilizzo di [Microsoft 365](navigate-and-utilize-reports.md) per suggerimenti su come visualizzare e usare questi report).
    
## <a name="make-the-collected-data-anonymous"></a>Rendere anonimi i dati raccolti

Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come i nomi di utenti, gruppi e siti nei report e nell'app modello.
  
1. Nell'interfaccia di amministrazione  passare a Impostazioni Impostazioni organizzazione e nella scheda \>  **Servizi** scegliere **Report.**
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo che all'app modello.
  
3. Selezionare **Salva modifiche**.