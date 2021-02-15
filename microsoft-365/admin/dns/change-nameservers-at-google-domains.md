---
title: Modificare i server dei nomi per configurare Microsoft con Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Informazioni su come configurare Microsoft per gestire i record DNS del dominio personalizzato in Google Domains.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658441"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Modificare i server dei nomi per configurare Microsoft con Google Domains

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Seguire queste istruzioni se si desidera che Microsoft gestirà i record DNS. Se si preferisce, è possibile [gestire tutti i record DNS su Google Domains.](create-dns-records-at-google-domains.md)
  
    
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
>  Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. To get started, go to your domains page at Google Domains via [this link.](https://domains.google.com/registrar) You'll be prompted to sign in. To do so:
    
1. Scegliere **Accedi**.
    
2. Immetti le credenziali di accesso e seleziona di **nuovo Accedi.**
    
2. Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare. 
    
3. Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori della tabella seguente. 
    
    Può essere necessario scorrere la pagina.
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**Type** <br/> |**TTL** <br/> |**Dati** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Selezionare **Aggiungi**.
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record nel sito del registrar, si tornerà a Microsoft e si richiederà una ricerca del record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario Microsoft. Questo consente a Microsoft di aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, vengono interessati tutti i servizi attualmente associati al dominio. Ad esempio, tutta la posta elettronica inviata al dominio ,ad esempio rob@ *your_domain.*  com) inizierà a venire a Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > Dopo aver completato i passaggi descritti in questa sezione, gli unici server dei nomi che dovrebbero essere elencati sono i quattro seguenti: 
  
1. Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:
    
1. Scegliere **Accedi**.
    
2. Immettere le credenziali di accesso e poi selezionare di nuovo **Accedi**.
    
2. Nella pagina **Domains**, nella sezione **Domain**, selezionare **Configura DNS** per il dominio che si vuole modificare. 
    
3. Nella pagina **Domains**, nella sezione **Name servers**, selezionare **Use custom name servers**.
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. A seconda che siano o meno già presenti server dei nomi nella pagina visualizzata, continuare con una delle due procedure seguenti:
    
  - Se **NON** sono già elencati server dei nomi, [Se NON sono già elencati server dei nomi](#if-there-are-no-nameservers-already-listed).
    
  - Se **SONO** già elencati server dei nomi, [Se SONO già elencati server dei nomi](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NON sono già elencati server dei nomi

1. Aggiungere il primo server dei nomi.
    
    Nella casella **NAME SERVER** della sezione **Name servers** digitare oppure copiare e incollare il primo valore dalla tabella seguente. 
    
|||
|:-----|:-----|
|**Primo server dei nomi** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondo server dei nomi** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Terzo server dei nomi** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarto server dei nomi** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Selezionare il **controllo + (aggiungi)** per creare una riga vuota. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. Aggiungere gli altri tre record dei server dei nomi.
    
    Nella sezione **Use custom name servers** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare il controllo + **(add)** per aggiungere un'altra riga. 
    
    Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.
    
4. Selezionare **Salva**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se SONO già elencati server dei nomi

1. Se sono elencati altri server dei nomi, selezionare **Modifica.**
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. In altre informazioni, eliminare solo i  server dei nomi correnti non denominati **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**. 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Eliminare ciascun valore selezionandolo e premendo **CANC**. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. Sempre nella sezione **Name servers**, nelle righe **NAME SERVER** digitare oppure copiare e incollare il valore dalla tabella seguente. 
    
|||
|:-----|:-----|
|**Primo server dei nomi** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondo server dei nomi** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Terzo server dei nomi** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarto server dei nomi** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Selezionare il **controllo +(add)** per creare una riga vuota. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Aggiungere gli altri due record dei server dei nomi.
    
    Nella sezione **Use custom name servers** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare il controllo **+(add)** per aggiungere un'altra riga. 
    
    Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.
    
6. Selezionare **Salva**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
