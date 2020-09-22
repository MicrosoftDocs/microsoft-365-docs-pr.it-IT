---
title: Come EOP convalida l'indirizzo del mittente per impedire il phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui tipi di indirizzi di posta elettronica accettati o rifiutati da Exchange Online Protection (EOP) e Outlook.com per evitare il phishing.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196060"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Come EOP convalida l'indirizzo del mittente per impedire il phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Gli attacchi di phishing rappresentano una minaccia costante per qualsiasi organizzazione di posta elettronica. Oltre a utilizzare [gli indirizzi di posta elettronica del mittente falsificati (falsificati)](anti-spoofing-protection.md), gli utenti malintenzionati utilizzano spesso valori nell'indirizzo from che violano gli standard di Internet. Per evitare questo tipo di phishing, Exchange Online Protection (EOP) e Outlook.com ora richiedono che i messaggi in ingresso includano un indirizzo conforme a RFC, come descritto in questo argomento. Questo Enforcement è stato abilitato nel novembre 2017.

**Note**:

- Se si ricevono regolarmente messaggi di posta elettronica provenienti da organizzazioni che hanno indirizzi non corretti come descritto in questo argomento, incoraggiare queste organizzazioni a aggiornare i propri server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.

- Il campo mittente correlato (utilizzato da Send per conto e mailing list) non è influenzato da questi requisiti. Per ulteriori informazioni, vedere il post di Blog seguente: [che cosa si intende quando si fa riferimento al ' mittente ' di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>Panoramica degli standard dei messaggi di posta elettronica

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in [rfc 5321](https://tools.ietf.org/html/rfc5321)e l'intestazione del messaggio è descritta in [RFC 5322](https://tools.ietf.org/html/rfc5322). I destinatari non vedono mai la busta reale del messaggio perché viene generata dal processo di trasmissione del messaggio e non è in realtà parte del messaggio.

- L'indirizzo `5321.MailFrom` (noto anche come indirizzo di **posta elettronica** , mittente P1 o mittente busta) è l'indirizzo di posta elettronica utilizzato per la trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (sebbene sia possibile che il mittente designi un indirizzo di posta elettronica diverso per il **percorso restituito** ).

- L'indirizzo di posta `5322.From` elettronica del mittente viene visualizzato nei client di posta elettronica (noto anche come indirizzo da o mittente P2) e è l'indirizzo di posta elettronica nel campo dell'intestazione **from** . L'indirizzo mittente è lo stato attivo dei requisiti di questo argomento.

L'indirizzo from è definito dettagliatamente in più RFC, ad esempio le sezioni di RFC 5322 3.2.3, 3,4 e 3.4.1 e [rfc 3696](https://tools.ietf.org/html/rfc3696). Sono presenti molte varianti sull'indirizzamento e su ciò che è considerato valido o non valido. Per semplificare le operazioni, è consigliabile utilizzare il formato e le definizioni seguenti:

`From: "Display Name" <EmailAddress>`

- **Nome visualizzato**: una frase facoltativa che descrive il proprietario dell'indirizzo di posta elettronica.

  - È consigliabile racchiudere sempre il nome visualizzato tra virgolette doppie ("), come mostrato nell'esempio. Se il nome visualizzato contiene una virgola, è _necessario_ racchiudere la stringa tra virgolette doppie per RFC 5322.
  - Se l'indirizzo from include un nome visualizzato, il valore EmailAddress deve essere racchiuso tra parentesi angolari (< >) come illustrato.
  - Microsoft consiglia vivamente di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.

- **EmailAddress**: l'indirizzo di posta elettronica utilizza il formato seguente `local-part@domain` :

  - **local-part**: una stringa che identifica la cassetta postale associata all'indirizzo. Questo valore è univoco all'interno del dominio. Spesso, viene utilizzato il nome utente o il GUID del proprietario della cassetta postale.
  - **dominio**: il nome di dominio completo (FQDN) del server di posta elettronica che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica.

  Di seguito sono riportate alcune considerazioni aggiuntive relative al valore EmailAddress:

  - Un solo indirizzo di posta elettronica.
  - Si consiglia di non separare le parentesi angolari con gli spazi.
  - Non includere testo aggiuntivo dopo l'indirizzo di posta elettronica.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Esempi di indirizzi validi e non validi

Gli indirizzi di posta elettronica seguenti sono validi:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Non consigliato perché esistono spazi tra le parentesi angolari e l'indirizzo di posta elettronica).

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Non consigliato perché il nome visualizzato non è racchiuso tra virgolette doppie).

Gli indirizzi di posta elettronica seguenti non sono validi:

- **Nessun indirizzo**: alcuni messaggi automatici non includono un indirizzo mittente. In passato, quando Microsoft 365 o Outlook.com ha ricevuto un messaggio senza indirizzo mittente, il servizio ha aggiunto l'indirizzo predefinito seguente: per rendere il messaggio risultato finale:

  `From: <>`

  A questo punto, i messaggi con un indirizzo vuoto non vengono più accettati.

- `From: Microsoft 365 sender@contoso.com` (Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari).

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Testo dopo l'indirizzo di posta elettronica).

- `From: Sender, Example <sender.example@contoso.com>` Il nome visualizzato contiene una virgola, ma non è racchiuso tra virgolette doppie.

- `From: "Microsoft 365 <sender@contoso.com>"` (L'intero valore viene racchiuso in modo errato tra virgolette doppie).

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Il nome visualizzato è presente, ma l'indirizzo di posta elettronica non è racchiuso tra parentesi angolari).

- `From: Microsoft 365<sender@contoso.com>` (Nessuna spaziatura tra il nome visualizzato e la parentesi uncinata sinistra).

- `From: "Microsoft 365"<sender@contoso.com>` (Nessuna spaziatura tra le virgolette doppie di chiusura e la parentesi angolare sinistra).

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Sopprimere le risposte automatiche al dominio personalizzato

Non è possibile utilizzare il valore `From: <>` per sopprimere le risposte automatiche. Al contrario, è necessario configurare un record MX null per il dominio personalizzato. Le risposte automatiche (e tutte le risposte) sono naturalmente soppressi perché non esiste alcun indirizzo pubblicato a cui il server che risponde può inviare messaggi.

- Scegliere un dominio di posta elettronica che non sia in grado di ricevere posta elettronica. Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.

- Il record MX null per questo dominio è costituito da un singolo punto.

Ad esempio:

```text
noreply.contoso.com IN MX .
```

Per ulteriori informazioni sulla configurazione dei record MX, vedere [creare record DNS presso qualsiasi provider di hosting DNS per Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Sostituzione dall'applicazione degli indirizzi

Per ignorare i requisiti di indirizzo per la posta elettronica in ingresso, è possibile utilizzare l'elenco indirizzi IP consentiti (filtro connessioni) o il flusso di posta (note anche come regole di trasporto) come descritto in [creare elenchi di mittenti attendibili in Microsoft 365](create-safe-sender-lists-in-office-365.md).

Non è possibile eseguire l'override dei requisiti degli indirizzi per la posta elettronica in uscita inviata da Microsoft 365. Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite supporto.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Altri modi per prevenire e proteggere i reati informatici in Microsoft 365

Per ulteriori informazioni su come è possibile rafforzare la propria organizzazione contro il phishing, la posta indesiderata, le violazioni dei dati e altre minacce, vedere [Top 10 modi per proteggere i piani Microsoft 365 for business](../../admin/security-and-compliance/secure-your-business-data.md).
