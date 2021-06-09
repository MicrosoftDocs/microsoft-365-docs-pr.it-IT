---
title: Reindirizzamento degli account da Microsoft Defender per Endpoint a Microsoft 365 Defender
description: Come reindirizzare account e sessioni da Defender for Endpoint a Microsoft 365 Defender.
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842567"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Reindirizzamento degli account da Microsoft Defender per Endpoint a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender
- Defender per endpoint

In linea con l'approccio tra domini di Microsoft alla protezione dalle minacce con SIEM e XDR (Extended Detection and Response), abbiamo ridefinito Microsoft Defender Advanced Threat Protection come Microsoft Defender for Endpoint e lo abbiamo unificato in un unico portale integrato, Microsoft 365 Defender.

Questa guida spiega come instradare gli account a Microsoft 365 Defender abilitando il reindirizzamento automatico dal precedente portale di Microsoft Defender for Endpoint (securitycenter.windows.com o securitycenter.microsoft.com) a Microsoft 365 Defender Portal (security.microsoft.com).

> [!NOTE]
> Microsoft Defender for Endpoint in Microsoft 365 Defender supporta la concessione dell'accesso ai provider di servizi di sicurezza gestiti [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) nello stesso modo in cui viene concesso l'accesso nel Centro sicurezza [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>Cosa aspettarsi
Una volta abilitato il reindirizzamento automatico, gli account che accedono all'ex portale di Microsoft Defender for Endpoint a securitycenter.windows.com o securitycenter.microsoft.com, verranno automaticamente instradati al portale di Microsoft 365 Defender in security.microsoft.com.
 
Altre informazioni sulle modifiche: [Microsoft Defender per Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).

Ciò include il reindirizzamento per l'accesso diretto al portale precedente tramite browser, inclusi i collegamenti che puntano al portale di securitycenter.windows.com precedente, ad esempio i collegamenti nelle notifiche di posta elettronica e i collegamenti restituiti dalle chiamate API SIEM.  

 I collegamenti esterni dalle notifiche di posta elettronica o dalle API SIEM attualmente contengono collegamenti a entrambi i portali. Una volta abilitato il reindirizzamento, entrambi i collegamenti puntano a Microsoft 365 Defender finché il collegamento precedente non viene rimosso. Ti invitiamo ad adottare il nuovo collegamento che punta a Microsoft 365 Defender.

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
Una volta abilitato, questo aggiornamento potrebbe avere effetto quasi immediatamente per alcuni account. Tuttavia, la propagazione del reindirizzamento a ogni account dell'organizzazione potrebbe richiedere più tempo. Gli account nelle sessioni attive mentre questa impostazione viene applicata non verranno espulsi dalla sessione e verranno instradati solo a Microsoft 365 Defender dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.  

### <a name="set-up-portal-redirection"></a>Configurare il reindirizzamento del portale
Per avviare il routing degli account Microsoft 365 Defender:
1. Assicurarsi di essere un amministratore globale o di disporre delle autorizzazioni di amministratore della sicurezza in Azure Active Directory 

2. [Accedi a](https://security.microsoft.com/) Microsoft 365 Defender.

3. Passare **a** Impostazioni  >  **endpoint di**  >  **reindirizzamento del**  >  **portale** generale o fare [clic qui](https://security.microsoft.com/preferences2/portal_redirection).  

4. Attiva l'impostazione Reindirizzamento **automatico**.

5. Fai **clic su** Abilita per applicare il reindirizzamento automatico a Microsoft 365 Defender.

>[!IMPORTANT]
>L'abilitazione di questa impostazione non interromperà le sessioni utente attive. Gli account che si trova in una sessione attiva mentre questa impostazione è applicata verranno indirizzati a Microsoft 365 Defender solo dopo aver terminare la sessione corrente e aver effettuato di nuovo l'accesso.

>[!NOTE]
>Per abilitare o disabilitare questa impostazione, è necessario essere un amministratore globale o disporre delle autorizzazioni Azure Active Directory di sicurezza.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?
Se qualcosa non funziona per te o se c'è qualcosa che non puoi completare tramite Microsoft 365 Defender, vogliamo sentirlo. Se hai riscontrato problemi con il reindirizzamento, ti invitiamo a contattarci usando il modulo Invia feedback.

Per ripristinare l'ex portale di Microsoft Defender for Endpoint:

1. [Accedere a](https://security.microsoft.com/) Microsoft 365 Defender come amministratore globale o usare e account con autorizzazioni di amministratore della sicurezza in Azure Active Directory.

2. Passare a **Impostazioni**  >  **reindirizzamento** del portale generale degli endpoint  >    >  o aprire [la pagina qui.](https://security.microsoft.com/preferences2/portal_redirection)  

3. Attivare o disattivare l'impostazione Reindirizzamento **automatico**.

4. Fai **clic su** & feedback quando richiesto.

Questa impostazione può essere nuovamente abilitata in qualsiasi momento. 

Una volta disabilitati, gli account non verranno più instradati a security.microsoft.com e si avrà di nuovo accesso al portale precedente, securitycenter.windows.com o securitycenter.microsoft.com. 

## <a name="related-information"></a>Informazioni correlate
- [Microsoft 365 Panoramica di Defender](overview-security-center.md)
- [Microsoft Defender per Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft fornisce SIEM e XDR unificati per modernizzare le operazioni di sicurezza](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografica XDR e SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Il nuovo defender](https://afrait.com/blog/the-new-defender/) 
- [Informazioni su Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portali di sicurezza Microsoft e centri di amministrazione](portals.md)