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
description: Gli amministratori possono imparare a utilizzare i criteri di recapito avanzati in Exchange Online Protection (EOP) per identificare i messaggi che non devono essere filtrati in scenari supportati specifici (simulazioni di phishing di terze parti e messaggi recapitati alle cassette postali secOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108404"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La funzionalità descritta in questo articolo è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.

Per proteggere [l'organizzazione](secure-by-default.md)per impostazione predefinita, Exchange Online Protection (EOP) non consente elenchi attendibili o bypass di filtro per i messaggi identificati come malware o phishing ad alta probabilità. Esistono tuttavia scenari specifici che richiedono il recapito di messaggi non filtrati. Ad esempio:

- **Simulazioni di phishing di terze** parti: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.
- Cassette postali delle operazioni di sicurezza **(SecOps):** cassette postali dedicate utilizzate dai team di sicurezza per raccogliere e analizzare i messaggi non filtrati (buoni e non).

È possibile utilizzare _i criteri di_ recapito avanzati in Microsoft 365 per impedire che questi messaggi in questi scenari _specifici_ vengano filtrati. <sup>\*</sup> Il criterio di recapito avanzato garantisce che i messaggi in questi scenari raggiunga i risultati seguenti:

- I filtri in EOP e Microsoft Defender per Office 365 non esempre alcuna azione su questi messaggi.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup>
- [Gli avvisi di](alerts.md) sistema predefiniti non vengono attivati per questi scenari.
- [AIR e clustering in Defender per Office 365](office-365-air.md) ignora questi messaggi.
- In particolare per simulazioni di phishing di terze parti:
  - [Gli invii di](admin-submission.md) amministratori generano una risposta automatica che indica che il messaggio fa parte di una campagna di simulazione di phishing e non è una minaccia reale. Gli avvisi e AIR non verranno attivati.
  - [Cassaforte link in Defender per Office 365](safe-links.md) non blocca o fa detonare gli URL identificati in modo specifico in questi messaggi.
  - [Cassaforte allegati in Defender per Office 365](safe-attachments.md) non fa detonare gli allegati in questi messaggi.

<sup>\*</sup> Non è possibile ignorare il filtro antimalware o ZAP per il malware.

I messaggi identificati dal criterio di recapito avanzato non sono minacce alla sicurezza, quindi i messaggi vengono contrassegnati come sostituzioni del sistema. Gli amministratori possono filtrare e analizzare queste sostituzioni di sistema nelle esperienze seguenti:

- [Threat Explorer/Rilevamenti in tempo reale in Defender per Office 365 piano 2](threat-explorer.md)
- Pagina [Entità e-mail in Esplora minacce/Rilevamenti in tempo reale](mdo-email-entity-page.md)
- Rapporto [sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report)
- [Ricerca avanzata in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Visualizzazioni campagna](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla **pagina Recapito avanzato,** aprire <https://security.microsoft.com/advanceddelivery> .

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare o rimuovere le impostazioni configurate nel criterio di  recapito avanzato, è necessario essere membri del  gruppo di ruoli Amministratore della sicurezza nel portale **di Microsoft 365 Defender** e membri del gruppo di ruoli Gestione organizzazione in **Exchange Online**.  
  - Per l'accesso in sola lettura ai criteri di recapito avanzati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > L'aggiunta di utenti al ruolo Azure Active Directory corrispondente offre agli utenti  le autorizzazioni necessarie nel portale Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Utilizzare il portale Microsoft 365 Defender per configurare le cassette postali SecOps nel criterio di recapito avanzato

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.

2. Nella pagina **Recapito avanzato** verificare che la scheda Cassetta postale **SecOps** sia selezionata e quindi eseguire una delle operazioni seguenti:
   - Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.
   - Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**

3. Nel riquadro a comparsa Modifica cassette postali **SecOps** visualizzato, immettere una cassetta postale di Exchange Online esistente che si desidera designare come cassetta postale SecOps eseguendo una delle operazioni seguenti:
   - Fare clic nella casella, lasciare che l'elenco delle cassette postali si risolva e quindi selezionare la cassetta postale.
   - Fare clic nella casella iniziare a digitare un identificatore per la cassetta postale (nome, nome visualizzato, alias, indirizzo di posta elettronica, nome account e così via) e selezionare la cassetta postale (nome visualizzato) dai risultati.

     Ripetere questo passaggio tutte le volte necessarie. I gruppi di distribuzione non sono consentiti.

     Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

4. Al termine, scegliere **Salva**.

Le voci della cassetta postale SecOps configurate vengono visualizzate nella scheda Cassetta postale **SecOps.** Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Usare il portale Microsoft 365 Defender per configurare simulazioni di phishing di terze parti nel criterio di recapito avanzato

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.

2. Nella pagina **Recapito avanzato** selezionare la scheda **Simulazione di phishing** e quindi eseguire una delle operazioni seguenti:
   - Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.
   - Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**

3. Nel riquadro **a comparsa Modifica simulazione di phishing** di terze parti visualizzato configurare le impostazioni seguenti:

   - **Dominio di** invio: espandere questa impostazione e immettere almeno un dominio dell'indirizzo di posta elettronica (ad esempio, contoso.com) facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. È possibile aggiungere fino a 10 voci.
   - **IP** di invio: espandere questa impostazione e immettere almeno un indirizzo IPv4 valido facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. È possibile aggiungere fino a 10 voci. I valori validi sono:
     - IP singolo: ad esempio, 192.168.1.1.
     - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
     - IP CIDR: ad esempio, 192.168.0.1/25.
   - URL di simulazione da **consentire:** espandere questa impostazione e facoltativamente immettere URL specifici che fanno parte della campagna di simulazione di phishing che non devono essere bloccati o detonati facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. È possibile aggiungere fino a 10 voci.

   Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

4. Al termine, eseguire una delle operazioni seguenti:
   - **Prima volta**: fare **clic su Aggiungi** e quindi su **Chiudi.**
   - **Modifica esistente**: fare clic **su Salva** e quindi su **Chiudi.**

Le voci di simulazione di phishing di terze parti configurate vengono visualizzate nella **scheda Simulazione di** phishing. Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Scenari aggiuntivi che richiedono il bypass del filtro

Oltre ai due scenari che possono essere utili per i criteri di recapito avanzati, esistono altri scenari che potrebbero richiedere l'esclusione del filtro:

- **Filtri di terze parti:** se il *record* MX del dominio non punta a Office 365 (i messaggi vengono instradati da un'altra [parte),](secure-by-default.md) la protezione per impostazione predefinita non *è disponibile.*

  Per ignorare il filtro Microsoft per i messaggi che sono già stati valutati dal filtro di terze parti, utilizzare le regole del flusso di posta (note anche come regole di trasporto). Per ulteriori informazioni, vedere [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsi positivi in** esame: è possibile consentire temporaneamente a Determinati messaggi ancora [](admin-submission.md) analizzati da Microsoft tramite invii da parte dell'amministratore di segnalare a Microsoft messaggi positivi noti erroneamente contrassegnati come non corretti (falsi positivi). Come per tutte le sostituzioni, è **_consigliabile_** che queste quote siano temporanee.
