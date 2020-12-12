---
title: Modificare i server dei nomi per configurare Microsoft con il dominio
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Informazioni su come è possibile configurare Microsoft per gestire i record DNS del dominio personalizzato in dominio.
ms.openlocfilehash: fbfa3c495f54a9890be6d9c9e31a7878b21f12fe
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658417"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a>Modificare i server dei nomi per configurare Microsoft con il dominio

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.
  
Se si desidera gestire i record DNS per l'utente, seguire le istruzioni riportate di seguito. Se si preferisce, è possibile [gestire tutti i record Microsoft DNS nel dominio](create-dns-records-at-mydomain.md).
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.
    
2. Nella sezione **Preferiti** selezionare **Dominio centrale**.
    
3. In **Dominio** selezionare il nome del dominio da modificare.
    
4. Nella riga **Panoramica** scegliere **DNS**.
    
5. Nell'elenco a discesa **Modifica** selezionare **Record TXT/SPF**.
    
6. Nella casella del nuovo record, in **Contenuto**, digitare oppure copiare e incollare il valore della tabella seguente.
    
||
|:-----|
|**Contenuto** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Nota**: questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selezionare **Aggiungi**.
    
8. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.
  
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
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft, sono coinvolti tutti i servizi attualmente associati al dominio. Ad esempio, tutti i messaggi di posta elettronica inviati al dominio (come rob@ *your_domain.* com) inizierà a essere Microsoft dopo aver apportato questa modifica. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. <br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. Per iniziare, passare alla propria pagina dei domini su MyDomain usando [questo collegamento](https://www.mydomain.com/controlpanel). Verrà richiesto di eseguire l'accesso.
    
2. Nella sezione **Preferiti** selezionare **Dominio centrale**.
    
3. In **Dominio** selezionare il nome del dominio da modificare.
    
4. Nella riga **Panoramica** selezionare Server dei **nomi**.
    
    ![Dominio-BP-redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. Nella sezione **Update Name Servers** selezionare **Use different name servers**.
    
    ![Dominio-BP-redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. A seconda del fatto che siano già presenti o meno i server dei nomi elencati nella pagina visualizzata, continuare con una delle due procedure seguenti.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Se i server dei nomi corretti SONO già elencati

- Se i server dei nomi corretti sono già elencati, è possibile ignorare questo passaggio.
    
    ![Dominio-BP-redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Se i server dei nomi corretti NON sono ancora elencati

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ovvero, eliminare solo eventuali server dei nomi correnti che  *non*  sono denominati **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com** o **NS4.BDM.microsoftonline.com**). 
  
1. Eliminare i server dei nomi esistenti selezionando le singole voci nel campo **Nameserver**, quindi premendo **CANC**. 
    
    ![Dominio-BP-redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Per aggiungere due nuove righe dei server dei nomi, fare clic su **Aggiungi** due volte. 
    
    ![Dominio-BP-redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. Nelle caselle dei record digitare oppure copiare e incollare i valori del server dei nomi dalla tabella seguente.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Dominio-BP-redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Selezionare **Salva**.
    
    ![Dominio-BP-redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
