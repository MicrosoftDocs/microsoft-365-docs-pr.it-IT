---
title: Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365
description: Come reindirizzare account e sessioni da Defender for Endpoint al Centro sicurezza Microsoft 365.
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
ms.openlocfilehash: db458015d8434843ec64f3c2c00d640d4c4d8ff2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760177"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender
- Defender per endpoint

In linea con l'approccio tra domini di Microsoft alla protezione dalle minacce con SIEM e XDR (Extended Detection and Response), Microsoft Defender Advanced Threat Protection è stato ridenobrato come Microsoft Defender for Endpoint e l'abbiamo unificato in un unico portale integrato, il Centro sicurezza Microsoft 365.

Questa guida spiega come instradare gli account al Centro sicurezza Microsoft 365 abilitando il reindirizzamento automatico dall'ex portale di Microsoft Defender for Endpoint (securitycenter.windows.com o securitycenter.microsoft.com) al portale del Centro sicurezza Microsoft 365 (security.microsoft.com).

> [!NOTE]
> Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 supporta la concessione dell'accesso ai provider di servizi di sicurezza gestiti [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) nello stesso modo in cui viene concesso l'accesso nel Centro sicurezza [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato il reindirizzamento automatico, gli account che accedono all'ex portale di Microsoft Defender for Endpoint a securitycenter.windows.com o securitycenter.microsoft.com, verranno automaticamente instradati al portale del centro sicurezza Microsoft 365 in security.microsoft.com.
 
Altre informazioni sulle modifiche: Microsoft Defender for Endpoint nel Centro sicurezza [Microsoft 365.](microsoft-365-security-center-mde.md)

Ciò include il reindirizzamento per l'accesso diretto al portale precedente tramite browser, inclusi i collegamenti che puntano al portale di securitycenter.windows.com precedente, ad esempio i collegamenti nelle notifiche di posta elettronica e i collegamenti restituiti dalle chiamate API SIEM.  

 I collegamenti esterni dalle notifiche di posta elettronica o dalle API SIEM attualmente contengono collegamenti a entrambi i portali. Una volta abilitato il reindirizzamento, entrambi i collegamenti puntano al Centro sicurezza Microsoft 365 fino a quando il collegamento precedente non viene rimosso. Ti invitiamo ad adottare il nuovo collegamento che punta al Centro sicurezza Microsoft 365.

Per ulteriori informazioni sui collegamenti e il routing, vedere la tabella seguente.
## <a name="siem-api-routing"></a>Routing API SIEM

|**Proprietà**  |**Destinazione quando il reindirizzamento è DISATTIVATO**  |**Destinazione quando il reindirizzamento è ON** | 
|---------|---------|---------|
| LinkToWDATP | Pagina avviso in securitycenter.windows.com | Pagina avviso in security.microsoft.com  |
| IncidentLinkToWDATP | Pagina Evento imprevisto in securitycenter.windows.com  | Pagina Evento imprevisto in security.microsoft.com  |
| LinkToMTP | Pagina avviso in security.microsoft.com | Pagina avviso in security.microsoft.com  |
| IncidentLinkToMTP | Pagina Evento imprevisto in security.microsoft.com  | Pagina Evento imprevisto in security.microsoft.com  

## <a name="email-alert-notifications"></a>Notifiche di avviso tramite posta elettronica

|**Proprietà**  |**Destinazione quando il reindirizzamento è DISATTIVATO**  |**Destinazione quando il reindirizzamento è ON** |
|---------|---------|---------|
| Pagina avviso  | Pagina avviso in securitycenter.windows.com  | Pagina avviso in security.microsoft.com  |
| Pagina Evento imprevisto  |Pagina Evento imprevisto in securitycenter.windows.com  | Pagina Evento imprevisto in security.microsoft.com  
| Pagina avviso nel portale del centro sicurezza | Pagina avviso in security.microsoft.com | Pagina avviso in security.microsoft.com | 
| Pagina Evento imprevisto nel portale del centro sicurezza | Pagina Evento imprevisto in security.microsoft.com  | Pagina Evento imprevisto in security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Quando ha effetto? 
Una volta abilitato, questo aggiornamento potrebbe avere effetto quasi immediatamente per alcuni account. Tuttavia, la propagazione del reindirizzamento a ogni account dell'organizzazione potrebbe richiedere più tempo. Gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati al Centro sicurezza Microsoft 365 solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare il routing degli account al Centro sicurezza Microsoft 365:
1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory 

2. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365.

3. Passare a **Impostazioni**  >  **Endpoint Reindirizzamento**  >    >  **portale generale** o fare [clic qui](https://security.microsoft.com/preferences2/portal_redirection).  

4. Attiva l'impostazione Reindirizzamento **automatico**.

5. Fare **clic su** Abilita per applicare il reindirizzamento automatico al portale del centro sicurezza Microsoft 365.

>[!IMPORTANT]
>L'abilitazione di questa impostazione non interromperà le sessioni utente attive. Gli account che si trova in una sessione attiva mentre questa impostazione viene applicata verranno indirizzati al Centro sicurezza Microsoft 365 solo dopo aver terminato la sessione corrente e aver effettuato di nuovo l'accesso.

>[!NOTE]
>Per abilitare o disabilitare questa impostazione, è necessario essere un amministratore globale o disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?
If something isn't working for you or if there're anything you're unable to complete through the Microsoft 365 security center portal, we want to hear about it. Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattarci usando il modulo Invia feedback.

Per ripristinare l'ex portale di Microsoft Defender for Endpoint:

1. [Accedere al](https://security.microsoft.com/) Centro sicurezza Microsoft 365 come amministratore globale oppure usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare a **Impostazioni**  >  **Endpoint**  >  **Reindirizzamento**  >  **portale generale** o aprire la pagina [qui](https://security.microsoft.com/preferences2/portal_redirection).  

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