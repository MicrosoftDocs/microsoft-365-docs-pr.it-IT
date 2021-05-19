---
title: Informazioni dettagliate sulla rappresentazione
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come funzionano le informazioni dettagliate sulla rappresentazione. Possono determinare rapidamente quali mittenti inviano legittimamente messaggi di posta elettronica nelle proprie organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535769"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Informazioni dettagliate sulla rappresentazione in Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.

La rappresentazione è il punto in cui il mittente di un messaggio di posta elettronica è molto simile a un indirizzo di posta elettronica mittente reale o previsto. Gli utenti malintenzionati spesso imitavano gli indirizzi di posta elettronica dei mittenti nel phishing o in altri tipi di attacchi nel tentativo di ottenere l'attendibilità del destinatario. Esistono fondamentalmente due tipi di rappresentazione:

- **Rappresentazione di dominio**: anziché lila@contoso.com, l'indirizzo di posta elettronica del mittente rappresentato è lila@ćóntoso.com.
- **Rappresentazione utente**: anziché michelle@contoso.com, l'indirizzo di posta elettronica del mittente rappresentato è rnichell@contoso.com.

La rappresentazione del dominio è diversa [dallo spoofing del](anti-spoofing-protection.md)dominio, perché il dominio rappresentato è in genere un dominio reale registrato. I messaggi provenienti dai mittenti nel dominio rappresentato possono e spesso superare controlli regolari di autenticazione della posta elettronica che altrimenti identificherebbero i tentativi di spoofing (SPF, DKIM e DMARC).

