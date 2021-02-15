---
title: Usare i criteri di prevenzione della perdita dei dati per le app cloud non Microsoft (anteprima)
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
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649657"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Usare i criteri di prevenzione della perdita dei dati per le app cloud non Microsoft (anteprima)

I criteri di prevenzione della perdita dei dati (DLP) per le app cloud non Microsoft fanno parte della famiglia di funzionalità DLP di Microsoft 365; Usando queste funzionalità, è possibile individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365. Per ulteriori informazioni su tutte le offerte dlp di Microsoft, vedere [Panoramica della prevenzione della perdita dei dati.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)

È possibile utilizzare i criteri DLP per le app cloud non Microsoft per monitorare e rilevare quando gli elementi sensibili vengono utilizzati e condivisi tramite app cloud non Microsoft. L'uso di questi criteri offre la visibilità e il controllo necessari per garantire che vengano utilizzati e protetti correttamente e consente di evitare comportamenti rischiosi che potrebbero comprometterli.

## <a name="before-you-begin"></a>Informazioni preliminari

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/abbonamenti

Prima di iniziare a usare i criteri DLP per le app cloud non Microsoft, confermare l'abbonamento a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e tutti i componenti aggiuntivi. Per accedere a questa funzionalità e utilizzarla, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi:

- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Preparare l'ambiente Cloud App Security

I criteri DLP per le app cloud non Microsoft utilizzano le funzionalità DLP di Cloud App Security. Per usarlo, è necessario preparare l'ambiente Cloud App Security. Per istruzioni, vedi [Impostare azioni immediate di visibilità, protezione e governance per le tue app.](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Connettere un'app cloud non Microsoft

Per usare i criteri DLP per un'app cloud non Microsoft specifica, l'app deve essere connessa a Cloud App Security. Per informazioni, vedere:

- [Connect Box](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Connettere Dropbox](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connettere G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Connettere Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Connettere Cisco Webex](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Dopo aver connesso le app cloud a Cloud App Security, è possibile creare criteri DLP di Microsoft 365 per loro.

>[!NOTE]
>È anche possibile usare Microsoft Cloud App Security per creare criteri DLP per le app cloud Microsoft. Tuttavia, è consigliabile usare Microsoft 365 per creare e gestire i criteri DLP per le app cloud Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Creare un criterio DLP in un'app cloud non Microsoft

Quando si seleziona un percorso per il criterio DLP, attivare il percorso **di Microsoft Cloud App Security.**

- Per selezionare un'app o un'istanza specifica, selezionare **Scegli istanza.**
- Se non si seleziona un'istanza, il criterio usa tutte le app connesse nel tenant di Microsoft Cloud App Security.

   ![Percorsi in cui applicare il criterio](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Puoi scegliere varie azioni per ogni app cloud non Microsoft supportata. Per ogni app, esistono diverse azioni possibili (dipende dall'API dell'app cloud).

![Creare una regola](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Quando si crea una regola nel criterio DLP, è possibile selezionare un'azione per le app cloud non Microsoft. Per limitare le app di terze parti, selezionare **Limita app di terze parti.**

![Limitare le app di terze parti](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Per informazioni sulla creazione e la configurazione di criteri DLP, vedere [Creare test e ottimizzare un criterio DLP.](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)

## <a name="see-also"></a>Vedere anche

- [Creare test e ottimizzare un criterio DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Creare un criterio di prevenzione della perdita dei dati da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
