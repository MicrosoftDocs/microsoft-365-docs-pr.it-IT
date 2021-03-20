---
title: Creare record DNS su GoDaddy per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi su GoDaddy per Microsoft.
ms.openlocfilehash: d0163447abdc7b9fe5afd4f471f24ee09de40d50
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910247"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a>Creare record DNS su GoDaddy per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.

Se il proprio provider di hosting DNS è GoDaddy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.

Dopo aver aggiunto questi record in GoDaddy, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.

> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.

> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **Domini** selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selezionare **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **TXT (Text)** nell'elenco a discesa. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.

    |**Tipo di record** |**Host**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (testo)|@|MS=ms *XXXXXXXX*<br>**Nota:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|1 ora  <br>Selezionare un valore nell'elenco a discesa.|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Selezionare **Salva**.

6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.

Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.

Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.



4. Nella pagina **Verifica dominio** selezionare **Verifica**.



> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **Domini** selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selezionare **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **MX (Mail Exchanger)** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.

    Scegliere il **valore TTL** nell'elenco a discesa.

    |**Tipo di record**|**Host**|**Punta a**|**Priorità**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](../setup/domains-faq.yml). <br/> |1 ora  <br/> |

6. Selezionare **Salva**.

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **Domini** selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selezionare **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Scegliere **CNAME (Alias)** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Creare il primo record CNAME.

    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.

    Scegliere il **valore TTL** nell'elenco a discesa.

    |**Tipo di record**|**Host**|**Punta a**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (alias)  <br/> |individuazione automatica  <br/> |autodiscover.outlook.com  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 ora  <br/> |



6. Ripetere questi passaggi per aggiungere il record CNAME successivo fino a quando non sono stati creati tutti e sei i record CNAME.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **Domini** selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selezionare **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **TXT (Text)** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.

    Scegliere il **valore TTL** dagli elenchi a discesa.

    |**Tipo di record**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (testo)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1 ora  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Selezionare **Salva**.


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

Effettuare le operazioni seguenti.

1. Per iniziare, passare alla propria pagina dei domini su GoDaddy usando [questo collegamento](https://account.godaddy.com/products/?go_redirect=disabled). Verrà richiesto di eseguire l'accesso.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. In **Domini** selezionare DNS nel dominio che si desidera modificare.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selezionare **Aggiungi**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Scegliere **SRV** nell'elenco a discesa.

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Creare il primo record SRV.

    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.

    Scegliere i **valori Tipo di record** e **TTL** dagli elenchi a discesa.

    |**Tipo di record**|**Nome**|**Destinazione**|**Protocollo**|**Servizio**|**Priorità**|**Peso**|**Porta**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 ora  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 ora  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Ripetere **il passaggio 5** per creare l'altro record SRV.

7. Selezionare **Salva**.

> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).