La protezione della rappresentazione fa parte delle impostazioni dei criteri anti-phishing) che sono esclusive di Microsoft Defender per Office 365. Per ulteriori informazioni su queste impostazioni, vedere Impostazioni di rappresentazione nei criteri [anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

È possibile utilizzare le informazioni dettagliate sulla rappresentazione per identificare rapidamente i messaggi provenienti da mittenti o domini mittenti impersonati configurati per la protezione della rappresentazione.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alle informazioni dettagliate sulla rappresentazione nella **pagina Anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - **Gestione organizzazione**
  - **Amministratore della sicurezza**
  - **Ruolo con autorizzazioni di lettura per la sicurezza**
  - **Lettore globale**

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre  agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Abiliti e configura la protezione dalla rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365. La protezione della rappresentazione non è abilitata per impostazione predefinita. Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a>Aprire le informazioni dettagliate sulla rappresentazione nel Centro sicurezza & conformità

1. Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**

2. Nella pagina principale **Anti-phishing,** l'analisi della rappresentazione è simile alla seguente:

   Questa panoramica ha due modalità:

    - **Modalità insight:** se la protezione della rappresentazione è abilitata e configurata in qualsiasi criterio anti-phishing, l'analisi mostra il numero di messaggi rilevati dai mittenti impersonati negli ultimi sette giorni. Questo è il totale di tutti i mittenti impersonati rilevati da tutti i criteri anti-phishing.
    - What **if mode**: Se la protezione della rappresentazione non è abilitata e  configurata in qualsiasi criterio anti-phishing attivo, le informazioni dettagliate mostrano quanti messaggi sarebbero stati rilevati dalle funzionalità di protezione della rappresentazione negli ultimi sette giorni.

   In entrambi i modi, **Domains impersonated** mostra il numero di messaggi provenienti da mittenti in domini protetti, mentre **Users impersonated** mostra il numero di messaggi provenienti da utenti protetti.

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Visualizzare informazioni sui messaggi provenienti da mittenti in domini impersonati

Nella pagina Informazioni dettagliate sulla rappresentazione fare clic **su Domini impersonati.** La **pagina Informazioni dettagliate** sulla rappresentazione visualizzata contiene le informazioni seguenti:

- **Dominio mittente**: Dominio di rappresentazione, ovvero il dominio utilizzato per inviare il messaggio di posta elettronica. 
- **Numero messaggi**: numero di messaggi provenienti dal dominio del mittente che rappresenta il dominio negli ultimi 7 giorni.
- **Tipo di rappresentazione:** questo valore indica la posizione rilevata della rappresentazione , ad esempio **Dominio nell'indirizzo**.
- **Dominio rappresentato:** il dominio rappresentato, che dovrebbe essere simile al dominio configurato per la protezione della rappresentazione nel criterio anti-phishing.
- **Tipo di dominio:** questo valore è **Dominio aziendale** per i domini interni o **Dominio personalizzato** per i domini personalizzati.
- **Criterio**: Criterio anti-phishing che ha rilevato il dominio rappresentato.
- **Allowed to impersonate**: Uno dei valori seguenti:
  - **Sì:** il dominio è stato configurato come dominio trusted (eccezione per la protezione della rappresentazione) nel criterio di protezione da posta indesiderata. I messaggi provenienti dai mittenti nel dominio rappresentato sono stati rilevati, ma sono consentiti.
  - **No**: il dominio è stato configurato per la protezione della rappresentazione nel criterio di protezione da posta indesiderata. I messaggi provenienti da mittenti nel dominio rappresentato sono stati rilevati e agiti in base all'azione per i domini impersonati nel criterio di protezione da posta indesiderata.

È possibile fare clic su intestazioni di colonna selezionate per ordinare i risultati.

Per filtrare i risultati, è possibile utilizzare la casella **Dominio** filtro per immettere un elenco di valori delimitati da virgole per filtrare i risultati.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Visualizzare i dettagli sui messaggi provenienti dai mittenti nei domini impersonati

Nella pagina **Informazioni dettagliate sulla rappresentazione** selezionare una delle righe disponibili. Il riquadro a comparsa dei dettagli visualizzato contiene le informazioni e le caratteristiche seguenti:

- **Criteri di rappresentazione della selezione da modificare:** selezionare il criterio anti-phishing interessato che si desidera modificare. Sono disponibili solo i criteri in cui il dominio rappresentato è definito nel criterio. Fare riferimento alla pagina precedente per vedere quale criterio era effettivamente responsabile del rilevamento del dominio rappresentato (probabilmente in base al destinatario e alla priorità del criterio).

- **Aggiungi all'elenco** di rappresentazione consentiti : utilizzare questo  interruttore per aggiungere o rimuovere il mittente dai mittenti e dai domini attendibili (eccezioni di rappresentazione) per il criterio anti-phishing selezionato:
  - Se il **valore di Allowed to impersonate** per questa voce è **No,** l'interruttore è disattivato. Per escludere tutti i mittenti in questo dominio dalla valutazione per protezione dalla rappresentazione, fai scorrere l'interruttore su Attiva: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva. Il dominio viene aggiunto **all'elenco Domini attendibili** nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.
  - Se il **valore consentito per rappresentare questa** voce è **Sì,** l'interruttore è attivato. Per restituire tutti i mittenti in questo dominio alla valutazione tramite protezione della rappresentazione, fai scorrere l'interruttore su Off: ![ Toggle off ](../../media/scc-toggle-off.png) . Il dominio viene rimosso **dall'elenco Domini attendibili** nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.

- Perché l'abbiamo preso.
- Cosa è necessario fare.
- Riepilogo del dominio che elenca il dominio rappresentato.
- WhoIs i dati sul mittente.
- Collegamento per aprire [Esplora minacce](threat-explorer.md) per visualizzare ulteriori dettagli sul mittente.
- Messaggi simili provenienti dallo stesso mittente recapitati all'organizzazione.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Visualizzare informazioni sui messaggi provenienti da mittenti impersonati

In Informazioni dettagliate sulla rappresentazione fare clic **su Utenti impersonati**. La **pagina Informazioni dettagliate** sulla rappresentazione visualizzata contiene le informazioni seguenti:

- **Sender**: Indirizzo di posta elettronica del mittente che ha inviato il messaggio di posta elettronica.
- **Conteggio messaggi**: numero di messaggi provenienti dal mittente che rappresenta il mittente negli ultimi 7 giorni.
- **Tipo di rappresentazione:** questo valore è **User in display name**.
- **Utenti impersonati:** l'indirizzo di posta elettronica del mittente rappresentato, che dovrebbe essere simile all'utente configurato per la protezione della rappresentazione nel criterio anti-phishing.
- **Tipo di utente**: Questo valore indica il tipo di protezione applicato (ad esempio, **Utente** protetto o Intelligence **cassetta postale).**
- **Criterio**: Criterio anti-phishing che ha rilevato il mittente rappresentato.
- **Allowed to impersonate**: Uno dei valori seguenti:
  - **Sì**: il mittente è stato configurato come utente attendibile (un'eccezione per la protezione dalla rappresentazione) nel criterio di protezione da posta indesiderata. I messaggi provenienti dal mittente rappresentato sono stati rilevati, ma sono consentiti.
  - **No**: il mittente è stato configurato per la protezione della rappresentazione nel criterio di protezione da posta indesiderata. I messaggi provenienti dal mittente rappresentato sono stati rilevati e agiti in base all'azione per gli utenti impersonati nel criterio di protezione da posta indesiderata.

È possibile fare clic su intestazioni di colonna selezionate per ordinare i risultati.

Per filtrare i risultati, è possibile utilizzare **la** casella Filtro mittente per immettere un elenco di valori delimitati da virgole per filtrare i risultati.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Visualizzare i dettagli sui messaggi provenienti da mittenti impersonati

Nella pagina **Informazioni dettagliate sulla rappresentazione** selezionare una delle righe disponibili. Il riquadro a comparsa dei dettagli visualizzato contiene le informazioni e le caratteristiche seguenti:

- **Criteri di rappresentazione della selezione da modificare:** selezionare il criterio anti-phishing interessato che si desidera modificare. Sono disponibili solo i criteri in cui il mittente rappresentato è definito nel criterio. Fare riferimento alla pagina precedente per vedere quale criterio è stato effettivamente responsabile del rilevamento del mittente rappresentato (probabilmente in base al destinatario e alla priorità del criterio).

- **Aggiungi all'elenco** di rappresentazione consentiti : utilizzare questo  interruttore per aggiungere o rimuovere il mittente dai mittenti e dai domini attendibili (eccezioni di rappresentazione) per il criterio anti-phishing selezionato:
  - Se il **valore di Allowed to impersonate** per questa voce è **No,** l'interruttore è disattivato. Per escludere il mittente dalla valutazione per protezione dalla rappresentazione, fai scorrere l'interruttore su Attiva: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva. Il mittente viene aggiunto **all'elenco Utenti** attendibili nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.
  - Se il **valore consentito per rappresentare questa** voce è **Sì,** l'interruttore è attivato. Per restituire il mittente alla valutazione tramite la protezione della rappresentazione, fai scorrere l'interruttore su off: ![ Toggle off ](../../media/scc-toggle-off.png) . Il mittente viene rimosso **dall'elenco Utenti** attendibili nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.

- Perché l'abbiamo preso.
- Cosa è necessario fare.
- Riepilogo del mittente che elenca il mittente rappresentato.
- WhoIs i dati sul mittente.
- Collegamento per aprire [Esplora minacce](threat-explorer.md) per visualizzare ulteriori dettagli sul mittente.
- Messaggi simili provenienti dallo stesso mittente recapitati all'organizzazione.
