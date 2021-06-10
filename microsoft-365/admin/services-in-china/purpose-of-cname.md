---
title: Qual è lo scopo del record aggiuntivo CNAME di Office 365 per MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Ulteriori informazioni sul record CNAME "MSOID" in Office 365 che indirizza l'utente al server migliore per i processi di autenticazione, in modo da ottenere una risposta più veloce.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914307"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="fbef2-103">Qual è lo scopo del record aggiuntivo CNAME di Office 365 per MSOID?</span><span class="sxs-lookup"><span data-stu-id="fbef2-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="fbef2-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="fbef2-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="fbef2-105">Quanto segue si applica solo a \*\*Office 365 gestito da 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="fbef2-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="fbef2-p101">Il record CNAME "MSOID" è necessario in Office 365. Si tratta infatti di un record che deve essere aggiunto per tutti i domini personalizzati, indipendentemente dall'abbonamento in uso. Perché è necessario? In termini semplificati, sostanzialmente è necessario per assicurare l'indirizzamento al server migliore per alcuni processi di autenticazione, per accelerare i tempi di risposta.</span><span class="sxs-lookup"><span data-stu-id="fbef2-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="fbef2-p102">Dettagli tecnici: quando si esegue un'applicazione client che funziona con Office 365, come Skype for Business online, Outlook, Windows PowerShell o lo Strumento di sincronizzazione di Microsoft Azure Active Directory, le credenziali devono essere autenticate. Office 365 usa un record CNAME per puntare all'endpoint di autenticazione corretto in base alla posizione dell'utente, per garantire tempi di risposta rapidi per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="fbef2-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="fbef2-p103">Se tale record CNAME non è presente per il proprio dominio, queste applicazioni useranno un endpoint di autenticazione predefinito negli Stati Uniti, il che potrebbe rallentare l'autenticazione. Se il record CNAME non è configurato in modo corretto, ad esempio se il campo **Indirizzo di puntamento** contiene un errore di digitazione, queste applicazioni non verranno autenticate.</span><span class="sxs-lookup"><span data-stu-id="fbef2-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="fbef2-114">**Se Office 365 i record DNS** del dominio, Office 365 il record CNAME automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fbef2-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="fbef2-115">**Se si gestiscono record DNS per il** dominio nell'host DNS, è possibile creare manualmente questo record seguendo le istruzioni [per l'host DNS.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="fbef2-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="fbef2-116">Se si sta pianificando una distribuzione di Office 365 e si desiderano ulteriori informazioni su tutti i record DNS che potrebbe essere necessario aggiungere o aggiornare, vedere Informazioni su di essi in [Riferimento:](../../enterprise/external-domain-name-system-records.md)record del sistema dei nomi di dominio esterno per Office 365 .</span><span class="sxs-lookup"><span data-stu-id="fbef2-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
