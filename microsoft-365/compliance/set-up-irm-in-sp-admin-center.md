---
title: Set up Information Rights Management (IRM) in SharePoint admin center
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
description: Informazioni su come utilizzare IRM di SharePoint Online tramite Microsoft Azure Active Directory Rights Management Services (RMS) per proteggere gli elenchi e le raccolte documenti di SharePoint.
ms.openlocfilehash: 3705c08b64ffbf719dbce91396c86976db14fea0
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610623"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

## <a name="introduction"></a>Introduzione

All'interno di SharePoint Online, la protezione IRM viene applicata ai file a livello di elenco e raccolta. Prima che l'organizzazione possa utilizzare la protezione IRM, è necessario innanzitutto impostare Rights Management. IRM si basa sul servizio Azure Rights Management da Azure Information Protection per crittografare e assegnare restrizioni di utilizzo. Alcuni piani di Office 365 includono Azure Rights Management, ma non tutti. Per ulteriori informazioni, vedere in [che modo le applicazioni e i servizi di Office supportano Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Abilitare il servizio IRM utilizzando l'interfaccia di amministrazione di SharePoint

Prima che l'organizzazione possa proteggere con IRM gli elenchi e le raccolte di SharePoint, è necessario prima attivare il servizio Rights Management per l'organizzazione. Per ulteriori informazioni, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). È necessario utilizzare un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365 per abilitare il servizio Rights Management. In caso contrario, non sarà possibile utilizzare le funzionalità IRM con SharePoint Online.
  
Dopo aver attivato il servizio Rights Management, accedere all'interfaccia di amministrazione di SharePoint per attivare IRM.
  
1. Accedere a Office 365 come amministratore globale o amministratore di SharePoint.
    
2. Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) nell'angolo in alto a sinistra e scegliere **Amministratore** per aprire l'interfaccia di amministrazione di Microsoft 365. Se il riquadro di amministrazione non è visibile, non si dispone delle autorizzazioni di amministratore di Office 365 all'interno dell'organizzazione.) 
    
3. Nel riquadro sinistro scegliere interfaccia di **Amministrazione** \> di **SharePoint**.
    
4. Nel riquadro a sinistra, scegliere **Impostazioni**, quindi **pagina impostazioni classiche**.
    
5. Nella sezione **Information Rights Management (IRM)** scegliere **utilizza il servizio IRM specificato nella configurazione**, quindi scegliere **Aggiorna impostazioni IRM**. Dopo aver eseguito l'aggiornamento delle impostazioni di IRM, gli utenti dell'organizzazione possono iniziare a utilizzare IRM negli elenchi di SharePoint e nelle raccolte documenti. Tuttavia, le opzioni per eseguire questa operazione possono richiedere fino a un'ora per essere visualizzate nelle impostazioni della raccolta e nelle impostazioni degli elenchi.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Abilitare gli elenchi e le raccolte documenti di SharePoint per IRM
<a name="__toc220831191"> </a>

Dopo aver eseguito l'aggiornamento delle impostazioni di IRM, i proprietari dei siti possono proteggere con IRM gli elenchi e le raccolte documenti di SharePoint. Per ulteriori informazioni, vedere [Applicare Information Rights Management a un elenco o una raccolta](apply-irm-to-a-list-or-library.md).
  
Quando i proprietari dei siti attivano IRM per un elenco o una raccolta, possono proteggere tutti i tipi di file supportati nell'elenco o nella raccolta. Quando IRM è abilitato per una raccolta, Rights Management si applica a tutti i file della raccolta. Quando si abilita IRM per un elenco, Rights Management si applica solo ai file associati a voci di elenco e non alle voci di elenco effettive.
  
Quando gli utenti scaricano i file in un elenco o in una raccolta abilitata per IRM, i file vengono crittografati in modo che solo le persone autorizzate possano visualizzarle. Ogni file con diritti gestiti contiene anche una licenza di pubblicazione che impone restrizioni agli utenti che visualizzano il file. Le restrizioni tipiche includono l'esecuzione di un file di sola lettura, la disattivazione della copia del testo, impedire agli utenti di salvare una copia locale e impedire agli utenti di stampare il file. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di pubblicazione all'interno del file Rights-Managed per applicare queste restrizioni. Questo è il modo in cui un file con diritti gestiti mantiene la propria protezione anche dopo il download. Per abilitare IRM su un elenco o una raccolta, vedere [Applicare Information Rights Management a un elenco o una raccolta](apply-irm-to-a-list-or-library.md).
  
Non è possibile creare o modificare documenti in una raccolta abilitata per IRM utilizzando Office in un browser. Invece, una persona alla volta può scaricare e modificare i file crittografati con IRM. Utilizzare l'archiviazione e l'estrazione per gestire la creazione *condivisa* o la creazione di una modifica in più utenti. 
  
Quando si scarica un file PDF da una raccolta protetta da IRM, Office 365 crea un file PDF protetto. L'estensione del file non cambia, ma il file è protetto. Per visualizzare questo file, è necessario Azure Information Protection Viewer, il client di Azure Information Protection completo o un'altra applicazione che supporta la visualizzazione di file PDF protetti. 
  
SharePoint Online supporta la crittografia dei seguenti tipi di file:
  
- PDF
    
- Formati di file di 97-2003 per le seguenti applicazioni di Microsoft Office: Word, Excel e PowerPoint
    
- Formati di Office Open XML per le seguenti applicazioni di Microsoft Office: Word, Excel e PowerPoint
    
- Formato XML Paper Specification (XPS)
 
> [!NOTE]
> La protezione IRM non può essere applicata ai documenti protetti (come i file PDF con firma digitale), in quanto SharePoint deve aprire il documento al caricamento. 

## <a name="next-steps"></a>Passaggi successivi
<a name="__toc220831191"> </a>

Dopo aver abilitato IRM per SharePoint Online, è possibile iniziare a applicare Rights Management agli elenchi e alle raccolte. Per informazioni, vedere [Applicare Information Rights Management a un elenco o una raccolta](apply-irm-to-a-list-or-library.md).
  
Il nuovo client di sincronizzazione di OneDrive per Windows supporta la sincronizzazione delle raccolte documenti di SharePoint e delle posizioni OneDrive protette da IRM (purché l'impostazione IRM per la raccolta non sia impostata sulla scadenza dei diritti di accesso ai documenti). Per ulteriori informazioni o per iniziare a distribuire il nuovo client di sincronizzazione, vedere [distribuire il nuovo client di sincronizzazione di OneDrive per Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Inizio pagina](#introduction)  
