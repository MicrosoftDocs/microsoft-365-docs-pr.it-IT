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
description: Informazioni su come usare SharePoint IRM online tramite Microsoft Azure Active Directory Rights Management Services (RMS) per proteggere SharePoint elenchi e raccolte documenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919402"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint

In SharePoint Online, la protezione IRM viene applicata ai file a livello di elenco e di raccolta. Prima che l’organizzazione possa usare la protezione IRM, è necessario prima di tutto configurare Rights Management. IRM si basa sul servizio Microsoft Azure AD Rights Management di Azure Information Protection per crittografare e assegnare restrizioni di utilizzo. Alcuni Microsoft 365 includono Azure Rights Management, ma non tutti. Per altre informazioni, vedere Come Office applicazioni e servizi di [Azure Rights Management.](/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Attivare il servizio IRM con l SharePoint intervaria di amministrazione

Prima che l'organizzazione possa proteggere SharePoint e raccolte con IRM, è necessario attivare il servizio Rights Management per l'organizzazione. Per informazioni su come [vedere Attivazione di Azure Rights Management](/information-protection/deploy-use/activate-service). È necessario utilizzare un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale per abilitare il servizio Rights Management. In caso contrario, non sarà possibile utilizzare le funzionalità IRM con SharePoint Online.
  
Dopo aver attivato il servizio Rights Management, accedere all'SharePoint di amministrazione per attivare IRM.
  
1. Accedi come amministratore globale o amministratore SharePoint amministratore.
    
2. Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) nell'angolo in alto a sinistra e scegliere **Amministratore** per aprire l'interfaccia di amministrazione di Microsoft 365. Se il riquadro Amministratore non è visualizzato, non si dispone delle autorizzazioni di amministratore nell'organizzazione. 
    
3. Nel riquadro sinistro scegliere **Interfaccia di amministrazione** \> **SharePoint**.
    
4. Nel riquadro sinistro scegliere **impostazioni** e quindi pagina impostazioni **classiche.**
    
5. Nella sezione **Information Rights Management (IRM)** scegliere **Use the IRM service specified in your configuration** e quindi Refresh **IRM Impostazioni**. Dopo aver aggiornato le impostazioni IRM, gli utenti dell'organizzazione possono iniziare a usare IRM nei SharePoint e nelle raccolte documenti. Tuttavia, le opzioni per eseguire questa operazione potrebbero richiedere fino a un'ora per essere visualizzate in Raccolta Impostazioni ed Elenco Impostazioni.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Elenchi e raccolte SharePoint IRM
<a name="__toc220831191"> </a>

Dopo l'aggiornamento delle impostazioni IRM, i proprietari dei siti possono proteggere con IRM SharePoint elenchi e raccolte documenti. Per ulteriori informazioni, vedere [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Quando i proprietari dei siti abilitano IRM per un elenco o una raccolta, possono proteggere qualsiasi tipo di file supportato in tale elenco o raccolta. Quando IRM è abilitato per una raccolta, rights management si applica a tutti i file in tale raccolta. Quando si abilita IRM per un elenco, rights management si applica solo ai file allegati alle voci di elenco, non alle voci di elenco effettive.
  
Quando gli utenti scaricano file in un elenco o una raccolta abilitata per IRM, i file vengono crittografati in modo che solo gli utenti autorizzati possano visualizzarli. Ogni file rights-managed contiene anche una licenza di rilascio che impone restrizioni alle persone che visualizzano il file. Le restrizioni tipiche includono la creazione di un file di sola lettura, la disabilitazione della copia del testo, l'impedimento del salvataggio di una copia locale e la stampa del file da parte degli utenti. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di rilascio all'interno del file rights-managed per applicare queste restrizioni. Questo è il modo in cui un file rights-managed mantiene la protezione anche dopo il download. Per abilitare IRM in un elenco o una raccolta, vedere [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Non è possibile creare o modificare documenti in una raccolta abilitata per IRM utilizzando Office in un browser. Al contrario, una persona alla volta può scaricare e modificare i file crittografati con IRM. Utilizzare l'archiviazione e l'estrazione per gestire la  *creazione*  condivisa o la creazione e modifica tra più utenti. 
  
Quando si scarica un file PDF da una raccolta protetta da IRM, Microsoft 365 crea un file PDF protetto. L'estensione del file non cambia, ma il file è protetto. Per visualizzare questo file, è necessario il visualizzatore di Azure Information Protection, il client Azure Information Protection completo o un'altra applicazione che supporti la visualizzazione di file PDF protetti. 
  
SharePoint Online supporta la crittografia dei seguenti tipi di file:
  
- PDF
    
- I formati di file 97-2003 per i programmi Microsoft Office seguenti: Word, Excel e PowerPoint
    
- I Office Open XML per i Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formato XPS (XML Paper Specification)
 
> [!NOTE]
> La protezione IRM non può essere applicata ai documenti protetti (come i file PDF firmati digitalmente) SharePoint necessario aprire il documento al caricamento. 

## <a name="next-steps"></a>Passaggi successivi
<a name="__toc220831191"> </a>

Dopo aver abilitato IRM per SharePoint Online, puoi iniziare ad applicare rights management a elenchi e raccolte. Per informazioni, vedere [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Il nuovo client di sincronizzazione OneDrive per Windows ora supporta la sincronizzazione delle raccolte documenti e dei percorsi di SharePoint OneDrive protetti da IRM (purché l'impostazione IRM per la raccolta non sia impostata per la scadenza dei diritti di accesso ai documenti). Per ulteriori informazioni o per iniziare a distribuire il nuovo client di sincronizzazione, vedere [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).
  
[Inizio pagina](set-up-irm-in-sp-admin-center.md)