---
title: Reindirizzamento degli account da Microsoft Defender per Office 365 al nuovo centro sicurezza Microsoft 365 sicurezza
description: Come reindirizzare da Defender per Office 365 al centro sicurezza Microsoft 365 sicurezza.
keywords: Microsoft 365 centro sicurezza, Guida introduttiva al centro sicurezza Microsoft 365, reindirizzamento del centro sicurezza
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
ms.openlocfilehash: 2a4b122b3ef3a1ddaf61d8f9373bec3e721db177
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651381"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Reindirizzamento degli account da Microsoft Defender per Office 365 al centro sicurezza Microsoft 365 sicurezza

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender
- Defender per Office 365

In questo articolo viene illustrato come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dall'ex Centro sicurezza e conformità Microsoft (protection.office.com o securitycenter.microsoft.com) al Centro sicurezza Microsoft 365 (security.microsoft.com).

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità correlate alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati al Centro sicurezza Microsoft 365 ( https://security.microsoft.com) .  

Altre informazioni sulle modifiche: [Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365 sicurezza](microsoft-365-security-center-mdo.md).

Con il reindirizzamento automatico attivato, gli utenti verranno instradati Microsoft 365 centro sicurezza quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365.

Queste includono funzionalità nella sezione Gestione delle minacce e nel dashboard e nei report di Gestione delle minacce. Gli elementi nel Office 365 sicurezza e conformità non correlati alla sicurezza non vengono reindirizzati al Centro sicurezza Microsoft 365 sicurezza.

Gli elementi correlati alla conformità sono disponibili nel Centro Microsoft 365 conformità e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia Exchange di amministrazione.

Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento. Office 365 avvisi di sicurezza vengono visualizzati sia nel Centro sicurezza Microsoft 365 che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare l'instradamento degli account al centro sicurezza Microsoft 365 in security.microsoft.com:

1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.
2. [Accedi al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 sicurezza.
3. Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.  
4. Attiva l'impostazione Reindirizzamento **automatico**.
5. Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale Microsoft 365 centro sicurezza.

> [!NOTE]
> Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?
Se qualcosa non funziona per te o se c'è qualcosa che non puoi completare tramite il portale del centro sicurezza Microsoft 365, vogliamo sentirlo usando l'opzione di feedback del portale. Se si sono verificati problemi con il reindirizzamento, contattaci.

Per ripristinare il portale precedente:

1. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare **a** Impostazioni  >  **e-mail & reindirizzamento del** portale  >  **di collaborazione**.   

3. Attivare o disattivare l'impostazione Reindirizzamento **automatico**.

4. Fai **clic su** & feedback quando richiesto.

Questa impostazione può essere nuovamente abilitata in qualsiasi momento.

Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Informazioni correlate
- [Panoramica del Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 sicurezza](microsoft-365-security-center-mde.md)
- [Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografica XDR e SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Il nuovo defender](https://afrait.com/blog/the-new-defender/) 
- [Informazioni su Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portali di sicurezza Microsoft e centri di amministrazione](portals.md)
