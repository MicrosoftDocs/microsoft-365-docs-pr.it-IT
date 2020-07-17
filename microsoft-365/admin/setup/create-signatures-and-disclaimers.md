---
title: Creare firme e dichiarazioni di non responsabilità a livello di organizzazione
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Informazioni su come aggiungere la firma di posta elettronica, la dichiarazione di non responsabilità legale o la divulgazione a tutti i messaggi di posta elettronica che entrano o lasciano l'organizzazione.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779882"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Creare firme e dichiarazioni di non responsabilità a livello di organizzazione

 È possibile aggiungere una firma di posta elettronica, una dichiarazione di non responsabilità legale o una dichiarazione di riservatezza ai messaggi di posta elettronica in entrata e in uscita dall'organizzazione. Questo elemento può essere configurato in modo da applicarlo a tutti i messaggi in entrata e in uscita, come illustrato di seguito, oppure solo a determinati messaggi, come quelli che contengono parole o modelli di testo specifici.

 Guardare un breve video sulla creazione di una firma di posta elettronica a livello aziendale. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Creare una firma da applicare a tutti i messaggi

> [!TIP]
> Le firme a livello dell'organizzazione sono denominate "dichiarazioni di non responsabilità", indipendentemente da ciò che includono. Ad esempio, possono essere solo una firma o includere anche l'indirizzo, la dichiarazione di non responsabilità legale o altre informazioni desiderate.
    
::: moniker range="o365-worldwide"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Seleziona l'icona di avvio ![ delle app ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) e quindi seleziona **amministratore**.
   
    Non è possibile trovare l'app che si sta cercando? Dall'icona di avvio delle app, seleziona **tutte le app** per visualizzare un elenco alfabetico delle app disponibili. Da qui, è possibile cercare un'app specifica. 
    
2. Selezionare interfaccia di **Amministrazione**, quindi fare clic su **Exchange**.
    
3. In flusso di posta, selezionare **regole**.
    
4. Selezionare l' **+** icona (Aggiungi) e scegliere **applica dichiarazioni**di non responsabilità.
    
5. Assegnare un nome alla regola.
    
6. In **applica questa regola**selezionare **[applica a tutti i messaggi]**.
    
    > [!TIP]
    > [Altre informazioni](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) su come applicare condizioni se non si vuole che la dichiarazione di non responsabilità venga applicata a tutti i messaggi. (Questo articolo di ambito è per Exchange Server, ma si applica anche a Microsoft 365). 
  
7. In Effettua le operazioni seguenti lasciare selezionata l'opzione **Aggiungi una dichiarazione di non responsabilità**. 
    
8.  Selezionare **Immetti testo** e digitare la dichiarazione di non responsabilità. 
    
    > [!TIP]
    > [Altre informazioni](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sulla formattazione di dichiarazioni di non responsabilità. (Questo articolo di formattazione è per Exchange Server, ma si applica anche a Microsoft 365). 

9. Selezionare **selezionarne una** e scegliere **Wrap** come opzione di fallback. Quindi scegliere **OK**. Con questa opzione, se la dichiarazione di non responsabilità non può essere aggiunta a causa di un'impostazione della posta, come la crittografia, verrà incorporata nella busta del messaggio.
    
10. Lasciare selezionata l'opzione **Controlla questa regola con livello di gravità**. Quindi scegliere **Basso**, **Medio** o **Alto** come livello da usare nel log dei messaggi. 
    
11. Scegliere **Applica** per attivare immediatamente la dichiarazione di non responsabilità, a meno che non si voglia prima testarla. 
    
12. Scegliere **Altre opzioni** per includere altre condizioni o eccezioni. 
    
13. Al termine scegliere **Salva**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitazioni delle firme estese dell'organizzazione

Non è possibile effettuare le seguenti operazioni con le firme di Microsoft 365:
  
- Inserire la firma direttamente sotto la risposta di posta elettronica più recente o inoltrare
    
- Visualizzare le firme dei messaggi di posta elettronica sul server nelle cartelle degli elementi inviati degli utenti
    
- Incorporare immagini nelle firme di posta elettronica
    
- Consente di ignorare le righe che contengono variabili che non possono essere aggiornate (ad esempio, poiché il valore non è stato fornito per un utente)
    
Per ottenere queste e altre funzionalità, utilizzare uno strumento di terze parti. Eseguire una ricerca su Internet per il **software di firma della posta elettronica**. Alcuni di questi provider sono Microsoft Gold Partners e il relativo software fornisce queste funzionalità. 
  
## <a name="more-resources"></a>Altre risorse

- Per informazioni sull'utilizzo di PowerShell, vedere dichiarazioni, piè di pagina [o intestazioni dei messaggi a livello di organizzazione in Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) . 
    

