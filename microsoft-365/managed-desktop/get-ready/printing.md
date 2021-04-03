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
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574548"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparare risorse di stampa per Microsoft Managed Desktop

Quando si è pronti per la registrazione a Microsoft Managed Desktop, è consigliabile valutare i requisiti di stampa e determinare l'approccio giusto per l'ambiente. Sono disponibili tre opzioni:
 
- Distribuire la soluzione Microsoft Universal Print per semplificare l'individuazione delle stampanti da parte dei dispositivi Microsoft Managed Desktop. Per ulteriori informazioni, vedere [What is Universal Print.](/universal-print/fundamentals/universal-print-whatis)
- Distribuire le stampanti direttamente utilizzando uno script di PowerShell personalizzato. Seguire i passaggi descritti nella [sezione Configurare le stampanti](#set-up-local-printers) locali.
- Usa una soluzione di stampa cloud non Microsoft compatibile con i dispositivi Windows 10 aggiunti a un dominio di Azure Active Directory. La soluzione deve soddisfare i requisiti software per Microsoft Managed Desktop. Per altre informazioni, vedi [Requisiti dell'app Desktop gestito Microsoft.](../service-description/mmd-app-requirements.md)
 
In tutti i casi, se i driver della stampante non sono disponibili da Microsoft Update o microsoft Store, dovrai ottenerli autonomamente e averli in pacchetto per la distribuzione nei dispositivi Microsoft Managed Desktop con Microsoft Intune. Per altre informazioni, vedere [Intune Autonomo - Gestione app Win32](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurare stampanti locali

Se si è deciso di distribuire le stampanti utilizzando uno script di PowerShell personalizzato e si sono preparate le risorse di stampa, eseguire la procedura seguente per distribuire le stampanti condivise:

1.  Passare al portale Microsoft Managed Desktop.
2.  Inviare una richiesta con etichetta *Distribuzione* stampante nella sezione **Richieste >** supporto tecnico del portale di amministrazione, fornendo questi dettagli:
    - Tutti i percorsi UNC delle stampanti condivise che dovranno essere distribuiti per i dispositivi Desktop gestito Microsoft
    - Gruppi di utenti che richiedono l'accesso a queste stampanti condivise
3.  Usando il portale di amministrazione, ti inseriamo quando la richiesta è stata completata. Inizialmente la configurazione verrà distribuita solo nei dispositivi nel gruppo di distribuzione Test.
4.  È necessario verificare e verificare se la configurazione funziona come previsto. Rispondi usando la **scheda Discussione** nella richiesta di supporto per far sapere quando hai completato il test.
5.  La configurazione verrà quindi distribuita agli altri gruppi di distribuzione.

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
