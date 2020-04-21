---
title: Modificare i server dei nomi per configurare Microsoft con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Informazioni su come è possibile configurare Microsoft per gestire i record DNS del dominio personalizzato in Hostgator.
ms.openlocfilehash: 09f0409ed2a5f81b450c9aae7bb3699373ce6f22
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629888"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Modificare i server dei nomi per configurare Microsoft 365 con Hostgator

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.
  
Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito. Se si preferisce, è possibile [gestire tutti i record Microsoft DNS su Hostgator](create-dns-records-at-hostgator.md).
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Associare il dominio all'account di hosting.

> [!IMPORTANT]
> È necessario eseguire questa procedura prima di quella illustrata nella sezione seguente, **Aggiungere un record TXT a scopo di verifica**.
  
Seguire questa procedura per associare il dominio e gli account di hosting.
  
1. Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selezionare la scheda **domini** .
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Nell'area **Name Servers** della pagina **Domains Overview** selezionare **Change**.
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio.
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selezionare **Save Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

> [!IMPORTANT]
> Prima di eseguire questa procedura, è necessario prima eseguire la procedura nella prima sezione di questo articolo, [puntare il dominio all'account di hosting.](#point-your-domain-to-your-hosting-account)
  
Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo. La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Tale indirizzo sarà specificato nel messaggio di posta elettronica di iscrizione ricevuto da Hostgator.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare, è possibile acquistare un account di hosting da Hostgator o [modificare i record del server dei nomi del dominio](#change-your-domains-nameserver-ns-records) in modo che puntino a Microsoft. 
  
2. Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced DNS zone editor**.
    
    (You may have to scroll down.) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Usare il proprio  *nome_dominio*  , ad esempio fourthcoffee.com.<br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Selezionare **Aggiungi record**.
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record del server dei nomi del dominio

Per completare la configurazione del dominio con Microsoft, è necessario modificare i record NS del dominio presso il registrar in modo che puntino ai server dei nomi primari e secondari Microsoft. Questo configura Microsoft per aggiornare i record DNS del dominio per l'utente. Verranno aggiunti tutti i record necessari per il funzionamento della posta elettronica, di Skype for Business online e del sito Web pubblico con il dominio.
  
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio. Ad esempio, tutta la posta elettronica inviata al dominio (come rob@ *your_domain* . com) inizierà a venire a Microsoft dopo aver apportato questa modifica.
  
> [!IMPORTANT]
> Nella procedura seguente viene illustrato come eliminare tutti gli altri server dei nomi indesiderati dall'elenco e come aggiungere i server dei nomi corretti se non sono già elencati. Dopo aver completato la procedura descritta in questa sezione, gli unici server dei nomi che devono essere elencati sono questi quattro: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**e **NS4.BDM.microsoftonline.com**.
  
1. Per iniziare, passare alla pagina del portale per i clienti di Hostgator usando [questo collegamento](https://portal.hostgator.com/domain/manage). Verrà richiesto di eseguire l'accesso.
    
    ![Connessione dell'elenco attività a Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selezionare la scheda **domini** . 
    
    ![Barra multifunzione di Office 2010](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Nella pagina **Gestisci domini** , nell'area **domini personali** , selezionare il dominio che si desidera aggiornare. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Nell'area **Name Servers** della pagina **Domain Overview** selezionare **Change**.
    
    ![Immagine del pulsante Imposta colore trasparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Nella pagina **Name Servers** per il dominio, nell'elenco a discesa **selezionare l'account di hosting** , scegliere l' **account di hosting** associato al dominio. 
    
    ![Dashboard di Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selezionare **imposta manualmente i server My Name**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **Attenzione**: attenersi alla seguente procedura solo se sono presenti server dei nomi diversi dai quattro nameserver corretti. (Ovvero, eliminare solo eventuali server dei nomi correnti che *non* sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).
  
        Sempre nella pagina **Name Servers** del dominio, eliminare ognuno dei server dei nomi presenti nell'elenco selezionandolo e premendo **CANC**. 
    
   ![O365_proceduraguidata_Aggiungidominio_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Sempre nell'elenco dei server dei nomi, digitare oppure copiare e incollare i primi due valori della tabella seguente.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Aggiungere gli altri valori dei server dei nomi.
    
    Selezionare **(+)** Aggiungi, quindi digitare oppure copiare e incollare il valore della riga successiva della tabella nella casella relativa al record. 
    
    Ripetere questa procedura fino a creare tutti e quattro i record dei server dei nomi.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Selezionare **Save Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.
