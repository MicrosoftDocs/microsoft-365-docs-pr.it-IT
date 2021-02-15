---
title: Modificare i server dei nomi per configurare Microsoft con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Informazioni su come configurare Microsoft per gestire i record DNS del dominio personalizzato in Hostgator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658021"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Modificare i server dei nomi per configurare Microsoft 365 con Hostgator

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.
  
Seguire queste istruzioni se si desidera che Microsoft gestirà i record DNS. Se si preferisce, è possibile [gestire tutti i record DNS Microsoft su Hostgator.](create-dns-records-at-hostgator.md)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Associare il dominio all'account di hosting.

> [!IMPORTANT]
> È necessario eseguire questa procedura prima di quella illustrata nella sezione seguente, **Aggiungere un record TXT a scopo di verifica**.
  
Seguire questa procedura per associare il dominio e gli account di hosting.
  
1. Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selezionare la **scheda Domini.**
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. **Nell'area My** Domains della pagina Manage **Domains** selezionare il dominio che si desidera aggiornare.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Nell'area **Name Servers** della pagina **Domains Overview** selezionare **Change**.
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Nella pagina **Name Servers** del dominio scegliere l'account **di hosting** associato al dominio nell'elenco a discesa Select **Hosting Account.**
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selezionare **Save Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

> [!IMPORTANT]
> Prima di eseguire questa procedura, è necessario eseguire la procedura descritta nella prima sezione di questo articolo, Puntare il dominio [all'account di hosting.](#point-your-domain-to-your-hosting-account)
  
Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Tale indirizzo sarà specificato nel messaggio di posta elettronica di iscrizione ricevuto da Hostgator.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft. 
  
2. Nell'area Domini della  pagina **Pannello** di controllo selezionare Advanced DNS **Zone Editor.**
    
    Può essere necessario scorrere la pagina. 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Usare il proprio  *nome_dominio*  , ad esempio fourthcoffee.com.<br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Selezionare **Aggiungi record.**
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record nel sito del registrar, si tornerà a Microsoft e si richiederà una ricerca del record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario Microsoft. Questo consente a Microsoft di aggiornare automaticamente i record DNS del dominio. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, vengono interessati tutti i servizi attualmente associati al dominio. Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (ad esempio rob@ *your_domain*  .com) inizieranno a essere inviati a Microsoft dopo aver apportato questa modifica.
  
> [!IMPORTANT]
> Nella procedura seguente viene illustrato come eliminare altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. Dopo aver completato i passaggi descritti in questa sezione, gli unici server dei nomi che dovrebbero essere elencati sono i quattro seguenti:  **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** e **ns4.bdm.microsoftonline.com**.
  
1. Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selezionare la **scheda Domini.** 
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. **Nell'area My** Domains della pagina Manage **Domains** selezionare il dominio che si desidera aggiornare. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Nell'area **Name Servers** della pagina **Domain Overview** selezionare **Change.**
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Nella pagina **Name Servers** del dominio scegliere l'account **di hosting** associato al dominio nell'elenco a discesa Select **Hosting Account.** 
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selezionare **Imposta manualmente i server dei nomi.**
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **ATTENZIONE:** eseguire questa procedura solo se sono disponibili server dei nomi diversi da quattro server dei nomi corretti. In altre informazioni, eliminare solo i  server dei nomi correnti non denominati **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.
  
        Sempre nella pagina **Name Servers** del dominio, eliminare ognuno dei server dei nomi presenti nell'elenco selezionandolo e premendo **CANC**. 
    
   ![O365_proceduraguidata_Aggiungidominio_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Sempre nell'elenco dei server dei nomi, digitare oppure copiare e incollare i primi due valori della tabella seguente.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Aggiungere gli altri valori dei server dei nomi.
    
    Selezionare **(+)** aggiungere e quindi digitare oppure copiare e incollare il valore dalla riga successiva della tabella nella casella del record. 
    
    Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Selezionare **Save Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.
