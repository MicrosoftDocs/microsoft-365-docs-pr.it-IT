---
title: Creare record DNS su easyDNS per Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi su easyDNS per Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656820"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Creare record DNS su easyDNS per Microsoft

Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.yml). 
  
È necessario aggiungere tutti i record DNS seguenti nel sito Web del registrar per instradare la posta a Microsoft, usare il dominio per Teams e Skype for Business e così via.
  
NOTA: I record SRV non sono attualmente disponibili in tutti i pacchetti di servizio easyDNS. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere record SRV necessari per Skype for Business.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verificare di essere proprietari del dominio con un record TXT

1. Accedere con [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) le proprie credenziali ed eseguire l'accesso. 
    
2. Sotto **l'intestazione tutti i** domini, selezionare **dns.**
    
3. Sotto **l'intestazione dei record TXT,** selezionare il pulsante di modifica (icona della chiave inglese). 
    
4. Immettere i record seguenti nei campi di testo:
    
    |**Host**|**Testo**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (utilizzare il valore fornito nella pagina Domini dell'interfaccia di amministrazione)  <br/> |
   
5. Selezionare **AVANTI.** 
    
6. Verificare che il record sia corretto e quindi selezionare **CONFIRM.** 
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato possa propagarsi su Internet e essere rilevato da Microsoft.
    
8. Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
    
9. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
10. Nella pagina **Domini** selezionare il dominio da verificare. 
    
11. Nella pagina **Installazione** selezionare **Avvia installazione.**
    
12. Nella pagina **Verifica dominio** selezionare **Verifica**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Aggiungere un record MX per instradare la posta elettronica a Microsoft

1. Accedere con [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) le proprie credenziali ed eseguire l'accesso. 
    
2. Sotto **l'intestazione tutti i** domini, selezionare **dns.**
    
3. Sotto **l'intestazione dei record MX,** selezionare il pulsante di modifica (icona chiave inglese). 
    
4. Immettere i record seguenti nei campi di testo:
    
    |**POSTA PER L'AREA**|**SERVER DI POSTA**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (Ottenere il \<domain-key\> valore dalla pagina Domini dell'interfaccia di amministrazione)  <br/> |0  <br/> |
   
2. Se si desidera salvare gli altri record MX a scopo di backup, copiarli da qualche parte. Prima di procedere, rimuovere tutti gli altri record MX qui.
    
5. Selezionare **AVANTI.** 
    
6. Verificare che il record sia corretto e quindi selezionare **CONFIRM.** 
    
## <a name="add-the-required-cname-records"></a>Aggiungere i record CNAME necessari

1. Accedere con [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) le proprie credenziali ed eseguire l'accesso. 
    
2. Sotto **l'intestazione tutti i** domini, selezionare **dns.**
    
3. Sotto **l'intestazione CNAME/Alias records** selezionare il pulsante edit (icona con chiave inglese). 
    
4. Immettere i record seguenti nei campi di testo:


    |**HOST**|**Indirizzo (deve terminare con un ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selezionare **AVANTI.** 
    
6. Verificare che il record sia corretto e quindi selezionare **CONFIRM.** 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata

1. Accedere con [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) le proprie credenziali ed eseguire l'accesso. 
    
2. Sotto **l'intestazione tutti i** domini, selezionare **dns.**
    
3. Sotto **l'intestazione dei record TXT,** selezionare il pulsante di modifica (icona della chiave inglese). 
    
4. Immettere i record seguenti nei campi di testo:
    
    |**Host**|**Testo**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selezionare **AVANTI.** 
    
6. Verificare che il record sia corretto e quindi selezionare **CONFIRM.** 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft

NOTA: I record SRV non sono attualmente disponibili a livello di servizio Domain Plus di easyDNS. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere record SRV 
  
1. Accedere con [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) le proprie credenziali ed eseguire l'accesso. 
    
2. Sotto **l'intestazione tutti i** domini, selezionare **dns.**
    
3. Sotto **l'intestazione record SRV,** selezionare il pulsante di modifica (icona della chiave inglese). 
    
4. Immettere i record seguenti nei campi di testo:
    
    |**SERVICE**|**PROTO**|**HOST**|**PRI**|**WGT**|**PORT**|**TARGET(Deve terminare con un ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selezionare **AVANTI.** 
    
6. Verificare che il record sia corretto e quindi selezionare **CONFIRM.** 
    

