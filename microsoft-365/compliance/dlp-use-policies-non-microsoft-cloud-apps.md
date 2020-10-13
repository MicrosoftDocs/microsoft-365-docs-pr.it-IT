---
title: Utilizzare i criteri di prevenzione della perdita dei dati per le app Cloud non Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare i criteri DLP per le app Cloud non Microsoft.
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422758"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Utilizzare i criteri di prevenzione della perdita dei dati per le app Cloud non Microsoft (anteprima)

I criteri di prevenzione della perdita di dati (DLP, Data Loss Prevention) per le app Cloud non Microsoft fanno parte della famiglia di caratteristiche Microsoft 365 DLP. utilizzando queste funzionalità, è possibile individuare e proteggere gli elementi sensibili nei servizi Microsoft 365. Per ulteriori informazioni su tutte le offerte DLP Microsoft, vedere [Overview of Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).

È possibile utilizzare i criteri DLP per le app Cloud non Microsoft per monitorare e rilevare quando gli elementi sensibili vengono utilizzati e condivisi tramite le app Cloud non Microsoft. L'utilizzo di questi criteri garantisce la visibilità e il controllo necessari per garantire la corretta utilizzazione e protezione e consente di evitare comportamenti rischiosi che potrebbero comprometterli.

## <a name="before-you-begin"></a>Informazioni preliminari

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/abbonamenti

Prima di iniziare a utilizzare i criteri DLP per le app Cloud non Microsoft, confermare la [sottoscrizione microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi. Per accedere e utilizzare questa funzionalità, è necessario disporre di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Preparare l'ambiente di protezione delle app Cloud

I criteri DLP per le app Cloud non Microsoft utilizzano le funzionalità di protezione DLP di cloud app. Per utilizzarlo, è necessario preparare l'ambiente di protezione delle app cloud. Per istruzioni, vedere [set isntant Visibility, Protection, and Governance actions for your Apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).

### <a name="connect-a-non-microsoft-cloud-app"></a>Connettere un'app Cloud non Microsoft

Per utilizzare i criteri DLP per un'app Cloud non Microsoft specifica, è necessario che l'app sia connessa a cloud app Security. Per informazioni, vedere:

- [Casella Connetti](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Connettere Dropbox](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connettere G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Connettere Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Connettere Cisco WebEx](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Dopo aver collegato le app Cloud alla sicurezza delle app Cloud, è possibile creare i criteri di Microsoft 365 DLP.

>[!NOTE]
>È anche possibile usare Microsoft cloud app Security per creare criteri DLP per le app cloud di Microsoft. Tuttavia, si consiglia di utilizzare Microsoft 365 per creare e gestire i criteri DLP per le app cloud di Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Creare un criterio DLP in un'app Cloud non Microsoft

Quando si seleziona un percorso per il criterio DLP, accendere il percorso di **sicurezza di Microsoft cloud app** .

- Per selezionare un'applicazione o un'istanza specifica, selezionare **Scegli istanza**.
- Se non si seleziona un'istanza, il criterio utilizza tutte le app connesse nel tenant di sicurezza di Microsoft cloud app.

   ![Posizioni in cui applicare il criterio](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Casella-Stati Uniti e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

È possibile scegliere varie azioni per ogni app Cloud non Microsoft supportata. Per ogni app, esistono diverse azioni possibili (dipende dall'API delle app Cloud).

![Crea regola](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Quando si crea una regola nei criteri DLP, è possibile selezionare un'azione per le app Cloud non Microsoft. Per limitare le app di terze parti, seleziona **Impedisci app**di terze parti.

![Limitare le app di terze parti](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Per informazioni sulla creazione e sulla configurazione dei criteri DLP, vedere [create test and Tune a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).

## <a name="see-also"></a>Vedere anche

- [Creare test e ottimizzare un criterio DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Creare un criterio di prevenzione della perdita dei dati da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
