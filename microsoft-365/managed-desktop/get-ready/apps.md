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

Microsoft include alcune app chiave insieme alla licenza di Microsoft 365 E3 o E5 necessaria per partecipare a Microsoft Managed Desktop. Tuttavia, anche se forniamo queste app, hai ancora alcune responsabilità e azioni da completare.

Puoi anche distribuire altre app non Microsoft agli utenti per il self-service tramite il portale aziendale o un'installazione in background necessaria, il tutto usando la pipeline di distribuzione di Microsoft Intune. 

## <a name="apps-provided-by-microsoft"></a>App fornite da Microsoft

Con la licenza Microsoft Managed Desktop sono incluse le versioni a 64 bit delle app in Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote). Per impostazione predefinita, non sono incluse  le versioni a scelta di Microsoft Project e Visio, ma è possibile richiederle di essere aggiunte. Per ulteriori informazioni su queste app, vedere [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Cosa fa Microsoft per supportare le app fornite

Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app di Microsoft 365 Apps for enterprise incluse. Le versioni di Microsoft Project e  Visio a livello di clic non sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà gruppi di distribuzione che consentiranno all'amministratore IT di gestire le licenze e distribuire tali applicazioni in modo appropriato per l'organizzazione. Microsoft supporterà gli utenti di queste applicazioni tramite i canali di supporto di Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Cosa è necessario fare per supportare le app fornite

Esistono ancora alcune operazioni da eseguire con queste app:

- **Assegnare** licenze: l'utente è responsabile dell'ottenimento e dell'assegnazione delle licenze appropriate agli utenti per Microsoft 365 Apps for enterprise.
- **Aggiungere utenti ai gruppi di** sicurezza: se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione appropriati. Gli amministratori IT sono inoltre responsabili del recupero delle licenze da tali utenti se lasciano l'azienda.
- Distribuire i componenti aggiuntivi di **Microsoft 365:** se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 Apps for enterprise, distribuirli centralmente come qualsiasi altra app di Windows 32. 

## <a name="apps-you-provide"></a>App fornite

Probabilmente hai altre app necessarie per le tue operazioni aziendali. Queste app possono essere distribuite solo nei dispositivi Microsoft Managed Desktop tramite la pipeline di distribuzione di Microsoft Intune. Per altre informazioni sulla distribuzione delle applicazioni, segui i passaggi descritti in [Deploy apps to Microsoft Managed Desktop devices.](../get-started/deploy-apps.md)

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Preparazione delle proprie app per l'inclusione in Microsoft Managed Desktop
Controlla le app, controllando:

- Nessuna delle app è proibita o ha un comportamento limitato, come descritto in Requisiti per le app desktop gestite [da Microsoft.](../service-description/mmd-app-requirements.md)
- Le app devono essere pronte per la gestione da Parte di Microsoft Intune. Per altre informazioni su questo argomento, vedi Distribuzione di app di [Windows 10 con Microsoft Intune](/intune/apps-windows-10-app-deploy) e Aggiungere app a Microsoft [Intune.](/intune/apps-add)
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
