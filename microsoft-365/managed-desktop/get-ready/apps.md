---
title: App in Microsoft Managed Desktop
description: Spiega come vengono gestite le app, incluso come creare un pacchetto, distribuirle e supportarle.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028945"
---
# <a name="apps-in-microsoft-managed-desktop"></a>App in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>App in genere

Microsoft include alcune app chiave insieme alla licenza Microsoft 365 E3 o E5 necessaria per partecipare Microsoft Managed Desktop. Tuttavia, anche se forniamo queste app, hai ancora alcune responsabilità e azioni da completare.

Puoi anche distribuire altre app non Microsoft agli utenti per il self-service tramite il Portale aziendale o un'installazione in background necessaria, il tutto usando la pipeline di distribuzione di Microsoft Intune. 

## <a name="apps-provided-by-microsoft"></a>App fornite da Microsoft

Nella licenza Microsoft Managed Desktop sono incluse le versioni a 64 bit delle app in Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote). Le versioni A livello di Microsoft Project e Visio non  sono incluse per impostazione predefinita, ma è possibile richiederle di essere aggiunte. Per altre informazioni su queste app, vedi [Installare Microsoft Project o Microsoft Visio su Microsoft Managed Desktop dispositivi](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Cosa fa Microsoft per supportare le app fornite

Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app Microsoft 365 Apps for enterprise incluse. Le versioni di Microsoft Project e Visio a clic non  sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuire queste applicazioni in modo appropriato per l'organizzazione. Microsoft supporterà gli utenti di queste applicazioni tramite i canali Microsoft Managed Desktop supporto tecnico.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Cosa è necessario fare per supportare le app fornite

Esistono ancora alcune operazioni da eseguire con queste app:

- **Assegnare licenze:** l'utente è responsabile dell'ottenimento e dell'assegnazione delle licenze appropriate agli utenti per Microsoft 365 Apps for enterprise.
- **Aggiungere utenti ai gruppi** di sicurezza: se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione appropriati. Gli amministratori IT sono inoltre responsabili del recupero delle licenze da tali utenti se lasciano l'azienda.
- **Distribuire Microsoft 365** componenti aggiuntivi: se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 Apps for enterprise, distribuirli centralmente come qualsiasi altra app Windows 32. 

## <a name="apps-you-provide"></a>App fornite

Probabilmente hai altre app necessarie per le tue operazioni aziendali. Queste app possono essere distribuite solo Microsoft Managed Desktop dispositivi usando Microsoft Intune pipeline di distribuzione di Microsoft Intune. Per altre informazioni sulla distribuzione delle applicazioni, segui i passaggi descritti in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparazione delle tue app per l'inclusione in Microsoft Managed Desktop
Controlla le app, controllando:

- Nessuna delle app è proibita o ha un comportamento limitato, come descritto in [Microsoft Managed Desktop app.](../service-description/mmd-app-requirements.md)
- Le app devono essere pronte per la gestione Microsoft Intune. Per altre informazioni su questo argomento, vedi [distribuzione](/intune/apps-windows-10-app-deploy) Windows 10 app usando Microsoft Intune e Aggiungi app [a Microsoft Intune](/intune/apps-add).
- Altri requisiti di pre-creazione del pacchetto, ad esempio la fornitura di codici di licenza, il contratto con le condizioni di licenza e la pre-impostazione delle connessioni server.

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md) (questo articolo)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
