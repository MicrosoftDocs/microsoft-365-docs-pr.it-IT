---
title: Modificare i server dei nomi per configurare Microsoft con Amazon Web Services (AWS)
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Informazioni su come è possibile configurare Microsoft per gestire i record DNS su Amazon Web Services (AWS). '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658453"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Modificare i server dei nomi per configurare Microsoft con Amazon Web Services (AWS)

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito. Se si preferisce, è possibile [gestire tutti i record Microsoft DNS in AWS](create-dns-records-at-aws.md).
  
    
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **risorse** selezionare **aree ospitate**.
    
3. Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare **Crea set di record**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
|(Lasciare vuoto questo campo)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Semplice <br/> |
   
6. Selezionare **Crea**.
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft. Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio. Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain*  . com) inizierà a venire a Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
>  Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. > dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **risorse** selezionare **aree ospitate**.
    
3. Nella colonna **nome dominio** della pagina **aree ospitate** selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare il set di record **Nameserver**. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. Nel set di record **NS - Name server** della casella **Valore** eliminare tutti i server dei nomi selezionandoli e premendo **CANC**. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ovvero, eliminare solo eventuali server dei nomi correnti che  *non*  sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com** o **NS4.BDM.microsoftonline.com**). 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. Nell'area **TTL (secondi):** selezionare **1h** (1 ora). 
    
    ![Selezionare 1H per un'ora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Sempre nel set di record **NS - Name server** della casella **Valore** digitare oppure copiare e incollare il valore **Prima riga** dalla tabella seguente, quindi premere **INVIO** e digitare oppure copiare e incollare il valore **Seconda riga**. 
    
    > [!IMPORTANT]
    > Ogni valore per il nome dei server  *deve*  trovarsi su una riga separata nella casella **Valore**, come mostrato nella figura seguente. 
  
|||
|:-----|:-----|
|**Prima riga** <br/> |ns1.bdm.microsoftonline.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
|**Seconda riga** <br/> |ns2.bdm.microsoftonline.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
|**Terza riga** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
|**Quarta riga** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
   
   ![Digitare o incollare il valore della prima riga nella casella valore.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Selezionare **Salva set di record**.
    
    ![Selezionare Salva set di record](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
