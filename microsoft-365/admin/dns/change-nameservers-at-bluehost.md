---
title: Modificare i server dei nomi per configurare Microsoft con Bluehost
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Informazioni su come è possibile configurare Microsoft per gestire i record DNS in Bluehost. '
ms.openlocfilehash: f20c09d2c9ca107648cba843cc93d839df8c53fc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939392"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>Modificare i server dei nomi per configurare Microsoft con Bluehost

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito. Se si preferisce, è possibile [gestire tutti i record DNS su Bluehost](create-dns-records-at-bluehost.md).
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina. 
    
3. Nell'area **Domain_name** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. Selezionare **Aggiungi record**.
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari. Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio. Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain* . com) inizierà a venire a Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
>  Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. > dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi da elencare sono i seguenti quattro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **Domain_name** della pagina **Domains** selezionare la casella di controllo per il dominio, quindi selezionare Server dei **nomi**.
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. Nell'area **Domain_name** selezionare **Usa server dei nomi personalizzati**.
    
    ![Miglioramenti relativi al percorso animazione](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:
    
  - Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).
    
  - Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NON sono già elencati server dei nomi

1. Nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della tabella seguente. 
    
|||
|:-----|:-----|
|**Prima riga vuota** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Seconda riga vuota** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. Selezionare **Aggiungi riga**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota. 
    
|||
|:-----|:-----|
|**Terza riga vuota** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta riga vuota** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. Per aggiungere il quarto record del server dei nomi, selezionare di nuovo **Aggiungi riga** e creare un record usando i valori dell'ultima riga della tabella precedente. 
    
5. Selezionare **Salva impostazioni server dei nomi**.
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se SONO già elencati server dei nomi

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**). 
  
1. Se sono già presenti server dei nomi, eliminarli selezionando ogni server e premendo **CANC**. 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. Sempre nella sezione **Use Custom Nameservers**, digitare oppure copiare e incollare i valori della tabella seguente. 
    
|||
|:-----|:-----|
|**Prima riga vuota** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Seconda riga vuota** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. Selezionare **Aggiungi riga**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota. 
    
|||
|:-----|:-----|
|**Terza riga vuota** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta riga vuota** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. Per aggiungere il quarto record del server dei nomi, selezionare di nuovo **Aggiungi riga** e creare un record usando i valori dell'ultima riga della tabella precedente. 
    
6. Selezionare **Salva impostazioni server dei nomi**.
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  
