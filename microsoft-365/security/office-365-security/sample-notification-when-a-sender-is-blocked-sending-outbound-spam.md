---
title: Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: "Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si configura il criterio di posta indesiderata in uscita riceverà un messaggio di posta elettronica di notifica simile al seguente:"
ms.openlocfilehash: badcd34bc35c8cc3cdd1cd06edefb87c6818e2e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084760"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.

Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si [Configura il criterio di posta indesiderata in uscita](configure-the-outbound-spam-policy.md) riceverà un messaggio di posta elettronica di notifica simile al seguente: 
  
 **Indirizzo mittente:** spamalerts@microsoft.com 
  
 **Oggetto:** Notifica posta indesiderata in uscita - a \<  *account name*  \> è stato impedito di inviare posta indesiderata in uscita 
  
 **Corpo:** Si tratta di una risposta automatica del sistema di analisi di posta indesiderata di Exchange Online Protection. 
  
Sono stati rilevati volumi elevati di posta elettronica contrassegnata come posta indesiderata o altro comportamento sospetto da parte di questa organizzazione. Ai seguenti account di posta elettronica è stato impedito di inviare posta elettronica (continueranno a ricevere messaggi di posta elettronica):
  
\< *account name*  \> 
  
È probabile che questo account di posta elettronica sia stato compromesso. Attenersi alla seguente procedura:
  
1. Risolvere questo problema internamente effettuando le seguenti operazioni:
    
  - Modificare la password dell'account.
    
  - Determinare la modalità con cui l'account è stato compromesso.
    
  - Adottare precauzioni per garantire che tale vulnerabilità non venga sfruttata di nuovo.
    
  - Confermare che nella coda della posta in uscita siano stati cancellati tutti i messaggi incriminati.
    
2. Contattare il supporto tecnico Microsoft tramite il consueto canale di contatto.
    
3. Spiegare che a un utente è stato impedito di inviare posta elettronica e che il problema è stato gestito.
    
4. L'agente creerà un ticket di supporto con le informazioni fornite e riassegnerà la pratica per sbloccare il dominio o l'indirizzo di posta elettronica.
    
5. Dopo che l'indirizzo è stato sbloccato e non ci sono altri problemi in sospeso, si verrà informati e avvisati dello sblocco.
    
Grazie per l'aiuto offerto nel controllo della posta elettronica indesiderata.
  
Exchange Online Protection.
  
\*\*NOTA - Non rispondere a questo messaggio, in quanto è stato inviato da un indirizzo di posta elettronica che non viene controllato.\*\*
  
> [!TIP]
> È inoltre possibile contattare il supporto tramite le opzioni descritte in [Help and Support for EOP](help-and-support-for-eop.md). 
  

