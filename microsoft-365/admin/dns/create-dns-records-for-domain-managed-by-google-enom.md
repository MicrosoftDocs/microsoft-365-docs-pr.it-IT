---
title: Creare record DNS quando il dominio è gestito da Google (eNom)
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
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Informazioni su come accedere a eNom e creare DNS tramite la pagina domini di Google.
ms.openlocfilehash: 566b3990c6cc3080eac9d1367531eea42ab135d1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362501"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Creare record DNS quando il dominio è gestito da Google (eNom)

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Per eseguire la migrazione degli account di posta elettronica a Office 365, è necessario creare un record DNS presso il proprio registrar.
  
Se il dominio è stato acquistato tramite Google durante l'iscrizione per l'account di **Google Apps for Work** , i record DNS vengono gestiti da Google ma registrati con eNom. 
  
È possibile accedere a eNom e creare DNS tramite la pagina **domini** di Google. Seguire i passaggi descritti in questo articolo. 
  
## <a name="create-the-dns-record"></a>Creare il record DNS

1. Nella [console di amministrazione di Google](https://www.google.com/work/apps/business), selezionare **Accedi**.
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Immettere il proprio nome di dominio, quindi selezionare **Vai**.
    
    ![Icona del pulsante](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Nella parte inferiore della pagina, selezionare **altri controlli**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Selezionare **Domini**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. Nella pagina **Domains** selezionare **Aggiungi/Rimuovi domini**.
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Nella pagina **Domains** selezionare **Advanced DNS Settings**.
    
    > [!NOTE]
    > Se non si è acquistato un nome di dominio tramite Google durante l'iscrizione per l'account di **Google Apps for Work**, nella pagina **Domini** non sarà disponibile l'opzione **Impostazioni DNS avanzate**. Occorre invece accedere alle impostazioni DNS direttamente dal sito Web dell'host del dominio ed eseguire questo passaggio e i seguenti. Per ulteriori informazioni, vedere [Access your G Suite Domain Settings](https://support.google.com/a/answer/54693?hl=en) . 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. Nella pagina **impostazioni DNS avanzate** , selezionare **Accedi alla console DNS**. Annotare le informazioni relative al **nome di accesso** e alla **password**. Verranno richieste nel passaggio successivo. 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Usando le informazioni di **Nome di accesso** e **Password** della pagina **Impostazioni DNS avanzate**, accedere a **Gestione dominio** di Google. 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. Nella sezione **Host Records** della pagina ***Domain_name*** selezionare **modifica**.
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Nella sezione **Host Records** selezionare **Aggiungi nuovo**.
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**HOST**|**TXT VALUE**|**TIPO DI RECORD**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365. 
  
    [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)
  
12. Selezionare **Salva**.
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Selezionare **Salva modifiche**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
