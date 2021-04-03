---
title: Configurare le opzioni di rilascio Standard o Mirato
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Informazioni su come configurare l'opzione di rilascio per gli aggiornamenti di nuovi prodotti e funzionalità nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: d3692f2e1cca58fec81f2ad492b9232d5576f99b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579255"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configurare le opzioni di rilascio Standard o Mirato

> [!IMPORTANT]
> Gli aggiornamenti di Microsoft 365 descritti in questo articolo si applicano a Microsoft 365, SharePoint Online ed Exchange Online. Queste opzioni di rilascio sono modi mirati e più efficaci per rilasciare le modifiche a Microsoft 365, ma non possono essere garantite in qualsiasi momento o per tutti gli aggiornamenti. Non si applicano alle app di Microsoft 365, Skype for Business, Microsoft Teams e ai servizi correlati. Per informazioni sulle opzioni di rilascio per Microsoft 365 Apps, vedere Panoramica dei canali di [aggiornamento per Microsoft 365 Apps.](/deployoffice/overview-update-channels)

Con Microsoft 365, si ricevono nuovi aggiornamenti di prodotti e funzionalità non appena diventano disponibili invece di eseguire aggiornamenti costosi ogni pochi anni. È possibile gestire il modo in cui l'organizzazione riceve questi aggiornamenti. Ad esempio, è possibile iscriversi a un rilascio anticipato in modo che l'organizzazione riceva prima gli aggiornamenti. È possibile specificare che solo determinati utenti ricevano gli aggiornamenti. In caso contrario, è possibile rimanere in base alla pianificazione di rilascio predefinita e ricevere gli aggiornamenti in un secondo momento. In questo articolo vengono illustrate le diverse opzioni di rilascio e viene spiegato come utilizzarle per l'organizzazione.

## <a name="how-it-works---release-validation"></a>Funzionamento - Convalida dei rilasci

Qualsiasi nuova versione viene prima testata e convalidata dal team delle funzionalità, quindi dall'intero team delle funzionalità di Microsoft 365, seguito da tutti i microsoft. Dopo il test e la convalida interni, il passaggio successivo è il rilascio **Targeted Release** (precedentemente noto come First Release) per i clienti che hanno acconsentito esplicitamente. A ogni anello di rilascio, Microsoft raccoglie feedback dagli utenti e convalida ulteriormente la qualità monitorando le metriche di utilizzo principali. Questa serie di convalide progressive viene applicata per garantire che la versione risulti quanto più stabile possibile in tutto il mondo. I rilasci sono illustrati nella figura seguente. 
  
