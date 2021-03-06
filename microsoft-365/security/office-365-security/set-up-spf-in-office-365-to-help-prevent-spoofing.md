---
title: Configurazione di SPF per evitare lo spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come aggiornare un record DNS (Domain Name Service) per usare un Sender Policy Framework (SPF) con il dominio personalizzato in Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 828d76b95a1e3f8d1a1851121d28603a1922f486
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538988"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configurazione di SPF per evitare lo spoofing

- [Prerequisiti](#prerequisites)
- [Creare o aggiornare il record TXT SPF](#create-or-update-your-spf-txt-record)
- [Come gestire i sottodomini](#how-to-handle-subdomains)
- [Risoluzione dei problemi relativi a SPF](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

In questo articolo viene descritto come aggiornare un record DNS (Domain Name Service) affinché sia possibile utilizzare l'autenticazione della posta elettronica di Sender Policy Framework (SPF) con il dominio personalizzato in Office 365.

SPF consente di *convalidare* la posta elettronica in uscita inviata dal dominio personalizzato (proviene da chi dice di essere). Si tratta di un primo passaggio per configurare i metodi di autenticazione della posta elettronica consigliati completi di SPF, [DKIM](use-dkim-to-validate-outbound-email.md) e [DMARC](use-dmarc-to-validate-email.md).

- [Prerequisiti](#prerequisites)
- [Creare o aggiornare il record TXT SPF](#create-or-update-your-spf-txt-record)
  - [Come gestire i sottodomini](#how-to-handle-subdomains)
- [Cosa fa effettivamente l'autenticazione SPF della posta elettronica?](#what-does-spf-email-authentication-actually-do)
  - [Risoluzione dei problemi relativi a SPF](#troubleshooting-spf)
- [Altre informazioni su SPF](#more-information-about-spf)

## <a name="prerequisites"></a>Prerequisiti

> [!IMPORTANT]
> Si consiglia alle **piccole imprese** e agli utenti che non hanno familiarità con gli indirizzi IP o la configurazione DNS di contattare il proprio gestore di domini internet (p. es. GoDaddy, Bluehost, web.com), per ottenere assistenza con la *configurazione DNS di SPF* (e qualsiasi altro metodo di autenticazione della posta elettronica usato). <p> **Se non si usa un URL personalizzato** (e l'URL usato per Office 365 termina con **onmicrosoft.com**), SPF è già stato configurato nel servizio Office 365.

Iniziamo.

Il record TXT SPF per Office 365 verrà creato nel DNS esterno per qualsiasi dominio o sottodominio personalizzato. Sono necessarie alcune informazioni per creare il record. Raccogliere le seguenti informazioni:

- Il record TXT SPF per il proprio dominio personalizzato, se disponibile. Per le istruzioni, vedere [Raccogliere le informazioni necessarie per creare record DNS di Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).

- Passare ai server di messaggistica e individuare gli indirizzi IP esterni (necessari per tutti i server locali di messaggistica). Ad esempio, **131.107.2.200**.

- Nomi di dominio da utilizzare per tutti i domini di terze parti che è necessario includere nel record TXT SPF. In alcuni provider di posta inviata in massa sono impostati sottodomini da utilizzare per i clienti. Ad esempio, la società MailChimp ha configurato **servers.mcsv.net**.

- Stabilire quale regola di imposizione utilizzare per il record TXT SPF. La regola **-all** è raccomandata. Per informazioni dettagliate sulle altre opzioni di sintassi, vedere [Sintassi del record TXT SPF per Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Per utilizzare un dominio personalizzato, Office 365 richiede l'aggiunta di un record TXT Sender Policy Framework (SPF) al record DNS per prevenire spoofing.

## <a name="create-or-update-your-spf-txt-record"></a>Creare o aggiornare il record TXT SPF

1. Assicurarsi di avere familiarità con la sintassi SFP nella tabella seguente.

   ****

   |Elemento|Se si sta utilizzando...|Comune per i clienti?|Aggiungere...|
   |---|---|---|---|
   |1|Qualsiasi sistema di posta elettronica (obbligatorio)|Comune. Tutti i record TXT SPF devono iniziare con questo valore|`v=spf1`|
   |2|Exchange Online|Comune|`include:spf.protection.outlook.com`|
   |3|Solo per Exchange Online|Non comune|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Germania, solo Microsoft Cloud Germania|Non comune|`include:spf.protection.outlook.de`|
   |5|Un sistema di posta elettronica di terze parti|Non comune|`include:<domain_name>` <p> \<domain_name\> è il dominio del sistema di posta elettronica di terze parti.|
   |6|Sistema di posta locale. Ad esempio, di Exchange Online Protection insieme a un altro sistema di posta elettronica|Non comune|Utilizzarne uno per ogni sistema di posta elettronica aggiuntivo: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> e \<domain_name\> sono l'indirizzo IP e il dominio dell'altro sistema di posta che invia i messaggi per conto del dominio.|
   |7|Qualsiasi sistema di posta elettronica (obbligatorio)|Comune. Tutti i record TXT SPF finiscono con questo valore|`<enforcement rule>` <p> Può trattarsi di uno dei vari valori. Consigliamo il valore `-all`.|
   |

2. Se non è già stato fatto, costituire il record TXT SPF utilizzando la sintassi della tabella.

   Ad esempio, se l'utente è completamente ospitato in Office 365, che significa che non sono presenti server di posta elettronica locali, il record TXT SPF includerà le righe 1, 2 e 7 e si otterrà un risultato simile al seguente:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **L'esempio precedente è il record TXT SPF più comune**. Questo record funziona praticamente per tutti, indipendentemente dal fatto che il datacenter di Microsoft si trovi negli Stati Uniti, in Europa (Germania inclusa) o in un'altra area geografica.

   Tuttavia, se è stato acquistato Office 365 Germania, parte di Microsoft Cloud Germania, è necessario utilizzare l'istruzione inclusa dalla riga 4 anziché dalla riga 2. Ad esempio, se l'utente è completamente ospitato in Office 365 Germania, che significa che non sono presenti server di posta elettronica locali, il record TXT SPF includerà le righe 1, 4 e 7 e si otterrà un risultato simile al seguente:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Se l'utente è già distribuito in Office 365, dispone di record TXT SPF configurati per il dominio personalizzato e sta eseguendo la migrazione a Office 365 Germania, è necessario aggiornare il record TXT SPF. Per farlo, cambiare `include:spf.protection.outlook.com` in `include:spf.protection.outlook.de`.

3. Dopo aver creato il record TXT SPF, è necessario aggiornare il record in DNS. **È possibile avere un solo record TXT SPF per un dominio.** Se esiste un record TXT SPF, anziché aggiungere un nuovo record, è necessario aggiornare quello esistente. Passare a [Creare record DNS per Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) e quindi selezionare il collegamento relativo al proprio host DNS.

4. Verificare il record TXT SPF.

## <a name="how-to-handle-subdomains"></a>Come gestire i sottodomini

È importante tenere presente che *è necessario creare un record distinto per ogni sottodominio, in quanto i sottodomini non ereditano il record SPF del dominio di primo livello*.

Per tutti i domini e sottodomini è necessario un record SPF jolly (`*.`) per impedire agli utenti malintenzionati di inviare messaggi di posta elettronica che provengano da sottodomini inesistenti. Ad esempio:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Risoluzione dei problemi relativi a SPF

Se si hanno problemi con il record TXT SPF, vedere [Risoluzione dei problemi: procedure consigliate per SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="what-does-spf-email-authentication-actually-do"></a>Cosa fa effettivamente l'autenticazione SPF della posta elettronica?

SPF identifica quali server di posta elettronica sono autorizzati a inviare posta elettronica per conto dell'utente. In sostanza, SPF insieme a DKIM, DMARC e altre tecnologie supportate da Office 365 aiuta a prevenire spoofing e phishing. SPF viene aggiunto come un record TXT che viene utilizzato da DNS per identificare i server di posta elettronica che possono inviare posta elettronica per conto di un dominio personalizzato. I sistemi di posta elettronica del destinatario fanno riferimento al record TXT SPF per stabilire se un messaggio di un dominio personalizzato proviene da un server di messaggistica autorizzato.

Ad esempio, si supponga che il dominio personalizzato contoso.com utilizzi Office 365. Si aggiunge un record TXT SPF che elenca i server di messaggistica di Office 365 come server di posta elettronica legittimi per il dominio. Quando il server di messaggistica ricevente riceve un messaggio da joe@contoso.com, il server cerca il record TXT SPF per contoso.com e scopre se il messaggio è valido. Se il server di destinazione rileva che il messaggio proviene da un server di messaggistica di Office 365 diverso da quelli elencati nel record SPF, il server di posta di destinazione può scegliere di rifiutare il messaggio come posta indesiderata.

Inoltre, se nel dominio personalizzato non è presente un record TXT SPF, alcuni server di destinazione possono rifiutare il messaggio immediatamente. Ciò avviene perché il server di destinazione non può convalidare che il messaggio provenga da un server di messaggistica autorizzato.

Se la posta di Office 365 è già stata sincronizzata, i server di messaggistica Microsoft sono già stati inclusi nel sistema DNS come record TXT SPF. Tuttavia, esistono alcuni casi in cui è necessario aggiornare il record TXT SPF nel sistema DNS. Ad esempio:

- In precedenza, era necessario aggiungere un record SPF o TXT diverso al dominio personalizzato se si utilizzava SharePoint Online. Ciò non è più necessario. Questa modifica dovrebbe ridurre il rischio che i messaggi di notifica di SharePoint Online finiscano nella cartella Posta indesiderata. Aggiornare il record SPF o TXT se si sta raggiungendo il limite di 10 ricerche e si stanno visualizzando errori del tipo "limite di ricerche superato" e "troppi hop".

- Se si dispone di un ambiente ibrido con Office 365 ed Exchange in locale.

- Si intende configurare DKIM e DMARC (scelta consigliata).

## <a name="more-information-about-spf"></a>Per ulteriori informazioni su SPF

Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, dello spoofing, della risoluzione dei problemi e di come Office 365 supporta SPF, vedere [Come funziona SPF per impedire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-dkim-and-dmarc"></a>Passaggi successivi: DKIM e DMARC

 SPF è progettato per prevenire spoofing, ma esistono tecniche di spoofing che SPF non è in grado di evitare. Per difendersi da queste minacce, dopo aver configurato SPF è consigliabile configurare anche DKIM e DMARC per Office 365.

L'obiettivo dell'autenticazione [DKIM](use-dkim-to-validate-outbound-email.md) della posta elettronica è dimostrare che il contenuto del messaggio non è stato manomesso.

L'obiettivo dell'autenticazione [DMARC](use-dmarc-to-validate-email.md) della posta elettronica è assicurare che le informazioni SPF e DKIM corrispondano all'indirizzo Da.

 Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, vedere [Funzionamento di SPF per prevenire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

*Selezionare 'Questa pagina' in 'Feedback' se si ha un feedback su questa documentazione.*
