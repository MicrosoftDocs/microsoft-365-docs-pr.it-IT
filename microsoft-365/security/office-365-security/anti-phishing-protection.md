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
ms.openlocfilehash: 2a28e2ecc45be941dbd6e346f9918e1692357840
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083105"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protezione anti-phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Il *phishing* è un attacco e-mail che prova a carpire informazioni riservate attraverso messaggi che sembrano provenire da mittenti attendibili e legittimi. Esistono categorie specifiche di phishing. Ad esempio:

- **Il spear phishing** usa contenuto mirato e personalizzato specifico per i destinatari di destinazione (in genere, dopo la ricognizione dei destinatari da parte dell'autore dell'attacco).

- **La caccia alle baleni** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per il massimo effetto.

- La compromissione della posta elettronica aziendale **(BEC)** utilizza mittenti attendibili contraffatti (responsabili finanziari, clienti, partner attendibili e così via) per indurre i destinatari ad approvare pagamenti, trasferire fondi o rivelare i dati dei clienti. Scopri di più guardando [questo video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo quasi sempre inizia nei messaggi di phishing. La protezione anti-phishing non può aiutarti a decrittografare i file crittografati, ma può aiutare a rilevare i messaggi di phishing iniziali associati alla campagna ransomware. Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Con la crescente complessità degli attacchi, è anche difficile per gli utenti addestrati identificare i messaggi di phishing sofisticati. Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive in Microsoft Defender per Office 365 possono essere utili.

## <a name="anti-phishing-protection-in-eop"></a>Protezione anti-phishing in EOP

EOP (ovvero, Microsoft 365 senza Microsoft Defender per Office 365) contiene funzionalità che consentono di proteggere l'organizzazione dalle minacce di phishing:

- **Spoof intelligence:** usare le informazioni di spoof intelligence per esaminare i mittenti contraffatti rilevati nei messaggi provenienti da domini esterni ed interni e consentire o bloccare manualmente tali mittenti rilevati. Per altre informazioni, vedere [Dati analitici di spoof intelligence in EOP](learn-about-spoof-intelligence.md).

- **Criteri anti-phishing in EOP:** attivare o disattivare l'intelligence spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e specificare l'azione per i mittenti falsificati bloccati. Per ulteriori informazioni, vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

- **Consentire o bloccare i mittenti di spoofing nel tenant Elenco consentiti/bloccati**: quando si esegue l'override del verdetto nei dati analitici di spoof intelligence, il mittente di spoofing diventa una voce nell'Elenco consentiti/bloccati manuale che compare unicamente nella scheda **Spoofing** nel tenant Elenco consentiti/bloccati. Inoltre, è possibile creare, consentire o bloccare manualmente le voci per i mittenti di spoofing prima che vengano rilevati da spoof intelligence. Per altre informazioni, vedere [Gestire il tenant Elenco consentiti/blcocati in EOP](tenant-allow-block-list.md).

- Autenticazione implicita della posta elettronica **:** EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC)](use-dmarc-to-validate-email.md)con reputazione mittente, cronologia mittente, cronologia dei destinatari, analisi comportamentali e altre tecniche avanzate per identificare i mittenti contraffatti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protezione anti-phishing aggiuntiva in Defender per Office 365

Microsoft Defender per Office 365 contiene funzionalità anti-phishing aggiuntive e avanzate:

- **Criteri anti-phishing in Microsoft Defender per Office 365**: configurare le impostazioni di protezione della rappresentazione per mittenti e domini di mittente specifici, impostazioni di intelligence delle cassette postali e soglie avanzate di phishing regolabili. Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md). Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in EOP e i criteri anti-phishing in Defender per Office 365, vedere [Criteri anti-phishing in Microsoft 365](set-up-anti-phishing-policies.md).
- **Visualizzazioni campagna**: Machine learning e altre euristiche identificano e analizzano i messaggi coinvolti in attacchi di phishing coordinati contro l'intero servizio e l'organizzazione. Per altre informazioni, vedi [Visualizzazioni campagna in Microsoft Defender per Office 365](campaigns.md).
- **Formazione sulla simulazione di** attacchi: gli amministratori possono creare messaggi di phishing falsi e inviarli agli utenti interni come strumento didattico. Per ulteriori informazioni, vedere [Simulate a phishing attack](attack-simulation-training.md).

## <a name="other-anti-phishing-resources"></a>Altre risorse anti-phishing

- Per gli utenti finali: [proteggersi dagli schemi di phishing e altre forme di frode online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Come Microsoft 365 convalida l'indirizzo Mittente per impedire il phishing](how-office-365-validates-the-from-address.md).
