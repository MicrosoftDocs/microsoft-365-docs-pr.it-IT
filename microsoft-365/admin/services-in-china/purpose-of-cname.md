---
title: Qual è lo scopo del record aggiuntivo CNAME di Office 365 per MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Per ulteriori informazioni, vedere il record CNAME ' MSOID ' in Office 365 che consente di indirizzare il server migliore ai processi di autenticazione, in modo da ottenere una risposta più rapida.
monikerRange: o365-21vianet
ms.openlocfilehash: a7c59829419ac8e7db400b079681ccf5bff199d6
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053849"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Qual è lo scopo del record aggiuntivo CNAME di Office 365 per MSOID?

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
> [!NOTE]
> La seguente procedura si applica solo a * * Office 365 gestito da 21Vianet.
  
Il record CNAME "MSOID" è necessario in Office 365. Si tratta infatti di un record che deve essere aggiunto per tutti i domini personalizzati, indipendentemente dall'abbonamento in uso. Perché è necessario? In termini semplificati, sostanzialmente è necessario per assicurare l'indirizzamento al server migliore per alcuni processi di autenticazione, per accelerare i tempi di risposta.
  
Dettagli tecnici: quando si esegue un'applicazione client che funziona con Office 365, come Skype for Business online, Outlook, Windows PowerShell o lo Strumento di sincronizzazione di Microsoft Azure Active Directory, le credenziali devono essere autenticate. Office 365 usa un record CNAME per puntare all'endpoint di autenticazione corretto in base alla posizione dell'utente, per garantire tempi di risposta rapidi per l'autenticazione.
  
Se tale record CNAME non è presente per il proprio dominio, queste applicazioni useranno un endpoint di autenticazione predefinito negli Stati Uniti, il che potrebbe rallentare l'autenticazione. Se il record CNAME non è configurato in modo corretto, ad esempio se il campo **Indirizzo di puntamento** contiene un errore di digitazione, queste applicazioni non verranno autenticate.
  
 **Se Office 365 gestisce i record DNS del dominio,** Office 365 consente di configurare il record CNAME per l'utente. 
  
 **Se si gestiscono i record DNS per il dominio presso l'host DNS,** è necessario creare personalmente questo record [attenendosi alle istruzioni per l'host DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).
  
Se si sta pianificando una distribuzione di Office 365 e si desiderano ulteriori informazioni su tutti i record DNS che potrebbe essere necessario aggiungere o aggiornare, leggere informazioni su di essi in [Reference: record di sistema per il nome di dominio esterno per Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

