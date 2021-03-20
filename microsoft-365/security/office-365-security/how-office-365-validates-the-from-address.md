---
title: In che modo EOP convalida l'indirizzo From per impedire il phishing
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
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui tipi di indirizzi di posta elettronica accettati o rifiutati da Exchange Online Protection (EOP) e Outlook.com per prevenire il phishing.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71da944c02137024adda48434c5214695c54a817
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910679"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>In che modo EOP convalida l'indirizzo From per impedire il phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Gli attacchi di phishing sono una minaccia costante per qualsiasi organizzazione di posta elettronica. Oltre a usare indirizzi di posta elettronica mittenti [contraffatti](anti-spoofing-protection.md)(contraffatti), gli utenti malintenzionati spesso utilizzano valori nell'indirizzo mittente che violano gli standard Internet. Per evitare questo tipo di phishing, Exchange Online Protection (EOP) e Outlook.com ora richiedono che i messaggi in ingresso includano un indirizzo Mittente conforme a RFC, come descritto in questo articolo. Questa applicazione è stata abilitata a novembre 2017.

**Note**:

- Se si riceve regolarmente posta elettronica da organizzazioni con indirizzi From non validi come descritto in questo articolo, incoraggiare tali organizzazioni ad aggiornare i server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.

- Il campo Mittente correlato (utilizzato da Invia per conto di e liste di distribuzione) non è interessato da questi requisiti. Per ulteriori informazioni, vedere il post di blog seguente: Cosa si intende quando si fa riferimento al ["mittente" di un messaggio di posta elettronica?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).

## <a name="an-overview-of-email-message-standards"></a>Panoramica degli standard dei messaggi di posta elettronica

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in [RFC 5321](https://tools.ietf.org/html/rfc5321)e l'intestazione del messaggio è descritta in [RFC 5322](https://tools.ietf.org/html/rfc5322). I destinatari non vedono mai la busta effettiva del messaggio perché viene generata dal processo di trasmissione del messaggio e non fa effettivamente parte del messaggio.

- L'indirizzo (noto anche come indirizzo `5321.MailFrom` **MAIL FROM,** mittente P1 o mittente della busta) è l'indirizzo di posta elettronica utilizzato nella trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (anche se è possibile che il mittente designi un indirizzo di posta elettronica **Return-Path** diverso).

- L'indirizzo (noto anche come indirizzo mittente o mittente P2) è l'indirizzo di posta elettronica nel campo di intestazione Da ed è l'indirizzo di posta elettronica del mittente visualizzato nei client di posta `5322.From` elettronica.  L'indirizzo from è al centro dei requisiti di questo articolo.

L'indirizzo From è definito in dettaglio in diverse RFC (ad esempio, le sezioni RFC 5322 3.2.3, 3.4 e 3.4.1 e [RFC 3696).](https://tools.ietf.org/html/rfc3696) Esistono molte varianti per l'indirizzamento e ciò che viene considerato valido o non valido. Per semplicità, è consigliabile utilizzare il formato e le definizioni seguenti:

`From: "Display Name" <EmailAddress>`

- **Nome visualizzato**: frase facoltativa che descrive il proprietario dell'indirizzo di posta elettronica.

  - È consigliabile racchiudere sempre il nome visualizzato tra virgolette doppie (") come illustrato. Se il nome visualizzato contiene una virgola, _è_ necessario racchiudere la stringa tra virgolette doppie per RFC 5322.
  - Se l'indirizzo From include un nome visualizzato, il valore EmailAddress deve essere racchiuso tra parentesi angolari (< >) come illustrato.
  - Microsoft consiglia vivamente di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.

- **EmailAddress**: Un indirizzo di posta elettronica utilizza il formato `local-part@domain` :

  - **local-part**: stringa che identifica la cassetta postale associata all'indirizzo. Questo valore è univoco all'interno del dominio. Spesso viene utilizzato il nome utente o il GUID del proprietario della cassetta postale.
  - **domain**: nome di dominio completo (FQDN) del server di posta elettronica che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.

  Ecco alcune considerazioni aggiuntive per il valore EmailAddress:

  - Solo un indirizzo di posta elettronica.
  - È consigliabile non separare le parentesi angolari con spazi.
  - Non includere testo aggiuntivo dopo l'indirizzo di posta elettronica.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Esempi di indirizzi From validi e non validi

Gli indirizzi di posta elettronica from seguenti sono validi:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` Non consigliato perché sono presenti spazi tra le parentesi angolari e l'indirizzo di posta elettronica.

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` Non consigliato perché il nome visualizzato non è racchiuso tra virgolette doppie.

Gli indirizzi di posta elettronica from seguenti non sono validi:

- **No From address**: Alcuni messaggi automatizzati non includono un indirizzo Mittente. In passato, quando Microsoft 365 o Outlook.com riceveva un messaggio senza un indirizzo Mittente, il servizio aggiungeva il seguente indirizzo da predefinito: per rendere il messaggio recapitabile:

  `From: <>`

  A questo punto, i messaggi con un indirizzo Mittente vuoto non vengono più accettati.

- `From: Microsoft 365 sender@contoso.com` Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari.

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` Testo dopo l'indirizzo di posta elettronica.

- `From: Sender, Example <sender.example@contoso.com>` Il nome visualizzato contiene una virgola, ma non è racchiuso tra virgolette doppie.

- `From: "Microsoft 365 <sender@contoso.com>"` L'intero valore è racchiuso in modo errato tra virgolette doppie.

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari.

- `From: Microsoft 365<sender@contoso.com>` Nessuno spazio tra il nome visualizzato e la parentesi angolare sinistra.

- `From: "Microsoft 365"<sender@contoso.com>` Nessuno spazio tra le virgolette doppie di chiusura e la parentesi angolare sinistra.

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Eliminare le risposte automatiche al dominio personalizzato

Non è possibile utilizzare il valore `From: <>` per eliminare le risposte automatiche. Devi invece configurare un record MX null per il dominio personalizzato. Le risposte automatiche (e tutte le risposte) vengono naturalmente soppresse perché non esiste un indirizzo pubblicato a cui il server che risponde può inviare messaggi.

- Scegliere un dominio di posta elettronica che non può ricevere posta elettronica. Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.

- Il record MX null per questo dominio è costituito da un singolo punto.

Ad esempio:

```text
noreply.contoso.com IN MX .
```

Per ulteriori informazioni sulla configurazione dei record MX, vedere [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Eseguire l'override dell'imposizione degli indirizzi da

Per ignorare i requisiti dell'indirizzo mittente per la posta elettronica in ingresso, è possibile utilizzare l'elenco indirizzi IP consentiti (filtro connessioni) o le regole del flusso di posta (note anche come regole di trasporto) come descritto [in Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).

Non è possibile ignorare i requisiti dell'indirizzo mittente per la posta elettronica in uscita inviata da Microsoft 365. Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite il supporto.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Altri modi per prevenire e proteggere da crimini informatici in Microsoft 365

Per ulteriori informazioni su come rafforzare l'organizzazione contro phishing, posta indesiderata, violazioni dei dati e altre minacce, vedere [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).