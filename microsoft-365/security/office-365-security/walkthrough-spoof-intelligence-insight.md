---
title: Procedura dettagliata - Dati analitici spoof intelligence
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
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come funziona l'analisi dell'intelligence spoofing. Possono determinare rapidamente quali mittenti inviano legittimamente messaggi di posta elettronica nelle proprie organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206773"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Procedura dettagliata - Informazioni dettagliate sulla spoofing intelligence in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con Defender per Office 365, è possibile usare le informazioni di spoofing intelligence per determinare rapidamente quali mittenti esterni stanno inviando legittimamente messaggi di posta elettronica non autenticati (messaggi da domini che non superano i controlli SPF, DKIM o DMARC).

Consentendo ai mittenti esterni noti di inviare messaggi falsificati da posizioni note, è possibile ridurre i falsi positivi (buona posta elettronica contrassegnata come non buona). Monitorando i mittenti falsificati consentiti, si fornisce un ulteriore livello di sicurezza per impedire l'arrivo di messaggi non sicuri nell'organizzazione.

Per ulteriori informazioni su report e informazioni dettagliate, vedere Report e informazioni dettagliate nel [Centro sicurezza & conformità.](reports-and-insights-in-security-and-compliance.md)

Questa procedura dettagliata è una delle diverse per il Centro sicurezza & conformità. Per informazioni sull'esplorazione di report e informazioni dettagliate, vedere le procedure dettagliate nella [sezione Argomenti](#related-topics) correlati.