![Rilasciare gli anelli di convalida per Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Per gli aggiornamenti significativi, i clienti vengono inizialmente informati dalla roadmap di [Microsoft 365.](https://products.office.com/business/office-365-roadmap) Quando un aggiornamento si avvicina alla distribuzione, viene comunicato tramite il Centro messaggi di [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> È necessario un account Microsoft 365 o Azure AD per accedere al Centro messaggi tramite [l'interfaccia di amministrazione.](/office365/admin/admin-overview/about-the-admin-center) Gli utenti del piano home di Microsoft 365 non dispongono di un'interfaccia di amministrazione.


## <a name="standard-release"></a>Standard Release

Questa è l'opzione predefinita in cui l'utente e gli utenti ricevono gli aggiornamenti più recenti quando vengono rilasciati su larga base a tutti i clienti.
  
Una buona pratica consiste nel lasciare la maggior parte degli utenti nel rilascio **Standard** e professionisti IT e power users in **Rilascio** mirato per valutare nuove funzionalità e preparare i team a supportare gli utenti aziendali e i dirigenti. 
  
> [!NOTE]
> Se si passa dalla versione Targeted Release alla versione Standard Release, gli utenti potrebbero perdere l'accesso alle funzionalità non ancora incluse in Standard Release. 
  
## <a name="targeted-release"></a>Rilascio assegnato

Questa opzione consente di ricevere per primi gli aggiornamenti più recenti e di contribuire a migliorare il prodotto fornendo un riscontro precoce. È possibile specificare singole persone o l'intera organizzazione come destinatari degli aggiornamenti.
  
> [!IMPORTANT]
> Gli aggiornamenti di grandi dimensioni o complessi possono richiedere più tempo di altri per evitare un impatto negativo sugli utenti. L'esatta tempistica per un rilascio non è garantita in alcun modo. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release per l'intera organizzazione

Se si [configura l'opzione di rilascio nell'interfaccia di amministrazione](#set-up-the-release-option-in-the-admin-center) per questa opzione, tutti gli utenti otterrà l'esperienza di rilascio mirato. Per le organizzazioni con più di 300 utenti, è consigliabile usare un abbonamento di test per questa opzione. Per informazioni sull'abbonamento di test, contattare il proprio referente Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Targeted Release per utenti selezionati

Se si [configura l'opzione di](#set-up-the-release-option-in-the-admin-center) rilascio nell'interfaccia di amministrazione per questa opzione, è possibile definire utenti specifici, in genere utenti esperti, per ricevere l'accesso anticipato a funzionalità e funzionalità. 
  
## <a name="benefits-of-targeted-release"></a>Vantaggi della versione Targeted Release

Il rilascio mirato consente agli amministratori, ai responsabili delle modifiche o a chiunque altro responsabile degli aggiornamenti di Microsoft 365 di prepararsi per le modifiche future consentendo loro di:
  
- Testare e convalidare i nuovi aggiornamenti prima che vengano rilasciate a tutti gli utenti dell'organizzazione.
    
- Preparare la documentazione e le notifiche utente prima del rilascio degli aggiornamenti in tutto il mondo.
    
- Preparare l'help desk interno per le modifiche future.
    
- Controllare le revisioni relative a sicurezza e conformità.
    
- Usare i controlli delle funzionalità, se applicabili, per controllare il rilascio degli aggiornamenti agli utenti finali.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurare l'opzione di rilascio nell'interfaccia di amministrazione

È possibile modificare il modo in cui l'organizzazione riceve gli aggiornamenti di Microsoft 365 seguendo questa procedura. Devi essere un amministratore globale in Microsoft 365 per acconsentire esplicitamente.
  
> [!IMPORTANT]
> L'applicazione delle modifiche seguenti in Microsoft 365 può richiedere fino a 24 ore. Se si disattiva l'opzione Targeted Release dopo averla abilitata, è possibile che gli utenti non possano più accedere alle funzionalità non ancora inserite nel rilascio pianificato. 
  
1. Nell'interfaccia di amministrazione passare a Impostazioni Impostazione organizzazione e nella scheda  >   **Profilo organizzazione** scegliere Preferenze **di rilascio.**

5. Per disabilitare la versione di destinazione, selezionare **Rilascio standard,** quindi **selezionare Salva modifiche.** 
    
6. Per abilitare il rilascio mirato per tutti gli utenti dell'organizzazione, selezionare **Rilascio mirato per tutti,** quindi selezionare **Salva modifiche.** 
    
7. Per abilitare il rilascio mirato per alcune persone dell'organizzazione, selezionare **Rilascio mirato per** gli utenti selezionati, quindi selezionare Salva **modifiche.** 
    
8. Scegliere **Seleziona utenti** per aggiungere gli utenti uno alla volta oppure Carica **utenti** per aggiungerli in blocco.
    
9. Dopo aver aggiunto gli utenti, selezionare **Salva modifiche.**


  
## <a name="learn-more"></a>Ulteriori informazioni

Scopri come gestire [i messaggi nel](/office365/admin/manage/message-center) centro messaggi di Microsoft [365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) per ricevere notifiche sui prossimi aggiornamenti e rilasci di Microsoft 365.

## <a name="related-articles"></a>Articoli correlati

[Office Insider](https://insider.office.com/join/windows)
