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
ms.openlocfilehash: 5198691a38b179a5491a36de95531edb9f32d691
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322224"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparare risorse di stampa per Microsoft Managed Desktop

Quando si è pronti per eseguire la registrazione in Microsoft Managed Desktop, è consigliabile valutare i requisiti di stampa e determinare l'approccio appropriato per l'ambiente in uso. Sono disponibili tre opzioni:
 
- Distribuire la soluzione Microsoft Universal Print per rendere più semplice per i dispositivi desktop Microsoft gestiti individuare le stampanti. Per ulteriori informazioni, vedere [che cos'è la stampa universale](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis).
- Distribuire le stampanti direttamente tramite uno script di PowerShell personalizzato. Per eseguire questa operazione, seguire i passaggi della sezione [set up Printers local](#set-up-local-printers) .
- Utilizzare una soluzione di stampa cloud non Microsoft compatibile con i dispositivi Windows 10 aggiunti a un dominio di Azure Active Directory. La soluzione deve soddisfare i requisiti software per Microsoft Managed Desktop. Per ulteriori informazioni, vedere [requisiti delle app di Microsoft Managed Desktop](../service-description/mmd-app-requirements.md).
 
In tutti i casi, se i driver della stampante non sono disponibili da Microsoft Update o Microsoft Store, è necessario ottenerli personalmente e farli impacchettare per la distribuzione ai dispositivi Microsoft Managed Desktop con Microsoft Intune. Per ulteriori informazioni, vedere [Intune standalone-Win32 app Management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurare le stampanti locali

Se si è deciso di distribuire le stampanti tramite uno script di PowerShell personalizzato e si sono preparate le risorse di stampa, attenersi alla seguente procedura per distribuire le stampanti condivise:

1.  Passare al portale Microsoft Managed Desktop.
2.  Inviare una richiesta di distribuzione con l'etichetta della *stampante* nella sezione **supporto > richieste di supporto** del portale di amministrazione, in cui vengono fornite queste informazioni:
    - Tutti i percorsi UNC per le posizioni della stampante condivise che dovranno essere distribuite per i dispositivi Microsoft Managed Desktop
    - Gruppi di utenti che richiedono l'accesso a queste stampanti condivise
3.  Usando il portale di amministrazione, è possibile sapere quando la richiesta è stata completata. Inizialmente verrà distribuita solo la configurazione ai dispositivi nel gruppo di distribuzione di test.
4.  È necessario testare e verificare se la configurazione funziona come previsto. Rispondere utilizzando la scheda **discussione** nella richiesta di supporto per farci sapere quando è stato completato il testing.
5.  La configurazione verrà quindi distribuita negli altri gruppi di distribuzione.
