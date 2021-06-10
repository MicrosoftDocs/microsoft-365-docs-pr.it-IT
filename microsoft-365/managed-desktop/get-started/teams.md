---
title: Microsoft Teams
description: Come Teams installato nei dispositivi e aggiornato in seguito
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920657"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) è [un'app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) di messaggistica per l'organizzazione che fornisce anche un'area di lavoro per la collaborazione e la comunicazione in tempo reale, le riunioni e la condivisione di file e app.

## <a name="initial-deployment"></a>Distribuzione iniziale

La maggior parte dei fornitori di hardware non include ancora Teams come parte delle immagini, quindi Microsoft Managed Desktop distribuisce Teams ai dispositivi usando Microsoft Intune. Tutti i dispositivi gestiti hanno installato [Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) pacchetto, assicurando che tutti gli utenti che a loro volta a Microsoft Teams siano pronti per l'uso. Al termine dell'installazione del pacchetto, Teams viene avviato automaticamente e viene aggiunto un collegamento al desktop.

### <a name="microsoft-intune-changes"></a>Microsoft Intune modifiche

Microsoft Managed Desktop due applicazioni all'organizzazione di Azure AD per Microsoft Teams. Vengono distribuiti ai client a 64 bit o a 32 bit in base alle esigenze del dispositivo:  

- Ambiente di lavoro moderno - Teams machine wide installer x64  
- Ambiente di lavoro moderno - Teams di installazione a livello di computer x32

## <a name="updates"></a>Aggiornamenti

Teams segue un percorso di aggiornamento separato da Microsoft 365 Apps for enterprise e il client desktop si aggiorna automaticamente. Teams verifica la disponibilità di aggiornamenti ogni poche ore, li scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.  

Il Teams non consente agli amministratori di controllare gli aggiornamenti, quindi Microsoft Managed Desktop il canale di aggiornamento automatico [standard.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Aggiornamento manuale Teams

I singoli utenti possono anche scaricare gli aggiornamenti **selezionando** Controlla aggiornamenti nel menu a discesa Profilo in alto a   destra  ****   dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

## <a name="delivery-optimization-of-updates"></a>Ottimizzazione recapito degli aggiornamenti

Ottimizzazione recapito per Teams aggiornamenti è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.