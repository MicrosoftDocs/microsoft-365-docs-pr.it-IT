---
title: Usare la protezione da identità, dispositivi e minacce per la normativa sulla privacy dei dati
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Prevenire violazioni dei dati personali con i servizi di protezione da identità, dispositivi e minacce di Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847179"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usare la protezione da identità, dispositivi e minacce per la normativa sulla privacy dei dati

Microsoft 365 offre una serie di funzionalità di protezione da identità, dispositivi e minacce che le organizzazioni possono utilizzare per garantire la conformità alle normative di conformità relative alla privacy dei dati. Questo articolo descrive ciò che le normative sulla privacy dei dati richiedono in queste aree e fornisce un elenco delle funzionalità e dei servizi di Microsoft 365 correlati con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Relazione tra identità, dispositivo e protezione dalle minacce con la normativa sulla privacy dei dati

Anche se le normative sulla privacy dei dati variano in base alla loro specificità, l'essenza di ciò che chiamano è incorporata nell'articolo 5(1)(f) del GDPR, che afferma che: 

- I dati personali devono essere trattati in modo da garantire una sicurezza appropriata dei dati personali, compresa la protezione contro il trattamento non autorizzato o illecito e contro perdite accidentali, distruzione o danni, utilizzando misure tecniche o organizzative appropriate ("integrità e riservatezza").

Poiché le violazioni dei dati personali sono spesso causate da compromissione dell'account amministrativo o dell'utente finale e dall'accesso al sistema dannoso. Ad esempio, una violazione dell'account amministratore può comportare l'esfiltrazione dei numeri di carta di credito dei clienti o altre informazioni personali. Tutte le potenzialità di protezione da identità, dispositivi e minacce disponibili con Microsoft 365 dovrebbero essere implementate, che verranno riflesse nel punteggio di conformità, disponibile in Compliance Manager.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Utilizzo dei risultati del lavoro di valutazione e di Compliance Manager

Compliance Manager include la protezione da identità, dispositivi e minacce usando queste categorie:

- L'identità corrisponde alla **categoria Accesso di** controllo
- Il dispositivo corrisponde alla **categoria Gestisci** dispositivi
- Protezione dalle minacce corrisponde alla **categoria Protezione dalle** minacce
 
Se queste sono selezionate nell'insieme di esempio di quattro principali normative sulla privacy dei dati, Compliance Manager specifica 90 azioni di miglioramento, la maggior parte delle quali viene classificata come "27". Poiché un numero così elevato viene chiamato da Compliance Manager per queste categorie, alcune delle più comuni sono elencate qui, come riferimento.

Usare [Azure Active Directory (Azure AD) per](https://azure.microsoft.com/services/active-directory/) l'identità e la categoria Controlla **accesso,** con cui è possibile:

- Implementare l'autenticazione a prova di riproduzione (per impedire attacchi "Man in the middle")
- Bloccare l'autenticazione legacy.
- Configurare i criteri di rischio di accesso degli utenti e dei rischi per l'accesso degli utenti.
- Abilitare l'accesso condizionale e l'autenticazione a più fattori (MFA) per amministratori e non amministratori.
- Configurare e applicare i criteri password.
- Limitare l'accesso agli account con privilegi con Azure AD Privileged Identity Management.
- Disabilitare l'accesso al termine.
- Controllare gli account utente e le modifiche di stato.
- Esaminare le modifiche amministrative e del gruppo di ruoli.

Usare [Microsoft Endpoint Manager per](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) i dispositivi e la categoria **Gestisci** dispositivi, con cui è possibile:

- Bloccare i dispositivi mobili con jail broken e rooted.
- Configurare Intune per la gestione dei dispositivi mobili.
- Creare criteri di conformità per dispositivi Android, iOS, macOS e Windows.
- Crea un profilo di configurazione del dispositivo per dispositivi Android, iOS, macOS e Windows.
- Creare criteri di protezione delle app per iOS e Windows.
- Nascondere le informazioni con la schermata di blocco.
- Implementare criteri password per i dispositivi mobili.
- Richiedi ai dispositivi mobili di bloccare l'inattività.
- Richiedi ai dispositivi mobili di cancellare i dati in caso di più errori di accesso.

Usare Exchange Online Protection e Microsoft Defender per  [Office 365](../security/office-365-security/office-365-atp.md) per la categoria Protezione dalle minacce, con cui è possibile:

- Abilitare l'autenticazione mittente (SPF, DMARC e DKIM).
- Configurare i criteri anti-phishing di Microsoft Defender per Office 365.
- Implementare allegati sicuri.
- Implementare collegamenti sicuri.
- Implementare i criteri di rilevamento e risposta antimalware.
- Implementare i criteri di posta indesiderata in ingresso e in uscita.

### <a name="references"></a>Riferimenti:

- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)
- [Proteggere dalle minacce in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Allegati sicuri](../security/office-365-security/atp-safe-attachments.md)
- [Collegamenti sicuri](../security/office-365-security/atp-safe-links.md)
- [Sicurezza documenti](../security/office-365-security/safe-docs.md)
