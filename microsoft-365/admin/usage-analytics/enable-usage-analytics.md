---
title: Abilitare l'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Scopri come iniziare a raccogliere dati per il tenant usando l'app Microsoft 365 modello Analisi di utilizzo in Power BI.
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394750"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Abilitare l'analisi dell'utilizzo di Microsoft 365

Microsoft 365'analisi dei dati di utilizzo non è ancora disponibile per Microsoft 365 per il governo Community.

## <a name="before-you-begin"></a>Prima di iniziare

Per iniziare a usare Microsoft 365 di utilizzo, devi prima rendere disponibili i dati nel interfaccia di amministrazione di Microsoft 365, quindi avviare l'app modello in Power BI.

## <a name="get-power-bi"></a>Ottenere Power BI

Se non si dispone già di Power BI, è possibile iscriversi [a Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleziona **Prova gratuitamente** per iscriverti a una versione di valutazione o Acquista ora per ottenere Power BI Pro. 


È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.

> [!NOTE]
> È necessaria una licenza Power BI Pro per installare, personalizzare e distribuire un'app modello. Per ulteriori informazioni, vedere [Prerequisiti](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Per condividere i dati, sia l'utente che le persone con cui si condividono i dati, è necessaria una licenza di Power BI Pro o il contenuto deve essere in un'area di lavoro in un servizio [premium di Power BI](/power-bi/service-premium-what-is).

## <a name="enable-the-template-app"></a>Abilitare l'app modello

Per abilitare l'app modello, devi essere un **amministratore globale.**

Per [ulteriori informazioni, vedere](../add-users/about-admin-roles.md) Sui ruoli di amministratore.

1. Nell'interfaccia di amministrazione passare alla scheda **Impostazioni** \> **Impostazioni organizzazione** \> **Servizi.**

2. Nella scheda **Servizi** selezionare  **Report**.

3. Nel riquadro Report che si apre imposta Rendi disponibili i dati del **report** Microsoft 365 analisi di utilizzo per Power BI su **Al** \> **salvataggio.**

Il processo di raccolta dei dati verrà completato in due-48 ore a seconda delle dimensioni del tenant. Il **pulsante Vai a Power BI** verrà abilitato (non più grigio) al termine della raccolta dei dati.

## <a name="start-the-template-app"></a>Avviare l'app modello

Per avviare l'app modello, devi essere un amministratore **globale,** un lettore di **report,** Exchange **amministratore,** Skype for Business **amministratore** o SharePoint **amministratore.**

1. Copiare l'ID tenant e **selezionare Vai a Power BI**.

2. Dopo aver scaricato Power BI, eseguire l'accesso. Seleziona **Quindi App** Ottieni -> **app** dal menu di spostamento.

3. Nella scheda **App** digita Microsoft 365 nella casella di ricerca e quindi seleziona Microsoft 365 analisi di **utilizzo** \> **Scarica ora**.

    [![Seleziona Scarica ora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. Dopo l'installazione dell'app. Seleziona il riquadro per aprirlo.

5. Seleziona **Esplora app per** visualizzare l'app con dati di esempio. Scegli **Connessione** per connettere l'app ai dati dell'organizzazione.

6. Scegliere **Connessione**, nella  schermata Connessione per Microsoft 365 analisi di utilizzo, quindi digitare l'ID tenant (senza trattini) copiato nel passaggio (1) e selezionare **Avanti**.

7. Nella schermata successiva, selezionare **OAuth2 come** **metodo di autenticazione** \> **Accedi.** Se scegli un altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.

    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. Dopo aver creato un'istanza dell'app modello, Microsoft 365 dashboard di analisi dell'utilizzo sarà disponibile in Power BI sul Web. Il caricamento iniziale del dashboard avrà un tempo compreso tra 2 e 30 minuti.

Le aggregazioni a livello di tenant saranno disponibili in tutti i report dopo aver acconsentto esplicitamente. I dettagli a livello di utente saranno disponibili solo il **5 del mese di calendario successivo dopo aver scelto**. Ciò inciderà su tutti i report in Attività utente (vedere Esplorare e utilizzare i report [in](navigate-and-utilize-reports.md) analisi di utilizzo di Microsoft 365 per suggerimenti su come visualizzare e usare questi report).

## <a name="make-the-collected-data-anonymous"></a>Rendere anonimi i dati raccolti

Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come i nomi di utenti, gruppi e siti nei report e nell'app modello.

1. Nell'interfaccia di amministrazione  passare alla Impostazioni Org Impostazioni e nella scheda Servizi \> scegliere **Report.** 

2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo che all'app modello.

3. Selezionare **Salva modifiche**.

## <a name="related-content"></a>Contenuto correlato

[Informazioni sull'analisi dei](usage-analytics.md) dati di utilizzo (articolo)\
[Ottenere la versione più recente dell'analisi di utilizzo](get-the-latest-version-of-usage-analytics.md) (articolo)\
[Esplorare e utilizzare i report nell'Microsoft 365 di utilizzo](navigate-and-utilize-reports.md) (articolo)