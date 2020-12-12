---
title: Procedura dettagliata-spoofing Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Gli amministratori possono sapere come funziona l'Insight di intelligence di spoofing. Possono determinare rapidamente quali mittenti stanno inviando messaggi di posta elettronica nelle loro organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 665745e940ea9547d57a1d7c47ff54eaae3756b7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659691"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Procedura dettagliata-spoofing Intelligence Insight in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con difensore per Office 365, è possibile utilizzare l'Insight Intelligence di spoofing per determinare rapidamente quali mittenti esterni stanno inviando legittimamente la posta elettronica non autenticata (messaggi provenienti da domini che non superano i controlli SPF, DKIM o DMARC).

Consentendo ai mittenti esterni noti di inviare messaggi falsificati da posizioni note, è possibile ridurre i falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo). Monitorando i mittenti autorizzati falsificati, è possibile fornire un ulteriore livello di sicurezza per impedire l'arrivo di messaggi non sicuri nell'organizzazione.

Per ulteriori informazioni sui report e sulle intuizioni, vedere [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Questa procedura dettagliata è una delle numerose per il Centro sicurezza & Compliance. Per informazioni sull'esplorazione di report e approfondimenti, vedere le procedure dettagliate nella sezione [argomenti correlati](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina del **dashboard di sicurezza** , utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

  È possibile visualizzare l'Insight di intelligence di spoofing da più di un dashboard nel centro sicurezza & Compliance. Indipendentemente dal dashboard che si sta esaminando, l'Insight fornisce gli stessi dettagli e consente di eseguire rapidamente le stesse attività.

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - **Gestione organizzazione**
  - **Amministratore della sicurezza**
  - **Lettore di sicurezza**
  - **Lettore globale**

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Nota**: l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro sicurezza & Compliance _e_ le autorizzazioni per altre caratteristiche in Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- È possibile abilitare e disabilitare l'intelligence spoof nei criteri di anti-phishing in Microsoft Defender per Office 365. L'intelligenza contraffatta è abilitata per impostazione predefinita. Per ulteriori informazioni, vedere [Configure anti-phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Per utilizzare l'intelligence spoof per monitorare e gestire i mittenti che inviano messaggi non autenticati, vedere [Configure Spoofing Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Aprire lo spoofing Intelligence Insight nel centro sicurezza & Compliance

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Dashboard.**

2. Nella riga **Insights** cercare uno degli elementi seguenti:

   - **Domini probabilmente contraffatti negli ultimi sette giorni**: questa intuizione indica che l'intelligence spoof è abilitata (è abilitata per impostazione predefinita).
   - **Abilitare la protezione da spoofing**: questa intuizione indica che la falsificazione dell'intelligenza è disabilitata e facendo clic su Insight è possibile abilitare l'intelligence contraffatta.

3. L'Insight sul dashboard Visualizza informazioni di questo tipo:

   ![Schermata di Insight Intelligence spoofing](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Questa intuizione ha due modalità:

   - **Modalità Insight**: se l'intelligence spoof è abilitata, l'Insight Visualizza il numero di messaggi che sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi sette giorni.
   - **Che cosa fare se la modalità**: se l'intelligence di spoofing è disabilitata, l'Insight mostrerà il numero *di messaggi che* sono stati influenzati dalle nostre funzionalità di intelligence spoof negli ultimi sette giorni.

   In entrambi i casi, i domini falsificati visualizzati nell'Insight sono separati in due categorie: **domini sospetti** e **domini non sospetti**.

   - I **domini sospetti** includono:

     - Spoof ad alta confidenza: sulla base dei modelli di invio storico e del Punteggio di reputazione dei domini, è estremamente sicuro che i domini siano spoofing e che i messaggi provenienti da questi domini abbiano maggiori probabilità di essere dannosi.

     - Falsificazione della confidenza moderata: in base ai modelli di invio cronologici e al Punteggio di reputazione dei domini, si è certi che i domini siano spoofing e che i messaggi inviati da questi domini siano legittimi. I falsi positivi sono più probabili in questa categoria rispetto alla falsificazione con attendibilità elevata.

   **Domini non sospetti**: il dominio non è riuscito per l'autenticazione esplicita della posta elettronica controlli [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). Tuttavia, il dominio ha superato i controlli di autenticazione della posta elettronica impliciti ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)). Di conseguenza, non è stata eseguita alcuna azione antispoofing sul messaggio.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sui domini sospetti da spoofing Intelligence Insight

1. Nell'Insight Intelligence spoofing, fare clic su **domini sospetti** o su **domini non sospetti** per accedere alla pagina di **Insight Intelligence di spoofing** . La pagina di **Insight Intelligence spoof** contiene le seguenti informazioni:

   - **Dominio contraffatto**: il dominio dell'utente falsificato visualizzato nella casella **da** nei client di posta elettronica. Questo indirizzo è noto anche come `5322.From` indirizzo.
   - **Infrastructure**: nota anche come _infrastruttura di invio_. Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine. Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).
   - **Conteggio messaggi**: il numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il dominio contraffatto specificato negli ultimi 7 giorni.
   - **Ultimo** aggiornamento: l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene il dominio contraffatto.
   - **Tipo di spoofing**: questo valore è **esterno**.
   - **Consentita la falsificazione?**: i valori visualizzati qui sono:
     - **Yes**: i messaggi provenienti dalla combinazione del dominio dell'utente contraffatto e dell'infrastruttura di invio sono consentiti e non vengono considerati come posta elettronica contraffatta.
     - **No**: i messaggi provenienti dalla combinazione del dominio dell'utente falsificato e dell'infrastruttura di invio sono contrassegnati come falsificati. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri di anti-phishing personalizzati (il valore predefinito è **spostamento messaggio nella cartella posta indesiderata**).

     Per ulteriori informazioni, vedere [Configure anti-phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Selezionare un elemento nell'elenco per visualizzare i dettagli relativi alla coppia di infrastruttura di dominio/invio in un riquadro a comparsa. Le informazioni includono:
   - Perché questo è stato rilevato.
   - Cosa devi fare.
   - Riepilogo di un dominio.
   - Dati WhoIs sul mittente.
   - Messaggi simili che sono stati visualizzati nel tenant dallo stesso mittente.

   Da qui, è anche possibile scegliere di aggiungere o rimuovere la coppia di domini/l'infrastruttura di invio dall'elenco dei mittenti consentiti **per spoofing** . È sufficiente impostare l'interruttore di conseguenza.

   ![Schermata di un dominio nel riquadro dei dettagli dell'analisi di intelligence di spoofing](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Aggiunta di un dominio all'elenco consentiti per la falsificazione

L'aggiunta di un dominio all'elenco consentiti per la falsificazione da spoofing Intelligence Insight consente solo la combinazione del dominio contraffatto *e* l'infrastruttura di invio. Non consente la posta elettronica dal dominio contraffatto da qualsiasi origine, né consente la posta elettronica dall'infrastruttura di invio per qualsiasi dominio.

Ad esempio, il dominio seguente può essere consentito all'elenco dei messaggi consentiti per la falsificazione:

- **Dominio**: Gmail.com
- **Infrastruttura**: TMS.MX.com

Solo la posta elettronica da quel dominio/coppia di infrastruttura di invio sarà consentita per la falsificazione. Gli altri mittenti che tentano di falsificare gmail.com non sono consentiti. I messaggi in altri domini di tms.mx.com vengono controllati da spoofing Intelligence.

## <a name="related-topics"></a>Argomenti correlati

[Protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md)
