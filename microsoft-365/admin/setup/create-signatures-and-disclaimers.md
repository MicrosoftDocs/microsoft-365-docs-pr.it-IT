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
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Informazioni su come gestire le firme di posta elettronica, incluse dichiarazioni di non responsabilità legali o dichiarazioni di divulgazione per tutti i messaggi di posta elettronica che entrano o escono dall'organizzazione.
ms.openlocfilehash: e1c3df235442fdc6f569825a7137c92bfc5bb044
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244528"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Creare firme e dichiarazioni di non responsabilità a livello di organizzazione

 È possibile gestire le firme di posta elettronica aggiungendo una firma di posta elettronica, una dichiarazione di non responsabilità legale o una dichiarazione di divulgazione ai messaggi di posta elettronica che entrano o lasciano l'organizzazione. È possibile configurarlo per applicarlo a tutti i messaggi in arrivo e in uscita, come illustrato di seguito. Oppure puoi applicarlo a determinati messaggi come quelli contenenti parole o modelli di testo specifici.

 Guarda un breve video sulla creazione di una firma di posta elettronica a livello aziendale. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Creare una firma da applicare a tutti i messaggi

> [!TIP]
> Le firme a livello di organizzazione sono denominate "dichiarazioni di non responsabilità", indipendentemente da ciò che includono. Ad esempio, possono essere solo una firma o anche includere l'indirizzo, la dichiarazione di non responsabilità legale o altre informazioni desiderate.
    
::: moniker range="o365-worldwide"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Seleziona l'icona di avvio ![ delle app L'icona di avvio delle ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) app e quindi seleziona **Amministratore.**
   
    Non riesci a trovare l'app che stai cercando? Nell'icona di avvio delle app seleziona **Tutte le app** per visualizzare un elenco alfabetico delle app disponibili. Tramite la lista è possibile cercare un'applicazione specifica. 
    
2. Selezionare **Admin center** e quindi scegliere **Exchange**.
    
3. In Flusso di posta selezionare **Regole**.
    
4. Seleziona **+** l'icona (Aggiungi) e scegli **Applica dichiarazioni di non responsabilità.**
    
5. Assegnare un nome alla regola.
    
6. In **Applica questa regola** selezionare **[Applica a tutti i messaggi]**.
    
    > [!TIP]
    > [Altre informazioni](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) su come applicare condizioni se non si vuole che la dichiarazione di non responsabilità venga applicata a tutti i messaggi. Questo articolo sull'ambito è Exchange Server, ma si applica anche Microsoft 365. 
  
7. In Effettua le operazioni seguenti lasciare selezionata l'opzione **Aggiungi una dichiarazione di non responsabilità**. 
    
8.  Seleziona **Immetti testo** e digita la dichiarazione di non responsabilità. 
    
    > [!TIP]
    > [Altre informazioni](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sulla formattazione di dichiarazioni di non responsabilità. Questo articolo di formattazione è Exchange Server, ma si applica anche Microsoft 365. 

9. Selezionare **Seleziona uno** e scegliere A **capo** come opzione di fallback. Quindi scegliere **OK**. Con questa opzione, se la dichiarazione di non responsabilità non può essere aggiunta a causa di un'impostazione della posta, come la crittografia, verrà incorporata nella busta del messaggio.
    
10. Lasciare selezionata l'opzione **Controlla questa regola con livello di gravità**. Quindi scegliere **Basso**, **Medio** o **Alto** come livello da usare nel log dei messaggi. 
    
11. Scegliere **Applica** per attivare immediatamente la dichiarazione di non responsabilità, a meno che non si voglia prima testarla. 
    
12. Scegliere **Altre opzioni** per includere altre condizioni o eccezioni. 
    
13. Al termine scegliere **Salva**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitazioni delle firme a livello di organizzazione

Non è possibile eseguire le operazioni seguenti quando si gestiscono le firme di posta elettronica in Microsoft 365:
  
- Inserire la firma direttamente sotto l'ultima risposta o inoltro di posta elettronica
    
- Visualizzare le firme di posta elettronica sul lato server nelle cartelle Posta inviata degli utenti
    
- Incorporare immagini nelle firme di posta elettronica
    
- Ignorare le righe che contengono variabili che non è stato possibile aggiornare (ad esempio, perché il valore non è stato fornito per un utente)
    
Per ottenere queste e altre funzionalità per gestire le firme di posta elettronica, utilizzare uno strumento di terze parti. Eseguire una ricerca in Internet per il **software per la firma della posta elettronica.** Alcuni di questi provider sono Microsoft Gold Partners e il loro software fornisce queste funzionalità. 
  
## <a name="more-resources"></a>Altre risorse

- Per [informazioni sull'utilizzo](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) di PowerShell, vedere Dichiarazioni di non responsabilità, firme, piè di pagina o intestazioni a livello Exchange Online messaggio a livello di organizzazione.