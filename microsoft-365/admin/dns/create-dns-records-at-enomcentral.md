---
title: Creare record DNS in eNomCentral per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in eNomCentral per Microsoft.
ms.openlocfilehash: 94b0648e03d756f429094a6d35f03d5596a272f4
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434192"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Creare record DNS in eNomCentral per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.

Se il proprio provider di hosting DNS è eNomCentral, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.

Dopo aver aggiunto questi record in eNomCentral, il dominio sarà configurato per l'uso con i servizi Microsoft.

> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.

> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.

   Scegliere il valore del **tipo di record** nell'elenco a discesa.

   |Nome host|Record Type|Indirizzo|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. Selezionare **Salva**.

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.

Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.

Quando Microsoft trova il record TXT corretto, il dominio è verificato.

1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

2. Nella pagina **Domini** selezionare il dominio da verificare.

3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.

4. Nella pagina **Verifica dominio** selezionare **Verifica**.

> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Nell'elenco a discesa **Manage Domain** scegliere **Email Settings**.

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. Nell'elenco a discesa **Service Selection** scegliere **User (MX)**.

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |Nome host|Indirizzo|Pref|
   |---|---|---|
   |@| *\<domain-key\>*. mail.protection.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> **Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|10   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. Selezionare **Salva**.

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. Se sono presenti altri record MX esistenti, selezionare le caselle di controllo corrispondenti per selezionarli.

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. Selezionare **Delete Checked**.

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Selezionare **nuova riga**.

   ![eNom-BP-configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. Nelle caselle dei nuovi sei record digitare oppure copiare e incollare i valori seguenti.

   Scegliere il valore del **tipo di record** nell'elenco a discesa.

   |Nome host|Record Type|Indirizzo|
   |---|---|---|
   |autodiscover|CNAME (alias)|autodiscover.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|
   |sip|CNAME (alias)|sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|
   |lyncdiscover|CNAME (alias)|webdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|
   |enterpriseregistration|CNAME (alias)|enterpriseregistration.windows.net.  <br/> **Questo valore DEVE terminare con un punto (.)**|
   |enterpriseenrollment|CNAME (alias)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|

   ![eNom-BP-configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. Selezionare **Salva**.

   ![eNom-BP-configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.

   Scegliere il valore del **tipo di record** nell'elenco a discesa.

   |Nome host|Record Type|Indirizzo|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. Selezionare **Salva**.

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Per iniziare, passare alla propria pagina dei domini su eNom Central usando [questo collegamento](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Verrà richiesto di eseguire l'accesso.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Nell'elenco a discesa **Manage Domain** scegliere **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. A destra della **nuova riga**, selezionare **Aggiungi record SRV o SPF**.

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. Nelle caselle dei nuovi due record digitare oppure copiare e incollare i valori della tabella seguente.

   |Servizio|Protocollo|Priority|Peso|Porta|Destinazione (hostname)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|1 |443|sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|
   |_sipfederationtls|_tcp|100|1 |5061|sipfed.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. Seleziona **Salva**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).
