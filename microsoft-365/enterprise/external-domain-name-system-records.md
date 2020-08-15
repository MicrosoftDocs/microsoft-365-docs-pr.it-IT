---
title: Record Domain Name System (DNS) esterni per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: Un elenco di riferimento dei record dei nomi di dominio esterni da usare quando si pianifica una distribuzione di Office 365.
ms.openlocfilehash: da5a9a1095e50de779ee2fc148803e31583426a2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691496"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Record Domain Name System (DNS) esterni per Office 365

|||
|:-----|:-----|
|![Dominio](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)|**Se si desidera visualizzare un elenco personalizzato di record DNS per la propria organizzazione di Office 365,** è possibile [trovare le informazioni necessarie per creare record DNS di Office 365](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) per il proprio dominio in Office 365.  <br/> **Se si necessita di assistenza per aggiungere questi record al proprio host DNS di dominio, come GoDaddy o eNom,** [sono disponibili dei collegamenti alle istruzioni dettagliate per numerosi host DNS](https://go.microsoft.com/fwlink/?LinkId=286745). <br/>  **Si sta cercando di utilizzare l'elenco riferimenti per la propria distribuzione personalizzata?** Utilizzare l'elenco di seguito come riferimento per la propria distribuzione personalizzata di Office 365. Sarà necessario selezionare i record da applicare all'organizzazione e compilare i valori appropriati. <br/> **Tornare a** [Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune).  <br/> |

Spesso i record SPF e MX sono i più difficili da individuare. Microsoft ha aggiornato le indicazioni sui record SPF alla fine di questo articolo. La cosa importante da ricordare è che _è possibile avere un solo record SPF nel dominio_. È possibile avere più record MX; tuttavia, può essere proprio questa la causa di alcuni problemi relativi al recapito della posta. Disporre di un solo record MX che indirizza la posta elettronica a un sistema di posta consente di eliminare molti potenziali problemi.
  
Le sezioni di seguito sono suddivise per servizio in Office 365. Per visualizzare un elenco personalizzato dei record DNS di Office 365 per il proprio dominio, accedere a Office 365 e [raccogliere le informazioni necessarie per creare record DNS di Office 365](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Record DNS esterni necessari per Office 365 (servizi principali)
<a name="BKMK_ReqdCore"> </a>

Ogni cliente di Office 365 deve aggiungere due record ai propri DNS esterni. Il primo record CNAME garantisce che Office 365 possa indirizzare le workstation da autenticare alla piattaforma delle identità appropriata. Il secondo record necessario è un record per dimostrare che si è proprietari del nome di dominio.
  
||||
|:-----|:-----|:-----|
|**Record DNS** <br/> |**Scopo** <br/> |**Valore da utilizzare** <br/> |
|**CNAME** <br/> **(famiglia di prodotti)** <br/> |Utilizzato da Office 365 per indirizzare l'autenticazione verso la piattaforma delle identità corretta. [Ulteriori informazioni](https://go.microsoft.com/fwlink/p/?LinkId=322005) <br/> **Nota:** questo record CNAME si applica solo a Office 365 gestito da 21Vianet. [Altre informazioni](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**Alias:** msoid  <br/> **Destinazione:** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(verifica del dominio)** <br/> |Utilizzato da Office 365 per verificare soltanto se il dominio appartiene all'utente. Non incide su nessun altro elemento.  <br/> |**Host:** @ (o per alcuni provider di hosting DNS, il nome di dominio dell'utente)  <br/> **TXT Value:** _ una stringa di testo fornita da_ Office 365  <br/> La procedura guidata di **configurazione del dominio** di Office 365 fornisce i valori da utilizzare per creare il record.  <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Record DNS esterni richiesti per la posta elettronica in Office 365 (Exchange Online)
<a name="BKMK_ReqdCore"> </a>

La posta elettronica in Office 365 richiede diversi record; i tre record principali che tutti i clienti devono utilizzare sono Autodiscover, MX e SPF.
  
- **Il record di individuazione automatica** consente ai computer client di trovare automaticamente Exchange e configurare correttamente il client.

- **Il record MX** indica agli altri sistemi di posta dove inviare la posta elettronica per il proprio dominio. **Nota:** quando si configura il proprio indirizzo e-mail per Office 365, aggiornando il record MX del dominio TUTTI i messaggi inviati a quel dominio inizieranno a essere recapitati in Office 365.  
Si vogliono trasferire solo alcuni indirizzi di posta elettronica in Office 365? È possibile [Eseguire una distribuzione pilota di Office 365 con alcuni indirizzi di posta elettronica nel dominio personalizzato](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7).

- Il **record TXT per SPF** viene usato dai sistemi di posta elettronica dei destinatari per verificare che il server che invia i messaggi sia approvato. Ciò consente di prevenire problemi come lo spoofing e il phishing di posta elettronica. Per informazioni su cosa includere nel record, vedere i [record DNS esterni necessari per SPF](external-domain-name-system-records.md#BKMK_SPFrecords) in questo articolo.

I clienti di posta elettronica che utilizzano la federazione di Exchange dovranno avere un ulteriore record CNAME e TXT (elencati nella parte inferiore della tabella).
  
||||
|:-----|:-----|:-----|
|**Record DNS** <br/> |**Scopo** <br/> |**Valore da utilizzare** <br/> |
|**CNAME** <br/> **(Exchange Online)** <br/> |Consente ai client di Outlook di connettersi con facilità al servizio Exchange Online utilizzando il servizio di individuazione automatica. Il servizio di individuazione automatica trova automaticamente l'host di Exchange Server e configura Outlook per gli utenti.  <br/> |**Alias:** Autodiscover  <br/> **Destinazione:** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |Invia la posta in arrivo per il dominio al servizio Exchange Online in Office 365.  <br/> [!NOTE] Una volta che la posta elettronica viene inviata a Exchange Online, è necessario rimuovere i record MX che puntano al vecchio sistema.   |**Dominio:** ad esempio, contoso.com  <br/> **Server di posta elettronica di destinazione:**\<MX token\>.mail.protection.outlook.com  <br/> **Preferenza/priorità:** inferiore rispetto ad altri record MX (ciò garantisce che la posta venga recapitata a Exchange Online), ad esempio 1 o "bassa"  <br/>  Trovare il proprio \<MX token\> seguendo questa procedura:  <br/>  Accedere a Office 365, passare ad Amministrazione di Office 365 \> Domini.  <br/>  Nella colonna Azione relativa al dominio, scegliere Correggi i problemi.  <br/>  Nella sezione dei record MX, scegliere Cosa risolvere?  <br/>  Seguire le istruzioni contenute in questa pagina per aggiornare il record MX.  <br/> [Cos'è la priorità MX?](https://go.microsoft.com/fwlink/p/?LinkId=396471) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |Consente di impedire che altri utenti utilizzino il dominio per l'invio di posta indesiderata o comunque dannosa. I record SPF (Sender Policy Framework) identificano i server che sono autorizzati a inviare posta elettronica dal dominio dell'utente.  <br/> |[Record DNS esterni necessari per SPF](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(federazione di Exchange)** <br/> |Utilizzato per la federazione di Exchange per la distribuzione ibrida.  <br/> |**Record TXT 1:** ad esempio, contoso.com e il testo hash associato, generato in modo personalizzato e per la prova del dominio (ad esempio, Y96nu89138789315669824)  <br/> **Record TXT 2:** ad esempio, exchangedelegation.contoso.com e il testo hash associato, generato in modo personalizzato e per la prova del dominio (ad esempio, Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(federazione di Exchange)** <br/> |Consente ai client di Outlook di connettersi con facilità al servizio Exchange Online tramite il servizio di individuazione automatica, nel caso in cui la società dell'utente utilizzi la federazione di Exchange. Il servizio di individuazione automatica consente di trovare automaticamente l'host di Exchange Server e configura Outlook per gli utenti.  <br/> |**Alias:** ad esempio, Autodiscover.service.contoso.com  <br/> **Destinazione:** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>Record DNS esterni necessari per Skype for Business Online
<a name="BKMK_ReqdCore"> </a>

Per verificare che la rete sia stata configurata correttamente, ci sono dei passaggi da seguire quando si utilizzano [URL e intervalli di indirizzi IP di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).

> [!NOTE]
> Questi record DNS sono validi anche per Teams, in particolare in uno scenario ibrido con Teams e Skype for Business, in cui potrebbero verificarsi alcuni problemi di federazione.
  
||||
|:-----|:-----|:-----|
|**Record DNS** <br/> |**Scopo** <br/> |**Valore da utilizzare** <br/> |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Consente al dominio di Office 365 di condividere le funzionalità di messaggistica istantanea con client esterni abilitando la federazione SIP. Consultare ulteriori informazioni su [URL e intervalli di indirizzi IP di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |**Servizio**: sipfederationtls  <br/> **Protocollo:** TCP  <br/> **Priorità:** 100  <br/> **Peso:** 1  <br/> **Porta:** 5061  <br/> **Destinazione**: sipfed.online.lync.com  <br/> **Nota:** se il firewall o il server proxy bloccano le ricerche SRV su un DNS esterno, è necessario aggiungere questo record a quello DNS interno.   |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Utilizzato da Skype for Business per coordinare il flusso di informazioni tra i client di Lync.  <br/> |**Servizio**: sip  <br/> **Protocollo**: TLS  <br/> **Priorità:** 100  <br/> **Peso:** 1  <br/> **Porta:** 443  <br/> **Destinazione:** sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Utilizzato dal client di Lync per consentire all'utente di individuare il servizio di Skype for Business Online e accedere.  <br/> |**Alias:** sip  <br/> **Destinazione:** sipdir.online.lync.com  <br/> Per ulteriori informazioni, vedere [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Utilizzato dal client mobile di Lync per consentire all'utente di individuare il servizio di Skype for Business Online e accedere.  <br/> |**Alias:** lyncdiscover  <br/> **Destinazione:** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Record DNS esterni necessari per Office 365 Single Sign-On
<a name="BKMK_ReqdCore"> </a>

||||
|:-----|:-----|:-----|
|**Record DNS** <br/> |**Scopo** <br/> |**Valore da utilizzare** <br/> |
|**Host (A)** <br/> |Utilizzato per Single Sign-On (SSO). Fornisce l'endpoint agli utenti fuori sede (e locali, se si preferisce) per effettuare la connessione ai proxy di server federativi di Active Directory Federation Services (AD FS) o all'IP virtuale (VIP) con carico bilanciato.  <br/> |**Target:** ad esempio, sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>Record DNS esterni necessari per SPF
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
>  SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste tecniche, dopo aver configurato SPF, è necessario configurare anche DKIM e DMARC per Office 365. Per iniziare, vedere [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Successivamente, vedere [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
  
I record SPF sono record TXT che consentono di impedire che altri utenti utilizzino il dominio per l'invio di posta indesiderata o comunque dannosa. I record SPF (Sender Policy Framework) identificano i server che sono autorizzati a inviare posta elettronica dal dominio dell'utente.
  
È possibile avere solo un record SPF (ovvero un record TXT che definisce SPF) per il dominio. Tale singolo record può includere diversi elementi ma il totale delle ricerche DNS non può essere superiore a 10 (ciò consente di evitare attacchi Denial of Service). Vedere la tabella e gli altri esempi di seguito per creare o aggiornare i valori del record SPF appropriato per il proprio ambiente.
  
### <a name="structure-of-an-spf-record"></a>Struttura di un record SPF

Tutti i record SPF contengono tre parti, la dichiarazione che si tratta di un record SPF, i domini e gli indirizzi IP che si occupano dell'invio della posta elettronica e una regola di imposizione. È necessario disporre di tutti e tre gli elementi per avere un record SPF valido. Ecco un esempio di record SPF comune per Office 365 quando si usa solo la posta elettronica di Exchange Online:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

Un sistema di posta elettronica che riceve un messaggio dal dominio esamina il record SPF e se il server di posta elettronica del mittente è un server di Office 365, il messaggio viene accettato. Se invece è il vecchio sistema di posta o un sistema dannoso su Internet, ad esempio, il controllo SPF potrebbe non riuscire e il messaggio non viene consegnato. Questo tipo di controllo aiuta a prevenire i messaggi di spoofing e phishing.
  
### <a name="choose-the-spf-record-structure-you-need"></a>Scelta della struttura di record SPF necessaria

Per gli scenari in cui non si usa solo la posta elettronica di Exchange Online per Office 365 (ad esempio, quando si utilizza anche la posta elettronica di SharePoint Online), consultare la tabella seguente per stabilire cosa includere nel valore del record.
  
> [!NOTE]
> Negli scenari più complessi che includono, ad esempio, server e-mail perimetrale per gestire il traffico della posta attraverso il firewall, è necessario configurare un record SPF più dettagliato. Vedere come [configurare i record SPF in Office 365 per impedire lo spoofing](https://go.microsoft.com/fwlink/?LinkId=787656). Sono disponibili ulteriori informazioni sul funzionamento di SPF con Office 365 in [Utilizzo di Sender Policy Framework (SPF) in Office 365 per impedire lo spoofing](https://go.microsoft.com/fwlink/?LinkId=787065).
  
| Numero|Se si sta utilizzando...  <br/> |Scopo  <br/> |Aggiungere i seguenti valori  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |Tutti i sistemi di posta elettronica (obbligatorio)  <br/> |Tutti i record SPF devono iniziare con questo valore  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (comune)  <br/> |Utilizzare solo con Exchange Online  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Sistema di posta elettronica di terze parti (meno comune)  <br/> ||Includere:\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |Sistema di posta locale (meno comune)  <br/> |Utilizzare se si utilizza Exchange Online Protection o Exchange Online e un altro sistema di posta elettronica  <br/> |ip4:\<0.0.0.0\>  <br/> ip6:\< : : \>  <br/> Includere:\<mail.contoso.com\>  <br/> Il valore tra parentesi (\<\>) deve rappresentare altri sistemi di posta elettronica che inviano la posta elettronica per il dominio.  <br/> |
|5  <br/> |Tutti i sistemi di posta elettronica (obbligatorio)  <br/> ||-all  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>Esempio: aggiunta di un record SPF esistente
<a name="bkmk_addtospf"> </a>

Se già si dispone di un record SPF, è necessario aggiungere o aggiornare i valori per Office 365. Ad esempio, supponiamo che il record SPF esistente per contoso.com sia il seguente:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

Ora il record SPF deve essere aggiornato per Office 365. Modificare il record corrente in modo da avere un record SPF che includa i valori necessari. Per Office 365, "spf.protection.outlook.com".
  
Impostazione corretta:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

Impostazione non corretta:
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>Altri esempi di valori SPF comuni
<a name="bkmk_addtospf"> </a>

Se si usa la famiglia completa di prodotti Office 365 e si sceglie MailChimp per inviare messaggi di posta elettronica di marketing per proprio conto, il record SPF in contoso.com potrebbe essere simile al seguente, che usa le righe 1, 3 e 5 della tabella precedente. Tenere presente che le righe 1 e 5 sono obbligatorie.
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

In alternativa, se si dispone di una configurazione ibrida di Exchange in cui la posta elettronica viene inviata da Office 365 e dal sistema di posta locale, il record SPF con dominio contoso.com potrebbe essere simile al seguente:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

Questi sono alcuni esempi comuni che possono aiutare ad adattare il record SPF esistente quando si aggiunge il dominio a Office 365 per la posta elettronica. Negli scenari più complessi che includono, ad esempio, server e-mail perimetrale per gestire il traffico della posta attraverso il firewall, è necessario configurare un record SPF più dettagliato. Vedere come [configurare i record SPF in Office 365 per impedire lo spoofing](https://go.microsoft.com/fwlink/?LinkId=787656).
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/o365edns](https://aka.ms/o365edns)
