---
title: Protezione anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Gli amministratori possono conoscere le funzionalità di protezione anti-phishing in Exchange Online Protection (EOP) e Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289054"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protezione anti-phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Il phishing* è un attacco tramite posta elettronica che tenta di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili. Esistono categorie specifiche di phishing. Ad esempio:

- **Il phishing** con attacchi di phishing usa contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione sui destinatari da parte dell'autore dell'attacco).

- **La whaling è** diretta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per il massimo effetto.

- La compromissione della posta elettronica aziendale **(BEC)** utilizza mittenti attendibili contraffatti (responsabili finanziari, clienti, partner attendibili e così via) per indurre i destinatari ad approvare i pagamenti, trasferire fondi o rivelare i dati dei clienti.

- **Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo quasi sempre nei messaggi di phishing. La protezione anti-phishing non può aiutare a decrittografare i file crittografati, ma può aiutare a rilevare i messaggi di phishing iniziali associati alla campagna ransomware. Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Ripristino da un attacco ransomware in Microsoft 365.](recover-from-ransomware.md)

Con la crescente complessità degli attacchi, è anche difficile per gli utenti esperti identificare i messaggi di phishing sofisticati. Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive di Microsoft Defender per Office 365 possono essere di aiuto.

## <a name="anti-phishing-protection-in-eop"></a>Protezione anti-phishing in EOP

EOP (ovvero, le organizzazioni di Microsoft 365 senza Microsoft Defender per Office 365) contiene funzionalità che consentono di proteggere l'organizzazione dalle minacce di phishing:

- **Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti. Per ulteriori informazioni, vedere [Configurare spoof intelligence in EOP.](learn-about-spoof-intelligence.md)

- Criteri **anti-phishing in EOP:** attivare o disattivare spoof intelligence, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e specificare l'azione per i mittenti falsificati bloccati (spostare nella cartella Posta indesiderata o in quarantena). Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)

- **Autenticazione** implicita della posta elettronica : EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC)](use-dmarc-to-validate-email.md)con reputazione mittente, cronologia mittente, cronologia destinatari, analisi comportamentale e altre tecniche avanzate per identificare i mittenti contraffatti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protezione anti-phishing aggiuntiva in Microsoft Defender per Office 365

Microsoft Defender per Office 365 contiene funzionalità anti-phishing aggiuntive e più avanzate:

- Criteri **anti-phishing in Microsoft Defender per Office 365:** creare nuovi criteri personalizzati, configurare le impostazioni di anti-rappresentazione (proteggere utenti e domini dalla rappresentazione), le impostazioni di intelligence per le cassette postali e le soglie avanzate di phishing regolabili. Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md) Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in EOP e i criteri anti-phishing in Defender per Office 365, vedere [Criteri anti-phishing in Microsoft 365.](set-up-anti-phishing-policies.md)

- **Visualizzazioni della** campagna : Machine learning e altre euristiche identificano e analizzano i messaggi coinvolti in attacchi di phishing coordinati contro l'intero servizio e l'organizzazione. Per altre informazioni, vedere [Visualizzazioni campagna in Microsoft Defender per Office 365.](campaigns.md)

- **Simulatore di** attacco: gli amministratori possono creare messaggi di phishing falsi e inviarli agli utenti interni come strumento didattico. Per altre informazioni, vedere [Simulatore di attacchi in Microsoft Defender per Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Altre risorse anti-phishing

- Per gli utenti finali: [proteggersi da schemi di phishing e altre forme di frode online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [In che modo Microsoft 365 convalida l'indirizzo Da per impedire il phishing.](how-office-365-validates-the-from-address.md)
