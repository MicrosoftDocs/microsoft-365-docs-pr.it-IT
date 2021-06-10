---
title: Usare identità, dispositivo e protezione dalle minacce per la normativa sulla privacy dei dati
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
description: Prevenire violazioni dei dati personali con i servizi di identità, dispositivo e protezione dalle minacce di Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199466"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usare identità, dispositivo e protezione dalle minacce per la normativa sulla privacy dei dati

Microsoft 365 fornisce una serie di funzionalità di protezione da identità, dispositivi e minacce che le organizzazioni possono utilizzare per garantire la conformità alle normative di conformità relative alla privacy dei dati. In questo articolo vengono descritti i requisiti delle normative sulla privacy dei dati in queste aree e viene fornito un elenco delle funzionalità e dei servizi di Microsoft 365 correlati con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Relazione tra identità, dispositivo e protezione dalle minacce con la normativa sulla privacy dei dati

Anche se le normative sulla privacy dei dati variano in base alla loro specificità, l'essenza di ciò che chiamano è incorporata nell'articolo 5(1)(f) del GDPR, che afferma che:

- I dati personali devono essere trattati in modo da garantire una sicurezza adeguata dei dati personali, compresa la protezione contro il trattamento non autorizzato o illecito e contro la perdita accidentale, la distruzione o il danneggiamento, utilizzando misure tecniche o organizzative appropriate ("integrità e riservatezza").

Poiché le violazioni dei dati personali sono spesso causate da compromissione dell'account amministrativo o dell'utente finale e dall'accesso al sistema dannoso. Ad esempio, una violazione dell'account amministratore può comportare l'esfiltrazione dei numeri di carta di credito del cliente o altre informazioni personali. Tutte le identità, i dispositivi e la protezione dalle minacce generalmente consigliabili disponibili con Microsoft 365 potenzialmente dovrebbero essere implementate, che verranno riflesse nel punteggio di conformità, disponibile in Compliance Manager.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Utilizzo dei risultati del lavoro di valutazione e di Compliance Manager

Compliance Manager include identità, dispositivo e protezione dalle minacce usando queste categorie:

- L'identità corrisponde alla **categoria Controllo accesso**
- Il dispositivo corrisponde alla **categoria Gestisci** dispositivi
- Protezione dalle minacce corrisponde alla **categoria Protezione dalle** minacce
 
Se queste sono selezionate nell'insieme di esempio di quattro principali normative sulla privacy dei dati, Compliance Manager specifica 90 azioni di miglioramento, la maggior parte delle quali ha un punteggio "27". Dal momento che un numero così elevato viene chiamato da Compliance Manager per queste categorie, alcune delle più comuni sono elencate qui, per riferimento.

Usa [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) per l'identità e la categoria **Controllo accesso,** con cui puoi:

- Implementare l'autenticazione resistente alla riesecuzione (per impedire attacchi "Man in the middle")
- Bloccare l'autenticazione legacy.
- Configurare i criteri di rischio di accesso degli utenti e dei rischi per l'accesso degli utenti.
- Abilitare l'accesso condizionale e l'autenticazione a più fattori (MFA) per amministratori e non amministratori.
- Configurare e applicare criteri password.
- Limitare l'accesso agli account con privilegi con Azure AD Privileged Identity Management.
- Disabilitare l'accesso al termine.
- Controllare gli account utente e le modifiche di stato.
- Esaminare le modifiche amministrative e del gruppo di ruoli.

Usa [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) per i dispositivi e **la categoria Gestisci dispositivi,** con cui puoi:

- Bloccare i dispositivi mobili interrotti e rooted.
- Configurare Intune per la gestione dei dispositivi mobili.
- Creare criteri di conformità per dispositivi Android, iOS, macOS e Windows dispositivi.
- Crea un profilo di configurazione del dispositivo per dispositivi Android, iOS, macOS e Windows dispositivi.
- Creare criteri di protezione delle app per iOS e Windows.
- Nascondere le informazioni con la schermata di blocco.
- Implementare criteri password per i dispositivi mobili.
- Richiedi ai dispositivi mobili di bloccarsi in caso di inattività.
- Richiedere ai dispositivi mobili di cancellare i dati in caso di più errori di accesso.

Usa [Exchange Online Protection e Microsoft Defender per Office 365](../security/office-365-security/defender-for-office-365.md) per la **categoria** Protezione dalle minacce, con cui puoi:

- Abilitare l'autenticazione mittente (SPF, DMARC e DKIM).
- Configurare Microsoft Defender per i Office 365 anti-phishing.
- Implementare allegati sicuri.
- Implementare collegamenti sicuri.
- Implementare i criteri di rilevamento e risposta di malware.
- Implementare i criteri di posta indesiderata in ingresso e in uscita.

### <a name="references"></a>Riferimenti:

- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)
- [Proteggere dalle minacce in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Allegati sicuri](../security/office-365-security/safe-attachments.md)
- [Collegamenti sicuri](../security/office-365-security/safe-links.md)
- [Sicurezza documenti](../security/office-365-security/safe-docs.md)
