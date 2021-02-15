---
title: Preparare risorse di stampa per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che la stampa funzioni senza problemi
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841400"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparare risorse di stampa per Microsoft Managed Desktop

Quando si è pronti per la registrazione a Microsoft Managed Desktop, è consigliabile valutare i requisiti di stampa e determinare l'approccio giusto per il proprio ambiente. Sono disponibili tre opzioni:
 
- Distribuire la soluzione Microsoft Universal Print per semplificare l'individuazione delle stampanti da parte dei dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [What is Universal Print.](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)
- Distribuire le stampanti direttamente utilizzando uno script di PowerShell personalizzato. Seguire i passaggi descritti nella [sezione Configurare le stampanti](#set-up-local-printers) locali.
- Usare una soluzione di stampa cloud non Microsoft compatibile con i dispositivi Windows 10 aggiunti a un dominio di Azure Active Directory. La soluzione deve soddisfare i requisiti software per Microsoft Managed Desktop. Per altre informazioni, vedi i [requisiti dell'app Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)
 
In tutti i casi, se i driver della stampante non sono disponibili da Microsoft Update o da Microsoft Store, dovrai ottenerli manualmente e averli in pacchetto per la distribuzione nei dispositivi Microsoft Managed Desktop con Microsoft Intune. Per altre informazioni, vedere [Intune autonomo - Gestione app Win32](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurare stampanti locali

Se si è deciso di distribuire le stampanti utilizzando uno script di PowerShell personalizzato e si sono preparate le risorse di stampa, eseguire la procedura seguente per distribuire stampanti condivise:

1.  Passare al portale Microsoft Managed Desktop.
2.  Invia una richiesta di distribuzione *della* stampante etichettata nella sezione Richieste > **supporto** tecnico del portale di amministrazione, fornendo questi dettagli:
    - Tutti i percorsi UNC delle stampanti condivise che dovranno essere distribuiti per i dispositivi Microsoft Managed Desktop
    - Gruppi di utenti che richiedono l'accesso a queste stampanti condivise
3.  Usando il portale di amministrazione, ti inseriamo quando la richiesta è stata completata. Inizialmente la configurazione verrà distribuita solo ai dispositivi nel gruppo di distribuzione Test.
4.  È necessario verificare e verificare se la configurazione funziona come previsto. Rispondi usando la **scheda Discussione** nella richiesta di supporto per inserirci quando hai completato il test.
5.  La configurazione verrà quindi distribuita agli altri gruppi di distribuzione.
