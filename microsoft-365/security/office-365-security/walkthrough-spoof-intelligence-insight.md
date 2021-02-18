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
description: Gli amministratori possono scoprire come funziona l'intelligence spoofing. Possono determinare rapidamente quali mittenti stanno inviando legittimamente la posta elettronica alle proprie organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287972"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Procedura dettagliata: Informazioni dettagliate sull'intelligence per lo spoofing in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con Defender per Office 365, è possibile usare le informazioni dettagliate di Spoof intelligence per determinare rapidamente quali mittenti esterni inviano legittimamente messaggi di posta elettronica non autenticati (messaggi provenienti da domini che non superano i controlli SPF, DKIM o DMARC).

Consentendo ai mittenti esterni noti di inviare messaggi falsificati da posizioni note, è possibile ridurre i falsi positivi (messaggi di posta elettronica contrassegnati come non consentiti). Monitorando i mittenti falsificati consentiti, si fornisce un ulteriore livello di sicurezza per impedire l'arrivo di messaggi non sicuri nell'organizzazione.

Per ulteriori informazioni su report e informazioni dettagliate, vedere Report e informazioni dettagliate nel [Centro sicurezza & conformità.](reports-and-insights-in-security-and-compliance.md)

Questa procedura dettagliata è una delle diverse per il Centro sicurezza & conformità. Per informazioni sull'esplorazione di report e informazioni dettagliate, vedere le procedure dettagliate nella [sezione Argomenti](#related-topics) correlati.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla **pagina Dashboard di** sicurezza, utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

  È possibile visualizzare le informazioni di Spoof intelligence da più dashboard nel Centro sicurezza & conformità. Indipendentemente dal dashboard visualizzato, le informazioni dettagliate forniscono gli stessi dettagli e consentono di eseguire rapidamente le stesse attività.

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - **Gestione organizzazione**
  - **Amministratore della sicurezza**
  - **Lettore di sicurezza**
  - **Lettore globale**

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft  365 offre agli utenti le autorizzazioni necessarie nel Centro sicurezza & e conformità e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Abilitare e disabilitare spoof intelligence nei criteri anti-phishing in Microsoft Defender per Office 365. L'intelligence per lo spoofing è abilitata per impostazione predefinita. Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

