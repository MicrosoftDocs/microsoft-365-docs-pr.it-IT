---
title: Usare i criteri di prevenzione della perdita di dati per le app cloud non Microsoft (anteprima)
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
description: Informazioni su come usare i criteri dlp per le app cloud non Microsoft.
ms.openlocfilehash: 3c3c687bd1362182d35891ed1ebbfae12416d5d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226840"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Usare i criteri di prevenzione della perdita dei dati per le app cloud non Microsoft (anteprima)

I criteri di prevenzione della perdita dei dati (DLP) per le app cloud non Microsoft fanno parte della famiglia Microsoft 365 di funzionalità DLP. usando queste funzionalità, è possibile individuare e proteggere gli elementi sensibili tra Microsoft 365 servizi. Per ulteriori informazioni su tutte le offerte DLP di Microsoft, vedere [Informazioni sulla prevenzione della perdita dei dati.](dlp-learn-about-dlp.md)

Puoi usare i criteri DLP per le app cloud non Microsoft per monitorare e rilevare quando gli elementi sensibili vengono usati e condivisi tramite app cloud non Microsoft. L'uso di questi criteri offre la visibilità e il controllo necessari per garantire che siano utilizzati e protetti correttamente e consente di evitare comportamenti rischiosi che potrebbero comprometterli.

## <a name="before-you-begin"></a>Informazioni preliminari

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/abbonamenti

Prima di iniziare a usare i criteri DLP per le app cloud non Microsoft, confermare la sottoscrizione Microsoft 365 [ed](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) eventuali componenti aggiuntivi. Per accedere a questa funzionalità e utilizzarla, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi:

- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Preparare l'Cloud App Security locale

I criteri DLP per le app cloud non Microsoft usano Cloud App Security DLP. Per usarlo, è consigliabile preparare l'Cloud App Security locale. Per istruzioni, vedi [Impostare azioni di visibilità, protezione e governance istantanee per le tue app.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Connessione un'app cloud non Microsoft

Per usare i criteri DLP per una specifica app cloud non Microsoft, l'app deve essere connessa a Cloud App Security. Per informazioni, vedere:

- [Connessione Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Connessione Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connessione G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Connessione Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Connessione Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Dopo aver connesso le app cloud a Cloud App Security, è possibile creare Microsoft 365 criteri DLP per loro.

> [!NOTE]
> È anche possibile usare le Microsoft Cloud App Security per creare criteri DLP per le app cloud Microsoft. Tuttavia, è consigliabile usare Microsoft 365 per creare e gestire i criteri DLP per le app cloud Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Creare un criterio DLP in un'app cloud non Microsoft

Quando si seleziona una posizione per il criterio DLP, attivare la posizione **Microsoft Cloud App Security** locale.

- Per selezionare un'app o un'istanza specifica, seleziona **Scegli istanza.**
- Se non si seleziona un'istanza, il criterio usa tutte le app connesse nel tenant Microsoft Cloud App Security tenant.

   ![Percorsi per l'applicazione del criterio](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Puoi scegliere diverse azioni per ogni app cloud non Microsoft supportata. Per ogni app, esistono diverse azioni possibili (dipende dall'API dell'app cloud).

![Creare una regola](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Quando si crea una regola nel criterio DLP, è possibile selezionare un'azione per le app cloud non Microsoft. Per limitare le app di terze parti, seleziona **Limita app di terze parti.**

![Limitare le app di terze parti](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [NOTA] I criteri DLP applicati alle app non Microsoft usano Microsoft Cloud App Security. Quando viene creato il criterio DLP per un'app non Microsoft, lo stesso criterio verrà creato automaticamente in Microsoft Cloud App Security.

Per informazioni sulla creazione e la configurazione dei criteri DLP, vedere [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).

## <a name="see-also"></a>Vedere anche

- [Creare test e ottimizzare un criterio DLP](./create-test-tune-dlp-policy.md)
- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](./get-started-with-the-default-dlp-policy.md)
- [Creare un criterio di prevenzione della perdita dei dati da un modello](./create-a-dlp-policy-from-a-template.md)