> [!NOTE]
> L'analisi di spoof intelligence mostra i dati degli ultimi 7 giorni. Il [criterio di spoof intelligence](learn-about-spoof-intelligence.md) e il cmdlet [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) corrispondente in PowerShell di Exchange Online mostrano i dati degli ultimi 30 giorni. [Get-SpoofMailReport mostra](/powershell/module/exchange/get-spoofmailreport) i dati per un massimo di 90 giorni.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **Dashboard di** sicurezza, utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

  È possibile visualizzare le informazioni di intelligence spoofing da più dashboard nel Centro sicurezza & conformità. Indipendentemente dal dashboard visualizzato, le informazioni dettagliate forniscono gli stessi dettagli e consentono di eseguire rapidamente le stesse attività.

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - **Gestione organizzazione**
  - **Amministratore della sicurezza**
  - **Lettore sicurezza**
  - **Lettore globale**

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Nota:** l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di  Microsoft 365 offre agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Abilitare e disabilitare l'intelligence di spoofing nei criteri anti-phishing in Microsoft Defender per Office 365. L'intelligence di spoofing è abilitata per impostazione predefinita. Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Per usare spoof intelligence per monitorare e gestire i mittenti che inviano messaggi non autenticati, vedere [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Aprire le informazioni dettagliate sulla spoof intelligence nel Centro sicurezza & conformità

1. Nel Centro sicurezza & conformità passare a **Dashboard di gestione delle** \> **minacce.**

2. Nella riga **Insights** cercare uno degli elementi seguenti:

   - **Domini contraffatti probabilmente negli ultimi sette** giorni: questa informazione indica che l'intelligence di spoofing è abilitata (è abilitata per impostazione predefinita).
   - **Abilita protezione da spoofing**: questa informazione indica che l'intelligence di spoofing è disabilitata e fare clic sull'analisi consente di abilitare l'intelligence di spoofing.

3. Le informazioni dettagliate nel dashboard mostrano informazioni come queste:

   ![Screenshot of spoof intelligence insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Questa panoramica ha due modalità:

   - **Modalità di analisi:** se l'intelligence di spoofing è abilitata, le informazioni dettagliate mostrano quanti messaggi sono stati influenzati dalle funzionalità di spoof intelligence negli ultimi sette giorni.
   - **Cosa succede se la** modalità : se l'intelligence  di spoofing è disabilitata, le informazioni dettagliate mostrano quanti messaggi sarebbero stati influenzati dalle funzionalità di spoof intelligence negli ultimi sette giorni.

   In entrambi i casi, i domini contraffatti visualizzati nell'analisi sono suddivisi in due categorie: **domini** sospetti **e domini non sospetti.**

   - **I domini sospetti** includono:

     - Spoofing ad alta probabilità: in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, è molto probabile che i domini siano contraffatti e che i messaggi provenienti da questi domini siano più dannosi.

     - Spoofing di probabilità moderato: in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, siamo moderatamente sicuri che i domini siano contraffatti e che i messaggi inviati da questi domini siano legittimi. I falsi positivi sono più probabili in questa categoria rispetto allo spoofing ad alta probabilità.

   **Domini non sospetti:** il dominio non ha superato l'autenticazione esplicita della posta elettronica [controlla SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md). Tuttavia, il dominio ha superato i controlli impliciti di autenticazione della posta elettronica ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)). Di conseguenza, non è stata eseguita alcuna azione anti-spoofing sul messaggio.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sui domini sospetti dall'analisi dell'intelligence spoofing

1. Nella pagina Spoof intelligence insight fare clic **su Domini sospetti** o Domini **non** sospetti per passare alla pagina Spoof **intelligence insight.** La **pagina Informazioni di spoofing** intelligence contiene le informazioni seguenti:

   - **Dominio contraffatto**: Dominio dell'utente contraffatto visualizzato  nella casella Da nei client di posta elettronica. Questo indirizzo è noto anche come `5322.From` indirizzo.
   - **Infrastruttura**: nota anche come infrastruttura _di invio._ Dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine. Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).
   - **Numero messaggi**: numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il dominio contraffatto specificato negli ultimi 7 giorni.
   - **Last seen**: Data dell'ultima ricezione di un messaggio dall'infrastruttura di invio contenente il dominio contraffatto.
   - **Tipo spoof**: questo valore è **External.**
   - **Consentito lo spoofing?**: I valori visualizzati qui sono:
     - **Sì:** i messaggi provenienti dalla combinazione del dominio dell'utente contraffatto e dell'infrastruttura di invio sono consentiti e non considerati messaggi di posta elettronica contraffatti.
     - **No**: i messaggi provenienti dalla combinazione del dominio dell'utente contraffatto e dell'infrastruttura di invio vengono contrassegnati come contraffatti. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**).

     Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Selezionare un elemento nell'elenco per visualizzare i dettagli sulla coppia dominio/infrastruttura di invio in un riquadro a comparsa. Le informazioni includono:
   - Perché l'abbiamo preso.
   - Cosa è necessario fare.
   - Riepilogo del dominio.
   - WhoIs i dati sul mittente.
   - Messaggi simili che abbiamo visto nel tenant dallo stesso mittente.

   Da qui puoi anche scegliere di aggiungere o rimuovere la coppia dominio/infrastruttura di invio **dall'elenco Consenti spoofing** dei mittenti consentiti. È sufficiente impostare l'interruttore di conseguenza.

   ![Screenshot of a domain in the Spoof intelligence insight details pane](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Aggiunta di un dominio all'elenco Consenti spoofing

L'aggiunta di un dominio all'elenco Consenti spoofing dall'analisi di spoofing intelligence consente solo la combinazione del dominio contraffatto e *dell'infrastruttura* di invio. Non consente la posta elettronica dal dominio contraffatto da alcuna origine, né consente la posta elettronica dall'infrastruttura di invio per qualsiasi dominio.

Ad esempio, si consente al dominio seguente di effettuare lo spoofing nell'elenco Consenti spoofing:

- **Dominio**: gmail.com
- **Infrastruttura**: tms.mx.com

Solo la posta elettronica di tale coppia dominio/infrastruttura di invio sarà autorizzata a effettuare lo spoofing. Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti. I messaggi in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.

## <a name="related-topics"></a>Argomenti correlati

[Protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md)