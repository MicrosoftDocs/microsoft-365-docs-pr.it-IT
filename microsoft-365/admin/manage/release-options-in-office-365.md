---
title: Configurare le opzioni di Standard o Targeted Release in Office 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Informazioni su come configurare l'opzione di rilascio per gli aggiornamenti di nuovi prodotti e funzionalità nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252799"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a>Configurare le opzioni di Standard o Targeted Release in Office 365

Con Office 365 si possono ricevere i nuovi aggiornamenti e le nuove funzionalità del prodotto non appena sono disponibili invece di effettuare costosi aggiornamenti a distanza di pochi anni. È possibile gestire la modalità di ricezione degli aggiornamenti da parte dell'organizzazione. Ad esempio, è possibile iscriversi per un rilascio anticipato per fare in modo che l'organizzazione riceva per prima gli aggiornamenti. È possibile specificare che solo determinate persone devono ricevere gli aggiornamenti oppure mantenere la pianificazione dei rilasci predefinita e ricevere gli aggiornamenti in un secondo tempo. Questo articolo illustra le varie opzioni di rilascio e come usarle per l'organizzazione.
  
> [!IMPORTANT]
> Gli aggiornamenti di Office 365 descritti in questo articolo si applicano a Office 365, SharePoint Online ed Exchange Online, ma non a Skype for Business e ai servizi correlati. Queste opzioni di rilascio rappresentano un'iniziativa mirata a rilasciare le modifiche apportate a Office 365, ma non possono essere garantite costantemente e per tutti gli aggiornamenti. 
  
## <a name="how-it-works---release-validation"></a>Funzionamento - Convalida dei rilasci

Tutte le nuove versioni sono state verificate e convalidate dal team di funzionalità, quindi da tutto il team di Office 365, seguito da tutti i membri di Microsoft. Dopo il test e la convalida interni, il passaggio successivo è il rilascio **Targeted Release** (precedentemente noto come First Release) per i clienti che hanno acconsentito esplicitamente. A ogni anello di rilascio, Microsoft raccoglie feedback dagli utenti e convalida ulteriormente la qualità monitorando le metriche di utilizzo principali. Questa serie di convalide progressive viene applicata per garantire che la versione risulti quanto più stabile possibile in tutto il mondo. I rilasci sono illustrati nella figura seguente. 
  
![Rilasci gli anelli di convalida per Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Per gli aggiornamenti significativi, i clienti di Office vengono inizialmente informati dalla [Roadmap di Microsoft 365](https://products.office.com/business/office-365-roadmap). Man mano che un aggiornamento si avvicina all'implementazione, viene comunicato tramite il [centro messaggi di Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Per accedere al centro messaggi tramite l'interfaccia di [Amministrazione](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center), è necessario un account di Office 365 o Azure ad. Gli utenti di Office 365 Home Plan non dispongono di un centro di amministrazione.


## <a name="standard-release"></a>Standard Release

Questa è l'opzione predefinita in cui l'utente e gli utenti ricevono gli aggiornamenti più recenti quando vengono rilasciati in generale a tutti i clienti.
  
Una buona prassi è quella di lasciare la maggior parte degli utenti in **versione standard** e i professionisti IT e gli utenti di Power in **Release mirate** per valutare nuove funzionalità e preparare i team per supportare gli utenti e i dirigenti aziendali. 
  
> [!NOTE]
> Se si passa dalla versione Targeted Release alla versione Standard Release, gli utenti potrebbero perdere l'accesso alle funzionalità non ancora incluse in Standard Release. 
  
## <a name="targeted-release"></a>Rilascio assegnato

Questa opzione consente di ricevere per primi gli aggiornamenti più recenti e di contribuire a migliorare il prodotto fornendo un riscontro precoce. È possibile specificare singole persone o l'intera organizzazione come destinatari degli aggiornamenti.
  
> [!IMPORTANT]
> Gli aggiornamenti di grandi dimensioni o complessi possono richiedere più tempo di altri per evitare un impatto negativo sugli utenti. L'esatta tempistica per un rilascio non è garantita in alcun modo. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release per l'intera organizzazione

Se si [Configura l'opzione di rilascio nell'](#set-up-the-release-option-in-the-admin-center) interfaccia di amministrazione per questa opzione, tutti gli utenti riceveranno l'esperienza di rilascio mirata. Per le organizzazioni con più di 300 utenti, è consigliabile usare un abbonamento di test per questa opzione. Per informazioni sull'abbonamento di test, contattare il proprio referente Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Targeted Release per utenti selezionati

Se si [Configura l'opzione di rilascio nell'](#set-up-the-release-option-in-the-admin-center) interfaccia di amministrazione per questa opzione, è possibile definire gli utenti specifici, in genere gli utenti di alimentazione, per ricevere l'accesso precoce alle caratteristiche e alle funzionalità. 
  
## <a name="benefits-of-targeted-release"></a>Vantaggi della versione Targeted Release

La versione Targeted Release consente ad amministratori, responsabili delle modifiche o responsabili degli aggiornamenti di Office 365 di preparare l'ambiente per le modifiche imminenti, eseguendo queste operazioni:
  
- Testare e convalidare i nuovi aggiornamenti prima che vengano rilasciate a tutti gli utenti dell'organizzazione.
    
- Preparare la documentazione e le notifiche utente prima del rilascio degli aggiornamenti in tutto il mondo.
    
- Preparare l'help desk interno per le modifiche future.
    
- Controllare le revisioni relative a sicurezza e conformità.
    
- Usare i controlli delle funzionalità, se applicabili, per controllare il rilascio degli aggiornamenti agli utenti finali.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurare l'opzione di rilascio nell'interfaccia di amministrazione

La procedura seguente consente di modificare le modalità di ricezione degli aggiornamenti di Office 365 nell'organizzazione. È necessario essere un amministratore globale in Office 365 per acconsentire esplicitamente.
  
> [!IMPORTANT]
> L'applicazione delle modifiche in Office 365 può richiedere fino a 24 ore. Se si disattiva l'opzione Targeted Release dopo averla abilitata, è possibile che gli utenti non possano più accedere alle funzionalità non ancora inserite nel rilascio pianificato. 
  
1. Nell'interfaccia di amministrazione, passare all'impostazione **Impostazioni** > **** e nella scheda **profilo organizzazione** scegliere **Preferenze di rilascio**.

5. Per disabilitare la versione di destinazione, selezionare **versione standard**, quindi fare clic su **Salva modifiche**. 
    
6. Per abilitare la versione di destinazione per tutti gli utenti dell'organizzazione, selezionare **rilasci mirati per tutti**, quindi selezionare **Salva modifiche**. 
    
7. Per abilitare la versione di destinazione per alcuni utenti dell'organizzazione, selezionare **rilasci mirati per i clienti selezionati**, quindi selezionare **Salva modifiche**. 
    
8. Scegliere **selezionare gli** utenti per aggiungere gli utenti uno alla volta oppure **caricare gli utenti** per aggiungerli in blocco.
    
9. Dopo aver completato l'aggiunta di utenti, selezionare **Salva modifiche**.



## <a name="get-the-targeted-release-version-of-office"></a>Ottenere la versione finale di Office

Per installare una build Targeted Release di Office, [eseguire questa procedura](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Questa build consente di accedere in anteprima alle nuove funzionalità di Office 2016 per desktop Windows.
  
## <a name="learn-more"></a>Ulteriori informazioni

Informazioni su come [gestire i messaggi](https://docs.microsoft.com/office365/admin/manage/message-center) nel [centro messaggi di Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) per ottenere le notifiche relative agli aggiornamenti e rilasci imminenti di Office 365.
