---
title: Configurazione di criteri di protezione da posta indesiderata
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Il filtro posta indesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) L'amministratore può visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti espressamente concepiti per soddisfare nel modo migliore le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma non è possibile modificarne la priorità.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599583"
---
# <a name="configure-the-anti-spam-policies"></a>Configurare i criteri di protezione dalla posta indesiderata

Il filtro posta indesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) L'amministratore può visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti espressamente concepiti per soddisfare nel modo migliore le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma non è possibile modificarne la priorità. 
  
Per ulteriori informazioni sulla configurazione dei criteri di protezione da posta indesiderata, vedere i seguenti argomenti:
  
[Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md)
  
[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> Per i clienti EOP indipendenti: per impostazione predefinita, i filtri di contenuto EOP inviano messaggi rilevati dalla posta indesiderata alla cartella Posta indesiderata di ciascun destinatario. Tuttavia, per assicurarsi che il **messaggio di spostamento all'azione della cartella posta indesiderata** funzionerà con le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  

