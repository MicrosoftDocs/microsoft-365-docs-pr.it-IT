---
title: Modificare i server dei nomi per configurare Microsoft con 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Informazioni su come è possibile configurare Office 365 gestito da 21Vianet per gestire i record DNS, quando 1&1 Internet è il provider di hosting DNS.
ms.openlocfilehash: b363718c7d1d1845117f44317ae9e6b24e9a2e28
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658033"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>Modificare i server dei nomi per configurare Microsoft 365 con 1&1 IONOS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Seguire le istruzioni riportate di seguito se si desidera che Microsoft 365 gestisca i record DNS di Microsoft 365. Se si preferisce, è possibile [gestire tutti i record DNS di Microsoft 365 a 1&1 IONOS](create-dns-records-at-1-1-internet.md). 
  

    
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica


Prima di usare il proprio dominio con Microsoft 365, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft 365 che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS tramite [questo collegamento](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. In **My Domains** selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare. Selezionare quindi il controllo **Panel** ( **v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.
    
    Può essere necessario scorrere la pagina. 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **Nota**: questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. Fare clic su **Salva** e quindi su **Salva** di nuovo. 
    
8. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
9. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.
  
Quando Microsoft 365 trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> Solitamente, affinché le modifiche DNS diventino effettive, sono necessari circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft 365, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari di Microsoft 365. In questo modo si configura Microsoft 365 per aggiornare i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft 365, tutti i servizi attualmente associati al dominio sono intaccati. Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain*  . com) inizierà a venire a Microsoft 365 dopo aver apportato questa modifica. 
  
È possibile modificare i record NS per consentire a Microsoft 365 di configurare il dominio? Seguire le istruzioni riportate di seguito o [guardare il video (iniziare da 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
> [!IMPORTANT]
>  Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. > dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. In **My Domains** selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **Name Server Settings** selezionare **Other name servers**.
    
    Può essere necessario scorrere la pagina.
    
6. A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:
    
  - Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).
    
  - Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NON sono già elencati server dei nomi

1. Nella seconda casella **Name server 1** digitare o copiare e incollare il valore dalla tabella seguente. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![Immissione di un valore nella casella Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. Nell'elenco a discesa **Additional name servers** scegliere **My secondary name servers**.
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. Nelle caselle **Name server 2, 3 e 4** digitare o copiare e incollare il valore dalla tabella seguente. 
    
|||
|:-----|:-----|
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![Immissione di valori del server dei nomi](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. Selezionare **Salva**.
    
    ![Selezione di Save nella pagina Impostazioni server dei nomi](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
    ![Selezionare Salva nella finestra di dialogo Modifica impostazioni DNS.](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se SONO già elencati server dei nomi

> [!CAUTION]
> Seguire questa procedura  *solo*  se sono presenti server dei nomi diversi dai quattro server dei nomi  *corretti*  . In altre parole, eliminare  *solo*  eventuali server dei nomi  *diversi*  da **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**. 
  
1. Se sono già elencati altri server dei nomi nelle caselle **Name server**, eliminarli uno alla volta selezionandoli e premendo **CANC**. 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. Nelle caselle **Name server 1, 2, 3 e 4** digitare o copiare e incollare i valori dalla tabella seguente. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Immissione di valori del server dei nomi](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. Selezionare **Salva**.
    
    ![Selezione di Save nella pagina Impostazioni server dei nomi](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
    ![Selezionare Salva nella finestra di dialogo Modifica impostazioni DNS.](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  


