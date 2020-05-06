---
title: Protezione anti-phishing in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: In questo articolo vengono illustrate le risorse disponibili online che possono essere utilizzate per conoscere e implementare le opzioni e le strategie di anti-phishing in Microsoft 365.
ms.openlocfilehash: 09d384376b1e44989987c40ef3c7860e4fac6167
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033763"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protezione anti-phishing in Microsoft 365

*Phishing* un attacco di posta elettronica che cerca di rubare informazioni riservate nei messaggi che sembrano provenire da mittenti legittimi o attendibili. Esistono categorie specifiche di phishing. Ad esempio:

- **Spear phishing** utilizza contenuto molto concentrato e personalizzato appositamente adattato ai destinatari mirati (in genere dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).

- La **caccia alle balene** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per ottenere il massimo effetto.

- **Business email compromess (BEC)** utilizza i mittenti attendibili falsificati (responsabili finanziari, clienti, partner attendibili e così via) nel tentativo di ingannare il destinatario nell'approvazione dei pagamenti, nel trasferimento di fondi o nella divulgazione dei dati del cliente.

- **Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo inizia quasi sempre nei messaggi di phishing. La protezione anti-phishing non consente di decrittografare i file crittografati, ma può contribuire a rilevare i messaggi di phishing iniziali associati alla campagna ransomware. Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware Attack in Microsoft 365](recover-from-ransomware.md).

Con la crescente complessità degli attacchi, è persino difficile per gli utenti addestrati identificare messaggi di phishing sofisticati. Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive di Microsoft 365 Advanced Threat Protection (ATP) possono essere utili.

## <a name="anti-phishing-protection-in-eop"></a>Protezione anti-phishing in EOP

EOP (ovvero le organizzazioni Microsoft 365 senza ATP) contiene funzionalità che consentono di proteggere l'organizzazione da minacce di phishing:

- **Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti. Per altre informazioni, vedere [Configurare spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- **Criteri di anti-phishing in EOP**: attivazione o disattivazione dell'intelligence di spoofing, attivazione o disabilitazione dell'identificazione dei mittenti non autenticati in Outlook e specifica dell'azione per i mittenti bloccati falsificati (passare alla cartella posta indesiderata o alla quarantena). Per ulteriori informazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

- **Autenticazione della posta elettronica implicita**: EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) con la reputazione mittente, la cronologia del mittente, la cronologia dei destinatari, l'analisi comportamentale e altre tecniche avanzate che consentono di identificare i mittenti contraffatti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Ulteriore protezione anti-phishing in Office 365 ATP

Office 365 ATP contiene funzionalità di anti-phishing aggiuntive e avanzate:

- **Criteri di anti-phishing ATP**: creare nuovi criteri personalizzati, configurare le impostazioni di antirappresentazione (proteggere utenti e domini dalla rappresentazione), le impostazioni di intelligence delle cassette postali e le soglie di phishing avanzate regolabili. Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing ATP in Microsoft 365](configure-atp-anti-phishing-policies.md). Per ulteriori informazioni sulle differenze tra i criteri anti-phishing e i criteri di anti-phishing ATP, vedere [anti-phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Visualizzazioni della campagna**: l'apprendimento automatico e altre euristiche identificano e analizzano i messaggi coinvolti negli attacchi di phishing coordinati per l'intero servizio e per l'organizzazione. Per ulteriori informazioni, vedere [Campaign views in Office 365 ATP](campaigns.md).

- **Simulatore di attacco**: gli amministratori possono creare falsi messaggi di phishing e inviarli agli utenti interni come strumenti didattici. Per ulteriori informazioni, vedere [Attack Simulator in Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Altre risorse anti-phishing

- Per gli utenti finali: [proteggersi da schemi di phishing e altre forme di frode online](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).

- [In che modo Microsoft 365 convalida l'indirizzo del mittente per impedire il phishing](how-office-365-validates-the-from-address.md).