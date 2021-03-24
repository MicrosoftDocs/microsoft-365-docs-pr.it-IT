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
description: Gli amministratori possono ottenere informazioni sulle funzionalità di protezione anti-phishing in Exchange Online Protection (EOP) e Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065565"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protezione anti-phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Il phishing* è un attacco tramite posta elettronica che tenta di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili. Esistono categorie specifiche di phishing. Ad esempio:

- **Il spear phishing** usa contenuto mirato e personalizzato specifico per i destinatari di destinazione (in genere, dopo la ricognizione dei destinatari da parte dell'autore dell'attacco).

- **La caccia alle baleni** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per il massimo effetto.

- La compromissione della posta elettronica aziendale **(BEC)** utilizza mittenti attendibili contraffatti (responsabili finanziari, clienti, partner attendibili e così via) per indurre i destinatari ad approvare pagamenti, trasferire fondi o rivelare i dati dei clienti.

- **Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo quasi sempre inizia nei messaggi di phishing. La protezione anti-phishing non può aiutarti a decrittografare i file crittografati, ma può aiutare a rilevare i messaggi di phishing iniziali associati alla campagna ransomware. Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Con la crescente complessità degli attacchi, è anche difficile per gli utenti addestrati identificare i messaggi di phishing sofisticati. Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive in Microsoft Defender per Office 365 possono essere utili.

## <a name="anti-phishing-protection-in-eop"></a>Protezione anti-phishing in EOP

EOP (ovvero, le organizzazioni di Microsoft 365 senza Microsoft Defender per Office 365) contiene funzionalità che consentono di proteggere l'organizzazione dalle minacce di phishing:

- **Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti. Per ulteriori informazioni, vedere [Configure spoof intelligence in EOP.](learn-about-spoof-intelligence.md)

- Criteri **anti-phishing in EOP:** attivare o disattivare l'intelligence di spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e specificare l'azione per i mittenti falsificati bloccati (passare alla cartella Posta indesiderata o alla quarantena). Per ulteriori informazioni, vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

- Autenticazione implicita della posta elettronica **:** EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC)](use-dmarc-to-validate-email.md)con reputazione mittente, cronologia mittente, cronologia dei destinatari, analisi comportamentali e altre tecniche avanzate per identificare i mittenti contraffatti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protezione anti-phishing aggiuntiva in Microsoft Defender per Office 365

Microsoft Defender per Office 365 contiene funzionalità anti-phishing aggiuntive e più avanzate:

- Criteri **anti-phishing in Microsoft Defender per Office 365:** creare nuovi criteri personalizzati, configurare le impostazioni di anti-rappresentazione (proteggere utenti e domini dalla rappresentazione), impostazioni di intelligence delle cassette postali e soglie di phishing avanzate regolabili. Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in EOP e i criteri anti-phishing in Defender per Office 365, vedere [Criteri anti-phishing in Microsoft 365.](set-up-anti-phishing-policies.md)

- **Visualizzazioni campagna**: Machine learning e altre euristiche identificano e analizzano i messaggi coinvolti in attacchi di phishing coordinati contro l'intero servizio e l'organizzazione. Per ulteriori informazioni, vedere [Visualizzazioni campagna in Microsoft Defender per Office 365.](campaigns.md)

- **Simulatore di** attacco: gli amministratori possono creare messaggi di phishing falsi e inviarli agli utenti interni come strumento didattico. Per ulteriori informazioni, vedere [Simulatore di attacco in Microsoft Defender per Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Altre risorse anti-phishing

- Per gli utenti finali: [proteggersi dagli schemi di phishing e altre forme di frode online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [In che modo Microsoft 365 convalida l'indirizzo From per impedire il phishing.](how-office-365-validates-the-from-address.md)
