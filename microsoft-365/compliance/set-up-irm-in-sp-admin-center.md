---
title: Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Informazioni su come utilizzare IRM di SharePoint Online tramite Microsoft Azure Active Directory Rights Management Services (RMS) per proteggere elenchi e raccolte documenti di SharePoint.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819196"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint

In SharePoint Online, la protezione IRM viene applicata ai file a livello di elenco e di raccolta. Prima che l’organizzazione possa usare la protezione IRM, è necessario prima di tutto configurare Rights Management. IRM si basa sul servizio Microsoft Azure AD Rights Management di Azure Information Protection per crittografare e assegnare restrizioni di utilizzo. Alcuni piani di Microsoft 365 includono Azure Rights Management, ma non tutti. Per altre informazioni, vedere Come le applicazioni e i servizi [di Office supportano Azure Rights Management.](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Attivare il servizio IRM tramite l'interfaccia di amministrazione di SharePoint

Prima che l'organizzazione possa proteggere con IRM elenchi e raccolte di SharePoint, è necessario attivare il servizio Rights Management per l'organizzazione. Per ulteriori informazioni, vedere [Attivazione di Azure Rights Management.](https://docs.microsoft.com/information-protection/deploy-use/activate-service) È necessario utilizzare un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale per abilitare il servizio Rights Management. In caso contrario, non sarà possibile utilizzare le funzionalità IRM con SharePoint Online.
  
Dopo aver attivato il servizio Rights Management, accedere all'interfaccia di amministrazione di SharePoint per attivare IRM.
  
1. Accedere come amministratore globale o amministratore di SharePoint.
    
2. Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) nell'angolo in alto a sinistra e scegliere **Amministratore** per aprire l'interfaccia di amministrazione di Microsoft 365. Se il riquadro Amministratore non è visualizzato, non si dispone delle autorizzazioni di amministratore nell'organizzazione. 
    
3. Nel riquadro sinistro scegliere Interfaccia di amministrazione **di** \> **SharePoint.**
    
4. Nel riquadro sinistro scegliere **impostazioni** e quindi scegliere la pagina delle impostazioni **classiche.**
    
5. Nella sezione **Information Rights Management (IRM)** scegliere Usa il servizio **IRM** specificato nella configurazione e quindi scegliere Aggiorna **impostazioni IRM.** Dopo aver aggiornato le impostazioni IRM, gli utenti dell'organizzazione possono iniziare a utilizzare IRM nei relativi elenchi e raccolte documenti di SharePoint. Tuttavia, le opzioni a tale scopo potrebbero richiedere fino a un'ora per essere visualizzate in Impostazioni raccolta ed Impostazioni elenco.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Elenchi ed raccolte documenti di SharePoint abilitati per IRM
<a name="__toc220831191"> </a>

Dopo aver aggiornato le impostazioni IRM, i proprietari dei siti possono proteggere con IRM gli elenchi e le raccolte documenti di SharePoint. Per ulteriori informazioni, vedere [Applicare Information Rights Management a un elenco o a una raccolta.](apply-irm-to-a-list-or-library.md)
  
Quando i proprietari dei siti abilitano IRM per un elenco o una raccolta, possono proteggere qualsiasi tipo di file supportato in tale elenco o raccolta. Quando IRM è abilitato per una raccolta, la gestione dei diritti si applica a tutti i file in tale raccolta. Quando si abilita IRM per un elenco, la gestione dei diritti si applica solo ai file allegati alle voci di elenco e non alle voci di elenco effettive.
  
Quando gli utenti scaricano file in un elenco o in una raccolta abilitata per IRM, i file vengono crittografati in modo che solo gli utenti autorizzati possano visualizzarli. Ogni file rights-managed contiene anche una licenza di pubblicazione che impone restrizioni alle persone che visualizzano il file. Le restrizioni tipiche includono la possibilità di rendere un file di sola lettura, disabilitare la copia del testo, impedire agli utenti di salvare una copia locale e impedire agli utenti di stampare il file. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di pubblicazione all'interno del file protetto da Rights Management per applicare queste restrizioni. Questo è il modo in cui un file rights-managed mantiene la protezione anche dopo il download. Per abilitare IRM in un elenco o una raccolta, vedere [Applicare Information Rights Management a un elenco o a una raccolta.](apply-irm-to-a-list-or-library.md)
  
Non è possibile creare o modificare documenti in una raccolta abilitata per IRM utilizzando Office in un browser. Al contrario, una persona alla volta può scaricare e modificare i file crittografati con IRM. Utilizzare l'archiviazione e l'estrazione per gestire la  *creazione*  condivisa o la creazione condivisa tra più utenti. 
  
Quando si scarica un file PDF da una raccolta protetta con IRM, Microsoft 365 crea un file PDF protetto. L'estensione del file non cambia, ma il file è protetto. Per visualizzare questo file, è necessario il visualizzatore di Azure Information Protection, il client Azure Information Protection completo o un'altra applicazione che supporta la visualizzazione di file PDF protetti. 
  
SharePoint Online supporta la crittografia dei tipi di file seguenti:
  
- PDF
    
- Formati di file della versione 97-2003 per i Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formati Office Open XML per i Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formato XPS (XML Paper Specification)
 
> [!NOTE]
> La protezione IRM non può essere applicata ai documenti protetti (come i file PDF firmati digitalmente) perché SharePoint deve aprire il documento al caricamento. 

## <a name="next-steps"></a>Passaggi successivi
<a name="__toc220831191"> </a>

Dopo aver abilitato IRM per SharePoint Online, è possibile iniziare ad applicare rights management a elenchi e raccolte. Per informazioni, vedere [Applicare Information Rights Management a un elenco o a una raccolta.](apply-irm-to-a-list-or-library.md)
  
Il nuovo client di sincronizzazione di OneDrive per Windows ora supporta la sincronizzazione delle raccolte documenti di SharePoint protette con IRM e dei percorsi di OneDrive (purché l'impostazione IRM per la raccolta non sia impostata per la scadenza dei diritti di accesso ai documenti). Per altre informazioni o per iniziare a distribuire il nuovo client di sincronizzazione, vedere Distribuire il nuovo client di sincronizzazione di [OneDrive per Windows.](https://docs.microsoft.com/onedrive/deploy-on-windows)
  
[Inizio pagina](set-up-irm-in-sp-admin-center.md)
