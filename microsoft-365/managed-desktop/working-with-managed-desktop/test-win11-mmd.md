---
title: Anteprima e test Windows 11 con Microsoft Managed Desktop
description: Come ottenere Windows 11 nell'ambiente
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3ee0ca72f0eb3623755c9b342966915f520c485d
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458487"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Anteprima e test Windows 11 con Microsoft Managed Desktop

 Come registrare e partecipare al programma di test di compatibilità Windows 11 nell'ambiente Microsoft Managed Desktop 11. Per ulteriori informazioni su Windows 11 e Microsoft Managed Desktop in generale, vedere [Windows 11 e Microsoft Managed Desktop](../intro/win11-overview.md). 

## <a name="check-device-eligibility"></a>Verificare l'idoneità del dispositivo

Ad oggi, più del 95% dei Microsoft Managed Desktop soddisfa i criteri di idoneità per [Windows 11](/windows/whats-new/windows-11-requirements). Puoi richiedere dettagli sullo stato di idoneità dei dispositivi da Microsoft Managed Desktop. Per descrizione della richiesta, attenersi alla seguente procedura:

1. Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering. Se hai bisogno di altre info su come eseguire la richiesta, vedi [Supporto per gli amministratori.](admin-support.md)
2. Utilizzare questi valori per i campi:
    - Title: Windows 11 device eligibility
    - Tipo di richiesta: Richiesta di informazioni
    - Categoria: Dispositivi
    - Sottocategoria: Altro


## <a name="add-devices-to-the-windows-11-test-group"></a>Aggiungere dispositivi al gruppo di test Windows 11

Inizia aggiungendo dispositivi al gruppo di dispositivi (**\[ Modern Workplace Windows \] 11 Pre-Release Test Devices**) creato per il test e la valutazione Windows 11. I dispositivi in questo gruppo ottengono nuove Windows 11 build e Microsoft Managed Desktop di base non appena diventano disponibili e vengono monitorati per i problemi di affidabilità.

Puoi scegliere uno dei dispositivi esistenti o nuovi per i test di Windows 11, ma non registrare i dispositivi di produzione in questo gruppo a causa del rischio elevato di difetti o problemi di compatibilità nelle build non definitiva. Le assegnazioni precedenti del gruppo di dispositivi vengono rimosse dopo l'assegnazione a questo gruppo.

Per registrare i dispositivi nel gruppo di test non definitiva:

1. Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.
2. Utilizzare questi valori per i campi:
    - Title: Windows 11 compatibility enrollment
    - Tipo di richiesta: Richiesta di modifica
    - Categoria: Dispositivi
    - Sottocategoria: Assegnazione gruppo di distribuzione
3. Nel campo description elencare i numeri di serie dei dispositivi che si desidera utilizzare per Windows 11 test. Nota che, se presente, dei dispositivi specificati non sono ancora distribuiti nel tenant Microsoft Managed Desktop tenant.

## <a name="prioritize-applications-to-submit-to-test-base"></a>Assegnare priorità alle applicazioni da inviare a Test Base

Le applicazioni business-critical sono i candidati migliori per una maggiore convalida in un ambiente Windows 11. Possiamo aiutarti a definire la priorità delle app per Windows 11 test in base ai dati di utilizzo e affidabilità. Per richiedere i suggerimenti, attenersi alla seguente procedura:

1. Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering. Se hai bisogno di altre info su come eseguire la richiesta, vedi [Supporto per gli amministratori.](admin-support.md)
2. Utilizzare questi valori per i campi:
    - Title: Windows 11 Test Base candidates
    - Tipo di richiesta: Richiesta di informazioni
    - Categoria: App
    - Sottocategoria: Altro

## <a name="report-issues"></a>Segnalare i problemi

Se si verificano Windows 11 problemi di compatibilità con le app line-of-business o Microsoft 365, segnalarle a Microsoft per indagini e correzioni. Per segnalare un problema, attenersi alla seguente procedura:

1. Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.
2. Utilizzare questi valori per i campi:
    - Titolo: Windows 11 test di compatibilità
    - Tipo di richiesta: Evento imprevisto
    - Categoria: Dispositivi
    - Sottocategoria: Windows Upgrade/Update
3. Descrivere il comportamento e il livello di intralcio dell'azienda in un ambiente di produzione.

Microsoft Managed Desktop e gestisce i problemi relativi alle build non definitiva in base all'effetto sulla produttività. Sebbene la descrizione del servizio non riguardi i problemi relativi alle build non definitiva, microsoft conferirà agli amministratori dei clienti la risoluzione dei problemi che bloccano la produttività degli utenti prima di avviare la migrazione all'interno di un determinato tenant.