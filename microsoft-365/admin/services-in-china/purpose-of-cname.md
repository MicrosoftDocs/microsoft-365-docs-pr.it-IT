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
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Qual è lo scopo del record aggiuntivo CNAME di Office 365 per MSOID?

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
> [!NOTE]
> Quanto segue si applica solo a **Office 365 gestito da 21Vianet.
  
Il record CNAME "MSOID" è necessario in Office 365. Si tratta infatti di un record che deve essere aggiunto per tutti i domini personalizzati, indipendentemente dall'abbonamento in uso. Perché è necessario? In termini semplificati, sostanzialmente è necessario per assicurare l'indirizzamento al server migliore per alcuni processi di autenticazione, per accelerare i tempi di risposta.
  
Dettagli tecnici: quando si esegue un'applicazione client che funziona con Office 365, come Skype for Business online, Outlook, Windows PowerShell o lo Strumento di sincronizzazione di Microsoft Azure Active Directory, le credenziali devono essere autenticate. Office 365 usa un record CNAME per puntare all'endpoint di autenticazione corretto in base alla posizione dell'utente, per garantire tempi di risposta rapidi per l'autenticazione.
  
Se tale record CNAME non è presente per il proprio dominio, queste applicazioni useranno un endpoint di autenticazione predefinito negli Stati Uniti, il che potrebbe rallentare l'autenticazione. Se il record CNAME non è configurato in modo corretto, ad esempio se il campo **Indirizzo di puntamento** contiene un errore di digitazione, queste applicazioni non verranno autenticate.
  
 **Se Office 365 gestisce i record DNS del dominio,** Office 365 configura automaticamente questo record CNAME. 
  
 **Se si gestiscono record DNS per il** dominio nell'host DNS, è possibile creare manualmente questo record seguendo le istruzioni [per l'host DNS.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
  
Se si sta pianificando una distribuzione di Office 365 e si desiderano ulteriori informazioni su tutti i record DNS che potrebbe essere necessario aggiungere o aggiornare, vedere Informazioni su di essi in Riferimento: record di Domain Name System esterni per [Office 365](../../enterprise/external-domain-name-system-records.md).