- Per usare spoof intelligence per monitorare e gestire i mittenti che inviano messaggi non autenticati, vedere [Configurare spoof intelligence in Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Aprire le informazioni di spoof intelligence nel Centro sicurezza & conformità

1. Nel Centro sicurezza & conformità passare al dashboard **di gestione delle** \> **minacce.**

2. Nella riga **Insights** cercare uno degli elementi seguenti:

   - **Domini falsificati probabilmente negli ultimi sette giorni:** queste informazioni indicano che l'intelligence per lo spoofing è abilitata (è abilitata per impostazione predefinita).
   - **Abilitare la protezione da spoofing:** questa informazione indica che l'intelligence per lo spoofing è disabilitata e fare clic sulle informazioni dettagliate consente di abilitare lo spoof intelligence.

3. Le informazioni dettagliate nel dashboard mostrano informazioni come queste:

   ![Screenshot of spoof intelligence insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Queste informazioni dettagliate hanno due modalità:

   - **Modalità di analisi:** se l'intelligence per lo spoofing è abilitata, le informazioni dettagliate mostrano quanti messaggi sono stati influenzati dalle funzionalità di spoof intelligence degli ultimi sette giorni.
   - **Modalità what if:** se spoof intelligence è disabilitata,  le informazioni dettagliate mostrano quanti messaggi sarebbero stati influenzati dalle funzionalità di spoof intelligence negli ultimi sette giorni.

   In entrambi i casi, i domini falsificati visualizzati nelle informazioni dettagliate sono suddivisi in due **categorie:** domini sospetti **e domini non sospetti.**

   - **I domini sospetti** includono:

     - Spoofing ad alta probabilità: in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, siamo molto sicuri che i domini siano spoofing e i messaggi provenienti da questi domini sono più probabilmente dannosi.

     - Spoofing di confidenza moderato: in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, siamo moderatamente certi che i domini siano falsificati e che i messaggi inviati da questi domini siano legittimi. I falsi positivi sono più probabili in questa categoria rispetto allo spoofing ad alta probabilità.

   **Domini non sospetti:** il dominio non ha superato i controlli di autenticazione esplicita della posta elettronica [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC.](use-dmarc-to-validate-email.md) Tuttavia, il dominio ha superato i controlli impliciti di autenticazione della posta elettronica ([autenticazione composita).](email-validation-and-authentication.md#composite-authentication) Di conseguenza, non è stata eseguita alcuna azione anti-spoofing sul messaggio.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sui domini sospetti dalle informazioni di Spoof intelligence

1. Nella pagina Spoof intelligence insight, fare clic **su Domini sospetti** o Domini **non** sospetti per passare alla pagina Spoof **intelligence insight.** La **pagina Spoof Intelligence insight** contiene le informazioni seguenti:

   - **Dominio falsificato:** il dominio dell'utente falsificato visualizzato nella casella **Da** nei client di posta elettronica. Questo indirizzo è noto anche come `5322.From` indirizzo.
   - **Infrastruttura**: nota anche come infrastruttura _di invio._ Dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine. Se l'indirizzo IP di origine non dispone di un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).
   - **Numero di messaggi**: numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il dominio falsificato specificato negli ultimi 7 giorni.
   - **Ultimo messaggio visualizzato:** l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene il dominio falsificato.
   - **Tipo di spoofing:** questo valore è **Esterno.**
   - **Consentito lo spoofing?**: I valori visualizzati qui sono:
     - **Sì:** i messaggi provenienti dalla combinazione del dominio dell'utente falsificato e dell'infrastruttura di invio sono consentiti e non trattati come messaggi di posta elettronica falsificati.
     - **No:** i messaggi provenienti dalla combinazione del dominio dell'utente falsificato e dell'infrastruttura di invio vengono contrassegnati come falsificati. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta messaggio **nella cartella Posta indesiderata).**

     Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

2. Selezionare un elemento nell'elenco per visualizzare i dettagli sulla coppia dominio/infrastruttura di invio in un riquadro a comparsa. Le informazioni includono:
   - Perché l'abbiamo beccato.
   - Cosa è necessario fare.
   - Riepilogo del dominio.
   - WhoIs data about the sender.
   - Messaggi simili che abbiamo visto nel tenant dallo stesso mittente.

   Da qui è anche possibile scegliere di aggiungere o rimuovere la coppia dominio/infrastruttura di invio dall'elenco Consenti **spoofing** dei mittenti consentiti. È sufficiente impostare l'interruttore di conseguenza.

   ![Screenshot of a domain in the Spoof intelligence insight details pane](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Aggiunta di un dominio all'elenco Consentiti allo spoofing

L'aggiunta di un dominio all'elenco Di spoofing consentito dalle informazioni di spoof intelligence consente solo la combinazione del dominio falsificato e *dell'infrastruttura* di invio. Non consente la posta elettronica dal dominio falsificato da alcuna origine, né consente la posta elettronica dall'infrastruttura di invio per qualsiasi dominio.

Ad esempio, si consente al dominio seguente di accedere all'elenco Di spoofing consentiti:

- **Dominio**: gmail.com
- **Infrastruttura**: tms.mx.com

Solo la posta elettronica da tale coppia di infrastruttura di invio/dominio sarà autorizzata a effettuare lo spoofing. Altri mittenti che tentano di effettuare lo spoofing gmail.com non sono consentiti. I messaggi in altri domini provenienti tms.mx.com vengono controllati da spoof intelligence.

## <a name="related-topics"></a>Argomenti correlati

[Protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md)
