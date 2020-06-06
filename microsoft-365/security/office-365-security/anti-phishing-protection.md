---
title: Protezione anti-phishing
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
description: Gli amministratori possono ottenere informazioni sulle funzionalità di protezione anti-phishing in Exchange Online Protection (EOP) e Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 657224d3a18d7cae1581eaf6c603d1c04c3b41f3
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588313"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protezione anti-phishing in Microsoft 365

Il *phishing* è un attacco di posta elettronica che cerca di rubare informazioni riservate nei messaggi che sembrano provenire da mittenti legittimi o attendibili. Esistono categorie specifiche di phishing. Ad esempio:

- **Spear phishing** utilizza contenuto molto concentrato e personalizzato appositamente adattato ai destinatari mirati (in genere dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).

- La **caccia alle balene** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per ottenere il massimo effetto.

- **Business email compromess (BEC)** utilizza i mittenti attendibili falsificati (responsabili finanziari, clienti, partner attendibili e così via) nel tentativo di ingannare il destinatario nell'approvazione dei pagamenti, nel trasferimento di fondi o nella divulgazione dei dati del cliente.

- **Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo inizia quasi sempre nei messaggi di phishing. La protezione anti-phishing non consente di decrittografare i file crittografati, ma può contribuire a rilevare i messaggi di phishing iniziali associati alla campagna ransomware. Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware Attack in Microsoft 365](recover-from-ransomware.md).

Con la crescente complessità degli attacchi, è persino difficile per gli utenti addestrati identificare messaggi di phishing sofisticati. Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive di Office 365 Advanced Threat Protection (Office 365 ATP) possono essere di aiuto.

## <a name="anti-phishing-protection-in-eop"></a>Protezione anti-phishing in EOP

EOP (ovvero le organizzazioni Microsoft 365 senza ATP) contiene funzionalità che consentono di proteggere l'organizzazione da minacce di phishing:

- **Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti. Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).

- **Criteri di anti-phishing in EOP**: attivazione o disattivazione dell'intelligence di spoofing, attivazione o disabilitazione dell'identificazione dei mittenti non autenticati in Outlook e specifica dell'azione per i mittenti bloccati falsificati (passare alla cartella posta indesiderata o alla quarantena). Per ulteriori informazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

- **Autenticazione della posta elettronica implicita**: EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) con la reputazione mittente, la cronologia del mittente, la cronologia dei destinatari, l'analisi comportamentale e altre tecniche avanzate che consentono di identificare i mittenti contraffatti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Ulteriore protezione anti-phishing in Office 365 ATP

Office 365 ATP contiene funzionalità di anti-phishing aggiuntive e avanzate:

- **Criteri di anti-phishing ATP**: creare nuovi criteri personalizzati, configurare le impostazioni di antirappresentazione (proteggere utenti e domini dalla rappresentazione), le impostazioni di intelligence delle cassette postali e le soglie di phishing avanzate regolabili. Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing ATP in Microsoft 365](configure-atp-anti-phishing-policies.md). Per ulteriori informazioni sulle differenze tra i criteri anti-phishing e i criteri di anti-phishing ATP, vedere [anti-phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Visualizzazioni della campagna**: l'apprendimento automatico e altre euristiche identificano e analizzano i messaggi coinvolti negli attacchi di phishing coordinati per l'intero servizio e per l'organizzazione. Per ulteriori informazioni, vedere [Campaign views in Office 365 ATP](campaigns.md).

- **Simulatore di attacco**: gli amministratori possono creare falsi messaggi di phishing e inviarli agli utenti interni come strumenti didattici. Per ulteriori informazioni, vedere [Attack Simulator in Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Altre risorse anti-phishing

- Per gli utenti finali: [proteggersi da schemi di phishing e altre forme di frode online](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [In che modo Microsoft 365 convalida l'indirizzo del mittente per impedire il phishing](how-office-365-validates-the-from-address.md).
