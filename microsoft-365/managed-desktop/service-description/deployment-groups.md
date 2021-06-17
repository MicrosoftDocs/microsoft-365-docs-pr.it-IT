---
title: Gruppi di distribuzione dei dispositivi
description: Gruppi di distribuzione utilizzati per gestire gli aggiornamenti e altre modifiche
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985649"
---
# <a name="device-deployment-groups"></a>Gruppi di distribuzione dei dispositivi

Microsoft Managed Desktop i gruppi di distribuzione per gestire il rilascio di aggiornamenti e modifiche di configurazione ai dispositivi. I dispositivi vengono aggiunti automaticamente ai gruppi di distribuzione ("anelli" o "gruppi di aggiornamento") quando vengono registrati in Microsoft Managed Desktop. I gruppi di distribuzione consentono ai dispositivi di ricevere modifiche in una sequenza temporale in più fasi.

Potresti voler assegnare determinati dispositivi solo a scopo di test o designare specifici early adopter per ricevere prima le modifiche. Se si dispone di dispositivi critici, ad esempio quelli utilizzati dai dirigenti o che esecutivi, è consigliabile mantenerli nel gruppo che riceve gli aggiornamenti con la cadenza più lenta. Microsoft Managed Desktop consente di specificare che un dispositivo deve rimanere in uno dei gruppi seguenti.

- **Test**: ideale per i dispositivi usati per i test o per gli utenti che possono tollerare modifiche frequenti ed esposizione a nuove funzionalità e fornire anche feedback precoce. Questo gruppo riceve spesso modifiche e le esperienze in questo gruppo hanno un forte effetto. Il gruppo Test è esente da eventuali contratti di servizio stabiliti e dal supporto degli utenti. È meglio spostare prima solo alcuni dispositivi e quindi controllare l'esperienza utente. Microsoft Managed Desktop non assegna automaticamente i dispositivi a questo gruppo; avrà solo i dispositivi specificati.
- **Primo:** ideale per early adopter, volontari o validatori designati, professionisti IT o rappresentanti delle funzioni aziendali, cio? persone che possono convalidare le modifiche e fornire feedback sull'esperienza.
- **Broad** riceve le modifiche per ultime. La maggior parte dell'organizzazione si trova in genere in questo gruppo. Puoi anche specificare i dispositivi che devono essere in questo gruppo e devono ricevere modifiche solo per ultime perché stanno eseguendo funzioni business critical o appartengono a utenti con ruoli critici. 
- **Automatico:** selezionare questa opzione quando si Microsoft Managed Desktop assegnare automaticamente i dispositivi a uno degli altri gruppi. Non assegniamo automaticamente i dispositivi a Test. Se vuoi rilasciare un dispositivo specificato in precedenza in modo che possa essere assegnato di nuovo automaticamente, seleziona questa opzione. 

Microsoft Managed Desktop alcuni gruppi aggiuntivi per controllare le distribuzioni, ma non sarà possibile assegnare loro dispositivi. È tuttavia possibile spostare i dispositivi da tali gruppi a uno dei gruppi in questo articolo. Per ulteriori informazioni su come Windows gli aggiornamenti vengono gestiti in gruppi, vedere Come vengono gestiti gli aggiornamenti [in Microsoft Managed Desktop](updates.md).

Se un dispositivo fa parte di un gruppo specificato, il gruppo assegnato **da** dirà **Admin.** Se Microsoft Managed Desktop ha assegnato il gruppo, verrà visualizzato **Auto**. Mentre un dispositivo sta per passare a un gruppo, dirà **Pending.** Il **campo** Gruppo mostra sempre il gruppo in cui si trova il dispositivo e viene aggiornato solo al termine di uno spostamento.

> [!IMPORTANT]
> Non tentare di modificare direttamente l'appartenenza a questi gruppi. Seguire sempre i passaggi descritti in [Assegnare dispositivi a un gruppo di distribuzione.](../working-with-managed-desktop/assign-deployment-group.md)
