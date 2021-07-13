---
title: Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse informazioni sull'utilizzo delle linee di base per distribuire configurazioni tenant standard.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409180"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard 

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md). Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse di base offrono un modo ripetibile e scalabile per valutare e gestire Microsoft 365 di sicurezza tra più tenant. Le linee di base consentono inoltre di monitorare i criteri di sicurezza di base e gli standard di conformità del tenant con configurazioni che consentono di proteggere utenti, dispositivi e dati.

Progettato per aiutare i partner a consentire ai clienti l'adozione della sicurezza al proprio ritmo, Microsoft 365 Lighthouse fornisce un set standard di parametri di base e configurazioni predefinite per Microsoft 365 servizi. Queste configurazioni di sicurezza consentono di misurare l'avanzamento Microsoft 365 sicurezza e conformità dei tenant.

È possibile visualizzare la previsione predefinita e i relativi passaggi di distribuzione dall'Microsoft 365 Lighthouse. Per applicare le linee di base a un tenant, selezionare **Tenant nel** riquadro di spostamento sinistro e quindi selezionare un tenant. Passare quindi alla scheda **Piani di distribuzione** e implementare la previsione desiderata.

## <a name="standard-baseline-security-templates"></a>Modelli di sicurezza di base standard

Microsoft 365 Lighthouse configurazioni di base standard per i carichi di lavoro di sicurezza sono progettate per consentire a tutti i tenant gestiti di raggiungere uno stato accettabile di conformità e copertura della sicurezza.

Le configurazioni di base nella tabella seguente sono standard con la Microsoft 365 Lighthouse predefinita.<br><br>

| Configurazione di base | Descrizione |
|--|--|
| Richiedi MFA per gli amministratori | Criteri di accesso condizionale solo report che richiedono l'autenticazione a più fattori per gli amministratori. È necessario per tutte le applicazioni cloud. |
| Richiedi MFA per gli utenti finali | Criteri di accesso condizionale solo report che richiedono l'autenticazione a più fattori per gli utenti. È necessario per tutte le applicazioni cloud. |
| Bloccare l'autenticazione legacy | Criteri di accesso condizionale solo report per bloccare l'autenticazione client legacy. |
| Registrare i dispositivi in Microsoft Endpoint Manager - Aggiunta ad Azure AD | Registrazione dei dispositivi per consentire ai dispositivi tenant di registrarsi Microsoft Endpoint Manager. Questa operazione viene eseguita configurando la registrazione automatica tra Azure Active Directory e Microsoft Endpoint Manager. |
| Configurazione dei criteri antivirus | Un profilo di configurazione dei dispositivi Windows dispositivi con impostazioni Antivirus Microsoft Defender preconfigurato. |
| Window 10 Compliance policy set up | Un Windows dei dispositivi con impostazioni preconfigurato per soddisfare i requisiti di conformità di base. |

## <a name="related-content"></a>Contenuto correlato

[Distribuire Microsoft 365 Lighthouse di base](m365-lighthouse-deploy-baselines.md) (articolo)\
[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)
