---
title: Creare record DNS in easyDNS per Microsoft
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in easyDNS per Microsoft.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645552"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Creare record DNS in easyDNS per Microsoft

Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md). 
  
È necessario aggiungere tutti i seguenti record DNS al sito Web del registrar per instradare la posta a Microsoft, utilizzare il dominio per i team e Skype for business e così via.
  
Nota: i record SRV non sono attualmente disponibili in tutti i pacchetti di servizi di easyDNS. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV necessari per Skype for business.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verificare di essere proprietari del dominio con un record TXT

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**Host**|**Testo**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (utilizzare il valore specificato nella pagina Domains dell'interfaccia di amministrazione)  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato sia in grado di propagarsi su Internet e venga rilevato da Microsoft.
    
8. Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
    
9. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
10. Nella pagina **Domini** selezionare il dominio da verificare. 
    
11. Nella pagina **configurazione** , selezionare **Avvia installazione.**
    
12. Nella pagina **Verifica dominio** selezionare **Verifica**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Aggiungere un record MX per instradare la posta elettronica a Microsoft

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Sotto l'intestazione **MX Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**POSTA ELETTRONICA PER L'AREA**|**SERVER DI POSTA ELETTRONICA**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>. mail.protection.outlook.com (ottenere il \<domain-key\> valore dalla pagina Domains dell'interfaccia di amministrazione)  <br/> |0  <br/> |
   
2. Se si desidera salvare gli altri record MX per scopi di backup, copiarli in un punto qualsiasi. Prima di procedere, rimuovere tutti gli altri record MX qui.
    
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
## <a name="add-the-required-cname-records"></a>Aggiungere i record CNAME necessari

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Nella sezione **CNAME/alias Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:


    |**HOST**|**Indirizzo (deve terminare con un ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**Host**|**Testo**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft

Nota: i record SRV non sono attualmente disponibili in easyDNS ' Domain Plus Service Level. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV 
  
1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Nell'intestazione **SRV Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**SERVICE**|**PROTO**|**HOST**|**PRI**|**WGT**|**PORT**|**DESTINAZIONE (deve terminare con un ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    

