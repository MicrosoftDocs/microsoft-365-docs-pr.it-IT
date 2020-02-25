---
title: Creare record DNS su GoDaddy per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in GoDaddy per Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241276"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>Creare record DNS su GoDaddy per Office 365

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.

Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.

Dopo aver aggiunto questi record in GoDaddy, il domino sarà configurato per l'uso con i servizi di Office 365.

Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).

> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.

> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **domini**selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Seleziona **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **TXT (Text)** nell'elenco a discesa. In the boxes for the new record, type or copy and paste the values from the following table.

    |**Tipo di record** |**Host**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (Text)|@|MS=ms *XXXXXXXX*<br>**Nota**: questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|1 hour  <br>Selezionare un valore nell'elenco a discesa.|

      ![GoDaddy-BP-Verify-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Selezionare **Salva**.

6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.

Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.

When Office 365 finds the correct TXT record, your domain is verified.
  
1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.

    
2. Nella pagina **Domains** selezionare il dominio che si sta verificando. 
    
    
  
3. Nella pagina **configurazione** , selezionare **Avvia installazione**.



4. Nella pagina **Verifica dominio** selezionare **Verifica**.



> [!NOTE]
>  In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365
<a name="BKMK_add_MX"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **domini**selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Seleziona **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.

    Scegliere il valore **TTL** nell'elenco a discesa.

    |**Tipo di record**|**Host**|**Points to**|**Priorità**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dall'account di Office 365.           [Come trovarla](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> |1 ora  <br/> |

6. Selezionare **Salva**.

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Aggiungere i record CNAME necessari per Office 365
<a name="BKMK_add_CNAME"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **domini**selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Seleziona **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Scegliere **CNAME (Alias)** nell'elenco a discesa.

    ![GoDaddy-BP-configure-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Creare il primo record CNAME.

    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.

    Scegliere il valore **TTL** nell'elenco a discesa.

    |**Tipo di record**|**Host**|**Points to**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
    |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hour  <br/> |



6. Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **domini**selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Seleziona **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **TXT (Text)** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.

    Scegliere il valore **TTL** negli elenchi a discesa.

    |**Tipo di record**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1 hour  <br/> |

    ![GoDaddy-BP-Configure-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Selezionare **Salva**.


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365
<a name="BKMK_add_SRV"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **domini**selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Seleziona **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **SRV** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Creare il primo record SRV.

    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.

    Scegliere il **tipo di record** e i valori **TTL** negli elenchi a discesa.

    |**Tipo di record**|**Nome**|**Destinazione**|**Protocollo**|**Servizio**|**Priorità**|**Peso**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 ora  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 ora  <br/> |

    ![GoDaddy-BP-Configure-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Ripetere il **passaggio 5** per creare l'altro record SRV.

7. Selezionare **Salva**.

> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).
