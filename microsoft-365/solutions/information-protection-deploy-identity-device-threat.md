---
title: Utilizzo dell'identità, del dispositivo e della protezione dalle minacce per la normativa sulla privacy dei dati
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Impedire violazioni dei dati personali con i servizi Identity, Device e Threat Protection di Microsoft 365.
ms.openlocfilehash: 74894037ef2fe56aeb5bc44340cd8a946863baff
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695080"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Utilizzo dell'identità, del dispositivo e della protezione dalle minacce per la normativa sulla privacy dei dati

Microsoft 365 fornisce una serie di funzionalità di protezione dell'identità, dei dispositivi e delle minacce che le organizzazioni possono utilizzare per contribuire a conformarsi alle normative sulla conformità relative alla privacy dei dati. In questo articolo vengono descritte le normative sulla privacy dei dati richieste in queste aree e viene fornito un elenco delle funzionalità e dei servizi relativi a Microsoft 365 con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Come identità, dispositivo e protezione dalle minacce riguardano la normativa sulla privacy dei dati

Anche se le normative sulla privacy dei dati variano in base alla loro specificità, l'essenza del loro appello è incarnata nell'articolo 5 (1) (f) dell'GDPR, in cui si afferma che: 

- I dati personali devono essere elaborati in modo da garantire una sicurezza adeguata dei dati personali, inclusa la protezione contro l'elaborazione non autorizzata o illecita e contro la perdita accidentale, la distruzione o il danneggiamento, usando misure tecniche o organizzative appropriate ("integrità e riservatezza").

Poiché le violazioni dei dati personali sono spesso causate da un compromesso dell'account amministrativo o dell'utente finale e da un accesso dannoso del sistema. Ad esempio, un hack dell'account di amministratore può comportare la exfiltration dei numeri di carta di credito del cliente o di altre informazioni personali. Tutti gli identificatori, i dispositivi e la protezione delle minacce generalmente consigliati disponibili con Microsoft 365 potrebbero essere implementati, che verranno riflessi nel punteggio di conformità.

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>Utilizzo dei risultati del lavoro di valutazione e del Punteggio di conformità

Il Punteggio di conformità include identità, dispositivo e protezione dalle minacce utilizzando queste categorie:

- Identity corrisponde alla categoria di **accesso ai controlli**
- Dispositivo corrispondente alla categoria **Gestisci dispositivi**
- La protezione dalle minacce corrisponde alla categoria **Proteggi contro i pericoli**
 
Se questi sono selezionati nell'insieme del campione di quattro importanti normative sulla privacy dei dati, Score conformità specifica 90 azioni di miglioramento, la maggior parte delle quali ha un punteggio di "27". Poiché un numero così elevato viene definito dal punteggio di conformità per queste categorie, alcuni dei più comuni sono elencati qui, per riferimento.

Utilizzare [Azure Active Directory (Azure ad)](https://azure.microsoft.com/services/active-directory/) per l'identità e la categoria di **accesso ai controlli** , con cui è possibile:

- Implementazione dell'autenticazione resistente ai rigiocamenti (per impedire attacchi di tipo "Man in the Middle")
- Blocca l'autenticazione legacy.
- Configurare i rischi per gli utenti e i criteri di accesso dell'utente.
- Abilitare l'accesso condizionale e l'autenticazione a più fattori (AMF) per gli amministratori e gli utenti non amministratori.
- Configurare e applicare i criteri per le password.
- Limitare l'accesso a account privilegiati con Azure AD Privileged Identity Management.
- Disabilitare l'accesso alla terminazione.
- Controllare gli account utente e le modifiche dello stato.
- Esaminare il gruppo di ruoli e le modifiche amministrative.

Utilizzare [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) per i dispositivi e la categoria **Gestisci dispositivi** , con cui è possibile eseguire le operazioni seguenti:

- Blocca i dispositivi mobili bloccati e sradicati del Jail.
- Configurare Intune per la gestione dei dispositivi mobili.
- Creare criteri di conformità per i dispositivi Android, iOS, macOS e Windows.
- Creare un profilo di configurazione del dispositivo per i dispositivi Android, iOS, macOS e Windows.
- Creare criteri di protezione delle app per iOS e Windows.
- Nascondere le informazioni con la schermata di blocco.
- Implementare criteri password per i dispositivi mobili.
- Richiedere ai dispositivi mobili di bloccarsi su inattività.
- Richiedere ai dispositivi mobili di cancellare gli errori di accesso multipli.

Utilizzare [Exchange Online Protection e Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) per la categoria **protezione dalle minacce** , con cui è possibile eseguire le operazioni seguenti:

- Abilitare l'autenticazione del mittente (SPF, DMARC e DKIM).
- Impostare i criteri di anti-phishing di Office 365 Advanced Threat Protection (ATP).
- Implementare gli allegati sicuri di ATP.
- Implementare collegamenti sicuri di ATP.
- Implementare criteri di rilevamento e risposta malware.
- Implementare i criteri di posta indesiderata in uscita e in ingresso.

### <a name="references"></a>Riferimenti

- [Criteri comuni di identità e accesso dei dispositivi](../enterprise/identity-access-policies.md)
- [Protezione dalle minacce in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Allegati sicuri di ATP](../security/office-365-security/atp-safe-attachments.md)
- [Collegamenti sicuri di ATP](../security/office-365-security/atp-safe-links.md)
- [Sicurezza documenti ATP](../security/office-365-security/safe-docs.md)
