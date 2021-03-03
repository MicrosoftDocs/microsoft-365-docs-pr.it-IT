---
title: Reindirizzamento degli account da Microsoft Defender per Office 365 al nuovo Centro sicurezza Microsoft 365
description: Come reindirizzare da Defender per Office 365 al Centro sicurezza Microsoft 365.
keywords: Centro sicurezza Microsoft 365, Guida introduttiva al Centro sicurezza Microsoft 365, reindirizzamento del Centro sicurezza
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416795"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Reindirizzamento degli account da Microsoft Defender per Office 365 al Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender
- Defender per Office 365

Questo articolo spiega come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dal precedente Centro sicurezza e conformità (protection.office.com o securitycenter.microsoft.com) al Centro sicurezza Microsoft 365 (security.microsoft.com).

>[!NOTE]
> La funzionalità di reindirizzamento del portale è disponibile solo per i clienti di Office 365 E5 e Microsoft Defender per Office P2

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato e attivo il reindirizzamento automatico, gli utenti che accedono alle funzionalità relative alla sicurezza in Office 365 Security and Compliance (protection.office.com), verranno automaticamente instradati al Centro sicurezza Microsoft 365 ( https://security.microsoft.com) .  

Ulteriori informazioni sulle modifiche: Microsoft Defender per Office 365 nel Centro sicurezza [Microsoft 365.](microsoft-365-security-center-mdo.md)

Con il reindirizzamento automatico attivato, gli utenti verranno instradati al Centro sicurezza Microsoft 365 quando usano le funzionalità di sicurezza nel Centro sicurezza e conformità di Office 365.

Queste includono funzionalità nella sezione Gestione delle minacce, nel dashboard e nei report di Gestione delle minacce. Gli elementi nel Centro sicurezza e conformità di Office 365 non correlati alla sicurezza non vengono reindirizzati al Centro sicurezza Microsoft 365.

Gli elementi correlati alla conformità sono disponibili nel Centro conformità Microsoft 365 e gli elementi correlati al flusso di posta sono disponibili nell'interfaccia di amministrazione di Exchange.

Tutte le altre funzionalità, correlate alla conformità o che servono entrambe, non sono interessate dal reindirizzamento. Gli avvisi di sicurezza di Office 365 vengono visualizzati sia nel Centro sicurezza Microsoft 365 che nel Centro sicurezza e conformità di Office 365, senza reindirizzamento.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare il routing degli account al Centro sicurezza Microsoft 365 all'indirizzo security.microsoft.com:

1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.
2. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365.
3. Passare a **Impostazioni posta** elettronica  >  **& reindirizzamento del** portale di  >  **collaborazione.**  
4. Attiva l'impostazione reindirizzamento **automatico.**
5. Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale del Centro sicurezza Microsoft 365.

> [!NOTE]
> Dopo aver abilitato il reindirizzamento, gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare all'uso del portale precedente?
Se qualcosa non funziona per l'utente o se c'è qualcosa che non è possibile completare tramite il portale del Centro sicurezza Microsoft 365, vogliamo ricevere informazioni usando l'opzione di feedback del portale. Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattare il tuo amico pm direttamente tramite l'anteprima privata o contattarci tramite il modulo invia feedback.

Per ripristinare il portale precedente:

1. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare a **Impostazioni**  >  **Endpoint**  >  **reindirizzamento**  >  **portale generale.**  

3. Attivare o disattivare l'impostazione reindirizzamento **automatico.**

4. Fai **clic su** & condividi feedback quando richiesto.

Questa impostazione può essere ri abilitata in qualsiasi momento.

Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Informazioni correlate
- [Panoramica del Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografica XDR e SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Il nuovo defender](https://afrait.com/blog/the-new-defender/) 
- [Informazioni su Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portali di sicurezza Microsoft e centri di amministrazione](portals.md)