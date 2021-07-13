---
title: Requisiti per Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP), ottenere un elenco di requisiti da utilizzare Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395187"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Requisiti per Microsoft 365 Lighthouse

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i requisiti elencati in questo articolo. Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse è un portale di amministrazione che consente ai provider di servizi gestiti (MSP) di proteggere e gestire dispositivi, dati e utenti su larga scala per i clienti di piccole e medie imprese (SMB).  

Gli SSP devono essere registrati nel programma Cloud Solution Provider (CSP) come rivenditore indiretto o partner di Fatturazione diretta per usare Microsoft 365 Lighthouse.  

Inoltre, ogni tenant del cliente MSP deve essere idoneo per Microsoft 365 Lighthouse soddisfare i requisiti seguenti: 
 
- Privilegi di amministratore delegato (DAP) per msp 
- Almeno una licenza Microsoft 365 Business Premium licenza 
- Meno di 500 utenti con licenza  

## <a name="requirements-for-enablingdevice-management"></a>Requisiti per abilitare la gestione dei dispositivi   

Per visualizzare i dispositivi tenant dei clienti nelle pagine di gestione dei dispositivi, un msp deve:    

- Registrare tutti i dispositivi dei clienti in Microsoft Endpoint Manager (MEM).Per altre informazioni, vedi [Registrare i dispositivi in Microsoft Intune](/mem/intune/enrollment/).
- Assegnare criteri di conformità a tutti i dispositivi dei clienti.Per ulteriori informazioni, vedere [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy). 

## <a name="requirements-for-enabling-usermanagement"></a>Requisiti per l'abilitazione della gestione degli utenti 

Per visualizzare i dati dei clienti nei report nelle pagine di gestione degli utenti, inclusi gli utenti rischiosi, l'autenticazione a più fattori e la reimpostazione della password, i tenant dei clienti devono disporre di licenze per Azure Active Directory Premium P1 o versioni successive. Azure AD Premium P1 è incluso in Microsoft 365 Business Premium.   

## <a name="requirements-for-enablingthreat-management"></a>Requisiti per l'abilitazione della gestione delle minacce 

Per visualizzare i dispositivi tenant dei clienti e le minacce nelle pagine di gestione delle minacce, è necessario registrare tutti i dispositivi tenant dei clienti in Microsoft Endpoint Manager (MEM) e proteggerli eseguendo Antivirus Microsoft Defender.  

Per altre informazioni, vedi [Registrare i dispositivi in Microsoft Intune](/mem/intune/enrollment/).  

Antivirus Microsoft Defender fa parte del sistema operativo Windows ed è abilitato per impostazione predefinita nei dispositivi che eseguono Windows 10.  

> [!NOTE] 
> Se si utilizza una soluzione antivirus non Microsoft e non Antivirus Microsoft Defender, Antivirus Microsoft Defender viene disabilitata automaticamente. Quando si disinstalla la soluzione antivirus non Microsoft, l'Antivirus Microsoft Defender viene attivata automaticamente per proteggere i dispositivi Windows dalle minacce.    

## <a name="related-content"></a>Contenuto correlato   

[Configurare Microsoft 365 Lighthouse sicurezza del portale](m365-lighthouse-configure-portal-security.md) (articolo)\
[Microsoft 365 Lighthouse panoramica della pagina Conformità dispositivo](m365-lighthouse-device-compliance-page-overview.md) (articolo)\
[Microsoft 365 Lighthouse panoramica della pagina Utenti](m365-lighthouse-users-page-overview.md) (articolo)\
[Microsoft 365 Lighthouse panoramica della pagina gestione delle minacce](m365-lighthouse-threat-management-page-overview.md) (articolo)\
[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml)   (articolo)

