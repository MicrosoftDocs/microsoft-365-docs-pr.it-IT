---
title: Distribuire Microsoft 365 Lighthouse di base
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
description: Per i provider di servizi gestiti (MSP) che usano Microsoft 365 Lighthouse, scopri come distribuire le Microsoft 365 Lighthouse di base.
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409105"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Distribuire Microsoft 365 Lighthouse di base 

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md). Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse di base consentono di distribuire configurazioni tenant gestite standard per proteggere utenti, dispositivi e dati tenant. Esistono sei configurazioni di base predefinite standard con Microsoft 365 Lighthouse:

- Richiedi MFA per gli amministratori
- Richiedi MFA per gli utenti finali
- Blocca autenticazione legacy
- Configurare Registrazione dispositivi in Microsoft Endpoint Manager - Aggiunta ad Azure AD
- Configurare i criteri anti-virus defender per Windows dispositivi
- Configurare i criteri di conformità per Windows dispositivi

## <a name="before-you-begin"></a>Prima di iniziare

Assicurati che tu e i tenant dei clienti soddisfino i requisiti elencati in [Requisiti per Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="learn-more-about-the-default-baseline"></a>Ulteriori informazioni sulla previsione predefinita

Selezionare **Baselines** nel riquadro di spostamento sinistro per aprire la pagina Baselines. Vedrai che la linea di base predefinita è già stata aggiunta al gruppo tenant predefinito (tutti i tenant). Per visualizzare le configurazioni di base predefinite, selezionare **Visualizza** previsione per aprire la pagina Previsione predefinita. Le configurazioni sono elencate come passaggi di distribuzione. Selezionare uno dei passaggi di distribuzione per visualizzare i dettagli della distribuzione e l'impatto degli utenti.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Screenshot of the Default baseline page.>.":::

## <a name="deploy-a-baseline-configuration"></a>Distribuire una configurazione di base  

1. Nella pagina di spostamento sinistra selezionare **Tenant per** visualizzare un elenco dei tenant onboarded.

2. Selezionare il tenant in cui si desidera distribuire la configurazione di base.

3. Selezionare la **scheda Piano di** distribuzione per visualizzare tutti i passaggi di distribuzione dalla linea di base che sono stati aggiunti al piano di distribuzione del tenant.

4. Selezionare un passaggio di distribuzione per aprire la pagina del passaggio di distribuzione.

5. Selezionare **Applica** per applicare il passaggio di distribuzione selezionato al tenant. Se il passaggio di distribuzione indica "Questa azione richiede un passaggio manuale", assicurarsi di completare il passaggio manuale in modo che il passaggio di distribuzione venga applicato correttamente.

## <a name="related-content"></a>Contenuto correlato

[Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (articolo)\
[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)