---
title: Creare record DNS quando il dominio è gestito da Google (eNom)
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Informazioni su come accedere a eNom e creare DNS tramite la pagina domini di Google.
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656856"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="0e10e-103">Creare record DNS quando il dominio è gestito da Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="0e10e-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="0e10e-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0e10e-105">Per eseguire la migrazione degli account di posta elettronica a Microsoft, è necessario creare un record DNS presso il registrar.</span><span class="sxs-lookup"><span data-stu-id="0e10e-105">To migrate your mail accounts to Microsoft, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="0e10e-106">Se il dominio è stato acquistato tramite Google durante l'iscrizione per l'account di **Google Apps for Work** , i record DNS vengono gestiti da Google ma registrati con eNom.</span><span class="sxs-lookup"><span data-stu-id="0e10e-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="0e10e-107">È possibile accedere a eNom e creare DNS tramite la pagina **domini** di Google.</span><span class="sxs-lookup"><span data-stu-id="0e10e-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="0e10e-108">Seguire i passaggi descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0e10e-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="0e10e-109">Creare il record DNS</span><span class="sxs-lookup"><span data-stu-id="0e10e-109">Create the DNS record</span></span>

1. <span data-ttu-id="0e10e-110">Nella [console di amministrazione di Google](https://www.google.com/work/apps/business), selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="0e10e-112">Immettere il proprio nome di dominio, quindi selezionare **Vai**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Icona del pulsante](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="0e10e-114">Nella parte inferiore della pagina, selezionare **altri controlli**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="0e10e-116">Selezionare **Domini**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="0e10e-118">Nella pagina **Domains** selezionare **Aggiungi/Rimuovi domini**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="0e10e-120">Nella pagina **Domains** selezionare **Advanced DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e10e-121">Se non si è acquistato un nome di dominio tramite Google durante l'iscrizione per l'account di **Google Apps for Work**, nella pagina **Domini** non sarà disponibile l'opzione **Impostazioni DNS avanzate**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="0e10e-122">Occorre invece accedere alle impostazioni DNS direttamente dal sito Web dell'host del dominio ed eseguire questo passaggio e i seguenti.</span><span class="sxs-lookup"><span data-stu-id="0e10e-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="0e10e-123">Per ulteriori informazioni, vedere [Access your G Suite Domain Settings](https://support.google.com/a/answer/54693?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="0e10e-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="0e10e-125">Nella pagina **impostazioni DNS avanzate** , selezionare **Accedi alla console DNS**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="0e10e-126">Annotare le informazioni relative al **nome di accesso** e alla **password**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="0e10e-127">Verranno richieste nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0e10e-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="0e10e-129">Usando le informazioni di **Nome di accesso** e **Password** della pagina **Impostazioni DNS avanzate**, accedere a **Gestione dominio** di Google.</span><span class="sxs-lookup"><span data-stu-id="0e10e-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="0e10e-131">Nella sezione **_ host Records della pagina _Domain_name_\*_**\* fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-131">On the **_domain_name_*_ page, in the _\* Host Records*\* section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="0e10e-133">Nella sezione **Host Records** selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="0e10e-135">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0e10e-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0e10e-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="0e10e-136">**HOST**</span></span>|<span data-ttu-id="0e10e-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="0e10e-137">**TXT VALUE**</span></span>|<span data-ttu-id="0e10e-138">**TIPO DI RECORD**</span><span class="sxs-lookup"><span data-stu-id="0e10e-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="0e10e-139">TXT</span><span class="sxs-lookup"><span data-stu-id="0e10e-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="0e10e-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="0e10e-140">This is an example.</span></span> <span data-ttu-id="0e10e-141">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0e10e-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> 
  
    [<span data-ttu-id="0e10e-142">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="0e10e-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="0e10e-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="0e10e-145">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="0e10e-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="0e10e-p105">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0e10e-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
