---
title: Reindirizzamento degli account Office 365 Centro sicurezza e conformità al nuovo Microsoft 365 Defender
description: Come reindirizzare da Defender per Office 365 a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Guida introduttiva a Microsoft 365 Defender, reindirizzamento del centro sicurezza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842520"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Reindirizzamento degli account da Office 365 Centro sicurezza e conformità a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender
- Defender per Office 365

In questo articolo viene illustrato come instradare gli account a Microsoft 365 Office 365 Defender abilitando il reindirizzamento automatico dal centro sicurezza e conformità (protection.office.com) precedente a Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità correlate alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati a Microsoft 365 Defender ( https://security.microsoft.com) .  

Altre informazioni sulle modifiche: [Microsoft Defender per Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

Con il reindirizzamento automatico attivato, gli utenti verranno instradati a Microsoft 365 Defender quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365 sicurezza.

Queste includono funzionalità nella sezione Gestione delle minacce e nel dashboard e nei report di Gestione delle minacce. Gli elementi nel Office 365 sicurezza e conformità non correlati alla sicurezza non vengono reindirizzati a Microsoft 365 Defender.

Gli elementi correlati alla conformità sono disponibili nel Centro Microsoft 365 conformità e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia Exchange di amministrazione.

Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento. Office 365 avvisi di sicurezza vengono visualizzati sia in Microsoft 365 Defender che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare il routing degli account Microsoft 365 Defender in security.microsoft.com:

1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.
2. [Accedi a](https://security.microsoft.com/) Microsoft 365 Defender.
3. Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.  
4. Attiva l'impostazione Reindirizzamento **automatico**.
5. Fai **clic su** Abilita per applicare il reindirizzamento automatico a Microsoft 365 Defender.

> [!NOTE]
> Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione è applicata non verranno espulsi dalla sessione e verranno instradati a Microsoft 365 Defender solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?
Se qualcosa non funziona per te o se c'è qualcosa che non puoi completare tramite Microsoft 365 Defender, vogliamo sentirlo usando l'opzione di feedback del portale. Se si sono verificati problemi con il reindirizzamento, contattaci.

Per ripristinare il portale precedente:

1. [Accedere a](https://security.microsoft.com/) Microsoft 365 Defender come amministratore globale o usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.   

3. Attivare o disattivare l'impostazione Reindirizzamento **automatico**.

4. Fai **clic su** & feedback quando richiesto.

Questa impostazione può essere nuovamente abilitata in qualsiasi momento.

Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, ovvero securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Informazioni correlate
- [Microsoft 365 Panoramica di Defender](overview-security-center.md)
- [Microsoft Defender per Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografica XDR e SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Il nuovo defender](https://afrait.com/blog/the-new-defender/) 
- [Informazioni su Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portali di sicurezza Microsoft e centri di amministrazione](portals.md)
