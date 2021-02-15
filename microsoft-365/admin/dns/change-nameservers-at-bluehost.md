---
title: Modificare i server dei nomi per configurare Microsoft con Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Informazioni su come configurare Microsoft per gestire i record DNS su Bluehost. '
ms.openlocfilehash: 78b138a501054a573c2b36cc486dda833be7ae35
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658009"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>Modificare i server dei nomi per configurare Microsoft con Bluehost

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Seguire queste istruzioni se si desidera che Microsoft gestirà i record DNS. Se si preferisce, è possibile [gestire tutti i record DNS su Bluehost.](create-dns-records-at-bluehost.md)
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina. 
    
3. Nell'area **domain_name,** nella riga **DNS Zone Editor,** selezionare **Manage DNS records.**
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. Selezionare **Aggiungi record.**
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record nel sito del registrar, si tornerà a Microsoft e si richiederà una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario. Questo consente a Microsoft di aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, vengono interessati tutti i servizi attualmente associati al dominio. Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (ad esempio rob@ *your_domain*  .com) inizieranno a essere inviati a Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
>  Nella procedura seguente viene illustrato come eliminare altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. > Dopo aver completato i passaggi descritti in questa sezione, gli unici server dei nomi che dovrebbero essere elencati sono i quattro seguenti: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **dei domini,** nell'area **domain_name,** selezionare la casella di controllo per il dominio e quindi selezionare i **server dei nomi.**
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. Nell'area **domain_name** selezionare **Utilizza server dei nomi personalizzati.**
    
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
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. Selezionare **Aggiungi riga.**
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota. 
    
|||
|:-----|:-----|
|**Terza riga vuota** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta riga vuota** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. Per aggiungere il quarto record nameserver, selezionare di nuovo **Add Row** e creare un record utilizzando i valori dell'ultima riga della tabella precedente. 
    
5. Selezionare **Salva impostazioni server dei nomi.**
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se SONO già elencati server dei nomi

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. In altre informazioni, eliminare solo i  server dei nomi correnti non denominati **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**. 
  
1. Se sono già presenti server dei nomi, eliminarli selezionando ogni server e premendo **CANC**. 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. Sempre nella sezione **Use Custom Nameservers**, digitare oppure copiare e incollare i valori della tabella seguente. 
    
|||
|:-----|:-----|
|**Prima riga vuota** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Seconda riga vuota** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. Selezionare **Aggiungi riga.**
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. Sempre nella sezione **Use Custom Nameservers** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nella nuova riga vuota. 
    
|||
|:-----|:-----|
|**Terza riga vuota** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta riga vuota** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. Per aggiungere il quarto record Nameserver, selezionare di nuovo **Add Row** e creare un record utilizzando i valori dell'ultima riga della tabella precedente. 
    
6. Selezionare **Salva impostazioni server dei nomi.**
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
