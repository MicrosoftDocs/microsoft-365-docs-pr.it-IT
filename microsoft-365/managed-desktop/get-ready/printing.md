---
title: Preparare risorse di stampa per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che la stampa funzioni senza problemi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287210"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparare risorse di stampa per Microsoft Managed Desktop

Quando si è pronti per la registrazione a Microsoft Managed Desktop, è consigliabile valutare i requisiti di stampa e determinare l'approccio giusto per l'ambiente. Sono disponibili tre opzioni:

- Distribuire la soluzione Microsoft Universal Print per semplificare l'individuazione delle stampanti Microsoft Managed Desktop dispositivi. Per ulteriori informazioni, vedere [What is Universal Print.](/universal-print/fundamentals/universal-print-whatis)
- Distribuire le stampanti direttamente utilizzando uno script di PowerShell personalizzato. Seguire i passaggi descritti nella [sezione Configurare le stampanti](#set-up-local-printers) locali.
- Usa una soluzione di stampa cloud non Microsoft compatibile con i dispositivi Windows 10 aggiunti a un Azure Active Directory dominio. La soluzione deve soddisfare i requisiti software per Microsoft Managed Desktop. Per altre informazioni, vedi requisiti [Microsoft Managed Desktop'app](../service-description/mmd-app-requirements.md).
 
In tutti i casi, se i driver della stampante non sono disponibili da Microsoft Update o dal Microsoft Store, dovrai ottenerli manualmente e averli in pacchetto per la distribuzione nei dispositivi Microsoft Managed Desktop con Microsoft Intune. Per altre informazioni, vedere [Intune Autonomo - Gestione app Win32](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurare stampanti locali

Se si è deciso di distribuire le stampanti utilizzando uno script di PowerShell personalizzato e si sono preparate le risorse di stampa, eseguire la procedura seguente per distribuire le stampanti condivise:

1. Passare al portale Microsoft Managed Desktop.
2. Inviare una richiesta con etichetta *Distribuzione* stampante nella sezione **Richieste >** supporto tecnico del portale di amministrazione, fornendo questi dettagli:
    - Tutti i percorsi UNC per i percorsi delle stampanti condivise che dovranno essere distribuiti per Microsoft Managed Desktop dispositivi
    - Gruppi di utenti che richiedono l'accesso a queste stampanti condivise
3. Usando il portale di amministrazione, ti inseriamo quando la richiesta è stata completata. Inizialmente la configurazione verrà distribuita solo nei dispositivi nel gruppo di distribuzione Test.
4. È necessario verificare e verificare se la configurazione funziona come previsto. Rispondi usando la **scheda Discussione** nella richiesta di supporto per far sapere quando hai completato il test.
5. La configurazione verrà quindi distribuita agli altri gruppi di distribuzione.

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare le risorse di stampa per Microsoft Managed Desktop](printing.md) (questo articolo)
