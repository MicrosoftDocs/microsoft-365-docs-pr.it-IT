---
title: Come Office 365 convalida l'indirizzo mittente per impedire il phishing
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Per evitare il phishing, Office 365 e Outlook.com ora richiedono la conformità RFC per gli indirizzi da:.
ms.openlocfilehash: 39c9898a31c715487f3bc934ad0986e9a7b3679d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083445"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Come Office 365 convalida l'indirizzo mittente per impedire il phishing

Gli account di posta elettronica di Office 365 e Outlook.com ricevono un numero sempre più elevato di attacchi di phishing. Una tecnica utilizzata da phisher consiste nell'inviare messaggi con valori per l'indirizzo from: non conformi a [RFC 5322](https://tools.ietf.org/html/rfc5322). L'indirizzo from: è denominato anche indirizzo 5322. from. Per evitare questo tipo di phishing, Office 365 e Outlook.com richiedono messaggi ricevuti dal servizio per includere un indirizzo conforme a RFC da: Address, come descritto in questo articolo.
  
> [!NOTE]
> Le informazioni contenute in questo articolo richiedono una conoscenza di base del formato generale degli indirizzi di posta elettronica. Per ulteriori informazioni, vedere [rfc 5322](https://tools.ietf.org/html/rfc5322) (in particolare le sezioni 3.2.3, 3,4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), così come [RFC 3696](https://tools.ietf.org/html/rfc3696). Questo articolo riguarda l'applicazione dei criteri per l'indirizzo 5322. from. Questo articolo non riguarda l'indirizzo 5321. MailFrom. 
  
Purtroppo, esistono ancora alcuni server di posta elettronica legacy su Internet che continuano a inviare messaggi di posta elettronica "legittimi" che dispongono di un indirizzo mancante o non valido: Se si ricevono regolarmente messaggi di posta elettronica da organizzazioni che utilizzano questi sistemi legacy, incoraggiare tali organizzazioni a aggiornare i propri server di posta elettronica in modo che siano conformi agli standard di sicurezza moderni.
  
Microsoft inizierà a implementare l'applicazione dei criteri descritti in questo articolo il 9 novembre 2017.
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>In che modo Office 365 applica l'utilizzo di un indirizzo valido da: per impedire attacchi di phishing

Office 365 sta apportando modifiche al modo in cui applica l'utilizzo dell'indirizzo from: nei messaggi ricevuti per garantire una maggiore protezione dagli attacchi di phishing. Contenuto dell'articolo:
  
- [Tutti i messaggi devono includere un indirizzo valido da:](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Formato dell'indirizzo from: se non si include un nome visualizzato](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [Formato dell'indirizzo from: se si include un nome visualizzato](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [Esempi aggiuntivi di indirizzi validi e non validi:](how-office-365-validates-the-from-address.md#Examples)
    
- [Sopprimere le risposte automatiche al dominio personalizzato senza interrompere il criterio da:](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Override di Office 365 da: criteri di applicazione degli indirizzi](how-office-365-validates-the-from-address.md#Override)
    
- [Altri modi per prevenire e proteggere i reati informatici in Office 365](how-office-365-validates-the-from-address.md#OtherProtection)
    
L'invio per conto di un altro utente non è influenzato da questa modifica, per ulteriori informazioni, leggere il Blog di Terry zinco "[cosa si intende quando si fa riferimento al ' mittente ' di un messaggio di posta elettronica?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".
  
### <a name="all-messages-must-include-a-valid-from-address"></a>Tutti i messaggi devono includere un indirizzo valido da:
<a name="MustIncludeFromAddress"> </a>

Alcuni messaggi automatici non includono un indirizzo da: quando vengono inviati. In passato, quando Office 365 o Outlook.com ha ricevuto un messaggio senza un indirizzo from:, il servizio ha aggiunto il seguente indirizzo predefinito da: Address al messaggio per renderlo risultato finale:
  
```
From: <>
```

A partire dal 9 novembre 2017, Office 365 distribuirà le modifiche apportate ai propri datacenter e ai server di posta che applicano una nuova regola in cui i messaggi senza un indirizzo da: non verranno più accettati da Office 365 o Outlook.com. Al contrario, tutti i messaggi ricevuti da Office 365 devono già contenere un indirizzo valido da:. In caso contrario, il messaggio verrà inviato alla cartella posta indesiderata o agli elementi eliminati in Outlook.com e Office 365. 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Panoramica della sintassi: formato valido per l'indirizzo da: per Office 365
<a name="SyntaxOverviewFromAddress"> </a>

Il formato per il valore dell'indirizzo from: è definito in dettaglio tra diverse RFC. Sono presenti molte varianti sull'indirizzamento e su ciò che può essere considerato valido o non valido. Per semplificare le operazioni, Microsoft consiglia di utilizzare il formato e le definizioni seguenti:
  
```
From: "displayname " <emailaddress >
```

Dove:
  
- Optional  *DisplayName* è una frase che descrive il proprietario dell'indirizzo di posta elettronica. Ad esempio, questo potrebbe essere un nome più facile da usare per descrivere il mittente rispetto al nome della cassetta postale. L'utilizzo di un nome visualizzato è facoltativo. Tuttavia, se si sceglie di utilizzare un nome visualizzato, Microsoft consiglia di racchiuderlo sempre tra virgolette, come mostrato nella figura. 
    
- Necessari  *EmailAddress* è costituito da: 
    
  ```
  local-part @domain
  ```

    Dove:
    
  - Necessari  *local-part* è una stringa che identifica la cassetta postale associata all'indirizzo. Questo è univoco all'interno del dominio. Spesso, il nome utente o il GUID del proprietario della cassetta postale viene utilizzato come valore per la parte locale. 
    
  - Necessari  *Domain* è il nome di dominio completo (FQDN) del server di posta che ospita la cassetta postale identificata dalla parte locale dell'indirizzo di posta elettronica. 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Formato dell'indirizzo from: se non si include un nome visualizzato
<a name="FormatNoDisplayName"> </a>

Un indirizzo in formato appropriato che non include un nome visualizzato include solo un singolo indirizzo di posta elettronica con o senza parentesi angolari. Microsoft consiglia di non separare le parentesi angolari con gli spazi. Inoltre, non includere nulla dopo l'indirizzo di posta elettronica.
  
Gli esempi seguenti sono validi:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

L'esempio che segue è valido ma non consigliato perché contiene spazi tra le parentesi angolari e l'indirizzo di posta elettronica:
  
```
From: < sender@contoso.com >
```

L'esempio che segue non è valido perché contiene testo dopo l'indirizzo di posta elettronica:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Formato dell'indirizzo from: se si include un nome visualizzato
<a name="FormatDisplayName"> </a>

Per gli indirizzi da: che includono un valore per il nome visualizzato, si applicano le regole seguenti:
  
- Se l'indirizzo del mittente include un nome visualizzato e il nome visualizzato include una virgola, il nome visualizzato deve essere racchiuso tra virgolette. Ad esempio:
    
    L'esempio seguente è valido:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    L'esempio seguente non è valido:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    Non è necessario racchiudere il nome visualizzato tra virgolette se il nome visualizzato include una virgola non è valido in base a RFC 5322.
    
    Come procedura consigliata, inserire i contrassegni di virgolette attorno al nome visualizzato indipendentemente dal fatto che esista o meno una virgola all'interno del nome visualizzato.
    
- Se l'indirizzo del mittente include un nome visualizzato, l'indirizzo di posta elettronica deve essere racchiuso tra parentesi angolari.
    
    Come procedura consigliata, Microsoft consiglia di inserire uno spazio tra il nome visualizzato e l'indirizzo di posta elettronica.
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Esempi aggiuntivi di indirizzi validi e non validi:
<a name="Examples"> </a>

- Valido
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Non valido. L'indirizzo di posta elettronica non è racchiuso tra parentesi uncinate:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- Valido, ma non consigliato. Il nome visualizzato non è incluso tra virgolette. Come procedura consigliata, inserire sempre le virgolette attorno al nome visualizzato:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- Non valido. Tutto è racchiuso tra virgolette, non solo il nome visualizzato:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Non valido. Non ci sono parentesi angolari attorno all'indirizzo di posta elettronica:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Non valido. Non c'è spazio tra il nome visualizzato e la parentesi uncinata sinistra:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- Non valido. Non vi sono spazi tra le virgolette di chiusura attorno al nome visualizzato e la parentesi angolare sinistra.
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Sopprimere le risposte automatiche al dominio personalizzato senza interrompere il criterio da:
<a name="SuppressAutoReply"> </a>

Con il nuovo da: applicazione dei criteri, non è più possibile utilizzare da: \< \> per sopprimere le risposte automatiche. Al contrario, è necessario configurare un record MX null per il dominio personalizzato.
  
Il record MX (Mail Exchanger) è un record di risorse in DNS che identifica il server di posta elettronica che riceve la posta per il dominio. Le risposte automatiche (e tutte le risposte) sono naturalmente soppressi perché non esiste alcun indirizzo pubblicato a cui il server che risponde può inviare messaggi.
  
Quando si configura un record MX null per il dominio personalizzato:
  
- Scegliere un dominio da cui inviare i messaggi che non accettano (ricevono) la posta elettronica. Ad esempio, se il dominio principale è contoso.com, è possibile scegliere noreply.contoso.com.
    
- Configurare il record MX null per il dominio. Un record MX null è costituito da un singolo punto, ad esempio:
    
  ```
  noreply.contoso.com IN MX .
  ```

Per ulteriori informazioni sulla pubblicazione di un MX null, vedere [RFC 7505](https://tools.ietf.org/html/rfc7505).
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Override di Office 365 da: criteri di applicazione degli indirizzi
<a name="Override"> </a>

Una volta che il nuovo criterio è stato completato, è possibile ignorare questo criterio solo per la posta in ingresso ricevuta da Office 365 utilizzando uno dei metodi seguenti: 
  
- Elenchi di indirizzi IP consentiti
    
- Regole del flusso di posta di Exchange Online
    
Microsoft consiglia vivamente di eseguire l'override dell'applicazione del criterio from:. L'override di questo criterio può aumentare il rischio di esposizione da parte dell'organizzazione alla posta indesiderata, al phishing e ad altri reati informatici.
  
Non è possibile eseguire l'override di questo criterio per la posta in uscita inviata in Office 365. Inoltre, Outlook.com non consentirà sostituzioni di alcun tipo, anche tramite supporto. 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Altri modi per prevenire e proteggere i reati informatici in Office 365
<a name="OtherProtection"> </a>

Per ulteriori informazioni su come rafforzare la propria organizzazione contro i reati informatici, quali phishing, spamming, violazioni dei dati e altre minacce, vedere [procedure consigliate per la sicurezza per Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).
  
## <a name="related-topics"></a>Argomenti correlati

[Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

