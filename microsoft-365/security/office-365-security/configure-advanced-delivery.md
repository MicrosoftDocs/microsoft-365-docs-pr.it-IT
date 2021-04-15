---
title: Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Gli amministratori possono imparare a utilizzare i criteri di recapito avanzati in Exchange Online Protection (EOP) per identificare i messaggi che non devono essere filtrati in scenari supportati specifici (simulazioni di phishing di terze parti e messaggi recapitati alle cassette postali delle operazioni di sicurezza (SecOps).
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760432"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La funzionalità descritta in questo articolo è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.

Vogliamo proteggere l'organizzazione per impostazione [predefinita,](secure-by-default.md)in modo che Exchange Online Protection (EOP) non consenta elenchi attendibili o bypass di filtro per i messaggi che causano malware o verdetti di phishing ad alta confidenza. Tuttavia, riconosciamo che esistono scenari specifici che richiedono il recapito di messaggi non filtrati. Ad esempio:

- **Simulazioni di phishing di terze** parti: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.
- Cassette postali delle operazioni di sicurezza **(SecOps):** cassette postali dedicate utilizzate dai team di sicurezza per raccogliere e analizzare i messaggi non filtrati (buoni e non).

Si utilizza il _criterio di recapito avanzato_ in Microsoft 365 per impedire che questi messaggi in questi scenari _specifici_ vengano <sup>\*</sup> filtrati. Il criterio di recapito avanzato garantisce che i messaggi in questi scenari non siano filtrati:

- I filtri in EOP e Microsoft Defender per Office 365 non esempre alcuna azione su questi messaggi.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup>
- [Gli avvisi di](alerts.md) sistema predefiniti non vengono attivati per questi scenari.
- [AIR e il clustering in Defender per Office 365](office-365-air.md) ignora questi messaggi.
- In particolare per simulazioni di phishing di terze parti:
  - [Gli invii di](admin-submission.md) amministratori generano una risposta automatica che indica che il messaggio fa parte di una campagna di simulazione di phishing e non rappresenta una minaccia reale. Gli avvisi e AIR non verranno attivati.
  - [I collegamenti sicuri in Defender per Office 365](safe-links.md) non bloccano o detonano gli URL identificati in modo specifico in questi messaggi.
  - [Gli allegati sicuri in Defender per Office 365](safe-attachments.md) non detonano gli allegati in questi messaggi.

<sup>\*</sup> Non è possibile ignorare il filtro antimalware o ZAP per il malware.

I messaggi identificati dal criterio di recapito avanzato non sono minacce alla sicurezza, quindi i messaggi vengono contrassegnati come sostituzioni del sistema. Gli amministratori possono filtrare e analizzare queste sostituzioni di sistema nelle esperienze seguenti:

- [Threat Explorer/Rilevamenti in tempo reale in Defender per Office 365 piano 2](threat-explorer.md)
- Pagina [Entità e-mail in Esplora minacce/Rilevamenti in tempo reale](mdo-email-entity-page.md)
- Rapporto [sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report)
- [Ricerca avanzata in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Visualizzazioni campagna](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla **pagina Recapito avanzato,** aprire <https://protection.office.com/advanceddelivery> .

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare o rimuovere le impostazioni configurate nel criterio di  recapito avanzato, è necessario essere membri del gruppo  di ruoli Amministratore della sicurezza nel Centro sicurezza **&** conformità e membri del gruppo di ruoli Gestione organizzazione in **Exchange Online.**  
  - Per l'accesso in sola lettura ai criteri di recapito avanzati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online.](/exchange/permissions-exo/permissions-exo)

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Usare il Centro sicurezza & conformità per configurare simulazioni di phishing di terze parti nei criteri di recapito avanzati

1. Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Recapito avanzato.**

2. Nella pagina **Recapito avanzato** selezionare la scheda **Simulazione di phishing** e quindi fare clic su **Modifica.**

3. Nel riquadro **a comparsa Simulazione di phishing** di terze parti che si apre, configurare le impostazioni seguenti:

   - **Dominio di invio:** è necessario almeno un dominio di indirizzo di posta elettronica (ad esempio, contoso.com). È possibile aggiungere fino a 10 voci.
   - **IP di** invio: è necessario almeno un indirizzo IPv4 valido. È possibile aggiungere fino a 10 voci. I valori validi sono:
     - IP singolo: ad esempio, 192.168.1.1.
     - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
     - IP CIDR: ad esempio, 192.168.0.1/25.
   - **URL di simulazione per consentire:** facoltativamente, immettere URL specifici che fanno parte della campagna di simulazione di phishing che non devono essere bloccati o detonati. È possibile aggiungere fino a 10 voci.

4. Al termine, fare clic su **Salva.**

Le voci di simulazione di phishing di terze parti configurate vengono visualizzate nella **scheda Simulazione di** phishing. Per apportare modifiche, **fare clic su** Modifica nella scheda.

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Utilizzare il Centro sicurezza & conformità per configurare le cassette postali SecOps nel criterio di recapito avanzato

1. Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Recapito avanzato.**

2. Nella pagina **Recapito avanzato** selezionare la scheda Cassetta **postale SecOps** e quindi fare clic su **Modifica.**

3. Nel riquadro a comparsa della cassetta postale **SecOps** che si apre, immettere gli indirizzi di posta elettronica delle cassette postali di Exchange Online esistenti che si desidera designare come cassette postali SecOps. I gruppi di distribuzione non sono consentiti.

4. Al termine, fare clic su **Salva**.

Le voci della cassetta postale SecOps configurate vengono visualizzate nella scheda Cassetta postale **SecOps.** Per apportare modifiche, **fare clic su** Modifica nella scheda.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Scenari aggiuntivi che richiedono il bypass del filtro

Oltre ai due scenari che possono essere utili per i criteri di recapito avanzati, esistono altri scenari che potrebbero richiedere l'esclusione del filtro:

- **Filtri di terze parti:** se il record MX del dominio non punta a Office 365 (i messaggi vengono instradati da un'altra [parte),](secure-by-default.md) la protezione per impostazione predefinita non è disponibile.

  Per ignorare il filtro Microsoft per i messaggi che sono già stati valutati dal filtro di terze parti, utilizzare le regole del flusso di posta (note anche come regole di trasporto), vedere [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

- **Falsi positivi in** esame: è possibile consentire temporaneamente a Determinati messaggi ancora [](admin-submission.md) analizzati da Microsoft tramite invii da parte dell'amministratore di segnalare a Microsoft messaggi positivi noti erroneamente contrassegnati come non corretti (falsi positivi). Come per tutte le sostituzioni, è consigliabile che queste quote siano temporanee.
