---
title: Reindirizzamento degli account da Microsoft Defender per Office 365 al nuovo Centro sicurezza Microsoft 365
description: Come reindirizzare da Defender per Office 365 al Centro sicurezza Microsoft 365.
keywords: Centro sicurezza Microsoft 365, Introduzione al Centro sicurezza Microsoft 365, reindirizzamento del centro sicurezza
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064642"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Reindirizzamento degli account da Microsoft Defender per Office 365 al Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender
- Defender per Office 365

In questo articolo viene illustrato come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dall'ex Centro sicurezza e conformità Microsoft (protection.office.com o securitycenter.microsoft.com) al Centro sicurezza Microsoft 365 (security.microsoft.com).

>[!NOTE]
> La funzionalità di reindirizzamento del portale è disponibile solo per i clienti di Office 365 E5 e Microsoft Defender per Office P2

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità correlate alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati al Centro sicurezza Microsoft 365 ( https://security.microsoft.com) .  

Altre informazioni sulle modifiche: Microsoft Defender per Office 365 nel Centro sicurezza [Microsoft 365.](microsoft-365-security-center-mdo.md)

Con il reindirizzamento automatico attivato, gli utenti verranno instradati al Centro sicurezza Microsoft 365 quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365.

Queste includono funzionalità nella sezione Gestione delle minacce e nel dashboard e nei report di Gestione delle minacce. Gli elementi nel Centro sicurezza e conformità di Office 365 non correlati alla sicurezza non vengono reindirizzati al Centro sicurezza Microsoft 365.

Gli elementi correlati alla conformità sono disponibili nel Centro conformità Microsoft 365 e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia di amministrazione di Exchange.

Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento. Gli avvisi di sicurezza di Office 365 vengono visualizzati sia nel Centro sicurezza Microsoft 365 che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare il routing degli account al Centro sicurezza Microsoft 365 all'security.microsoft.com:

1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.
2. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365.
3. Passare a **Impostazioni**  >  **E-mail &**  >  **reindirizzamento portale di collaborazione**.  
4. Attiva l'impostazione Reindirizzamento **automatico**.
5. Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale del centro sicurezza Microsoft 365.

> [!NOTE]
> Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminato la sessione corrente e aver effettuato di nuovo l'accesso.

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?
Se qualcosa non funziona per te o se c'è qualcosa che non è possibile completare tramite il portale del centro sicurezza Microsoft 365, vogliamo sentirlo usando l'opzione di feedback del portale. Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattare il tuo amico pm direttamente tramite l'anteprima privata o contattarci tramite il modulo Invia feedback.

Per ripristinare il portale precedente:

1. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare a **Impostazioni**  >  **Endpoint**  >  **Reindirizzamento**  >  **portale generale**.  

3. Attivare o disattivare l'impostazione Reindirizzamento **automatico**.

4. Fai **clic su** & feedback quando richiesto.

Questa impostazione può essere nuovamente abilitata in qualsiasi momento.

Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Informazioni correlate
- [Panoramica del Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografica XDR e SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Il nuovo defender](https://afrait.com/blog/the-new-defender/) 
- [Informazioni su Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portali di sicurezza Microsoft e centri di amministrazione](portals.md)