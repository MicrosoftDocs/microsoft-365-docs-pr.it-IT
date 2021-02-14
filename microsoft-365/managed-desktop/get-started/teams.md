---
title: Microsoft Teams
description: Modalità di installazione di Teams nei dispositivi e aggiornamento in seguito
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950940"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) è [un'app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) di messaggistica per l'organizzazione che offre anche un'area di lavoro per la collaborazione e la comunicazione in tempo reale, le riunioni e la condivisione di file e app.

## <a name="initial-deployment"></a>Distribuzione iniziale

La maggior parte dei fornitori di hardware non include ancora Teams come parte delle proprie immagini, quindi Microsoft Managed Desktop distribuisce Teams nei dispositivi tramite Microsoft Intune. In tutti i dispositivi gestiti è installato il pacchetto MSI di [Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) che garantisce che tutti gli utenti che a questo punto hanno Microsoft Teams pronto per l'uso. Al termine dell'installazione del pacchetto, Teams si avvia automaticamente e aggiunge un collegamento al desktop.

### <a name="microsoft-intune-changes"></a>Modifiche di Microsoft Intune

Microsoft Managed Desktop aggiunge due applicazioni all'organizzazione Azure AD per Microsoft Teams. Vengono distribuiti ai client a 64 bit o a 32 bit in base alle esigenze del dispositivo:  

- Ambiente di lavoro moderno - Teams Machine Wide Installer x64  
- Ambiente di lavoro moderno - Teams Machine Wide Installer x32

## <a name="updates"></a>Aggiornamenti

Teams segue un percorso di aggiornamento separato da Microsoft 365 Apps for enterprise e il client desktop si aggiorna automaticamente. Teams verifica la disponibilità di aggiornamenti ogni poche ore, li scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.  

Il gruppo di prodotti Teams non consente agli amministratori di controllare gli aggiornamenti, quindi Microsoft Managed Desktop usa il canale [di aggiornamento automatico standard.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Aggiornamento manuale di Teams

I singoli utenti possono anche scaricare gli aggiornamenti selezionando Controlla **aggiornamenti** nel menu a discesa Profilo nell'angolo in alto   a destra  ****   dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

## <a name="delivery-optimization-of-updates"></a>Ottimizzazione del recapito degli aggiornamenti

Ottimizzazione recapito per gli aggiornamenti di Teams è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti. 