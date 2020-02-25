---
title: Creare record DNS in easyDNS per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in easyDNS per Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253130"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>Creare record DNS in easyDNS per Office 365

Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md). 
  
È necessario aggiungere tutti i seguenti record DNS al sito Web del registrar per instradare la posta a Office 365, utilizzare il dominio per i team e Skype for business e così via.
  
Nota: i record SRV non sono attualmente disponibili in tutti i pacchetti di servizi di easyDNS. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV necessari per Office 365 Skype for business.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verificare di essere proprietari del dominio con un record TXT

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Sotto l'intestazione **txt Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (utilizzare il valore specificato nella pagina Domains dell'interfaccia di amministrazione)  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato sia in grado di propagarsi su Internet e venga rilevato da Office 365.
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.
    
10. Nella pagina **Domains** selezionare il dominio che si sta verificando. 
    
11. Nella pagina **configurazione** , selezionare **Avvia installazione.**
    
12. Nella pagina **Verifica dominio** selezionare **Verifica**. 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Aggiungere un record MX per instradare la posta elettronica a Office 365

1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Sotto l'intestazione **MX Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**POSTA ELETTRONICA PER L'AREA**|**SERVER DI POSTA ELETTRONICA**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com (ottenere il \<valore della chiave\> di dominio dalla pagina Domains Admin Center)  <br/> |0  <br/> |
   
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
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365

Nota: i record SRV non sono attualmente disponibili in easyDNS ' Domain Plus Service Level. Potrebbe essere necessario eseguire l'aggiornamento a un livello di servizio superiore con easyDNS per aggiungere i record SRV 
  
1. Passare a [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e accedere con le credenziali. 
    
2. Nell'intestazione **tutti i domini** selezionare **DNS.**
    
3. Nell'intestazione **SRV Records** selezionare il pulsante modifica (icona della chiave inglese). 
    
4. Inserire nei campi di testo i record seguenti:
    
    |**SERVICE**|**PROTO**|**HOST**|**PRI**|**WGT**|**PORT**|**DESTINAZIONE (deve terminare con un ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selezionare **Avanti**. 
    
6. Verificare che il record sia corretto e quindi selezionare **conferma**. 
    

