---
title: Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli
description: Creare ruoli e definire le autorizzazioni assegnate al ruolo nell'ambito dell'implementazione del controllo di accesso basato sui ruoli nel Microsoft Defender Security Center
keywords: ruoli utente, ruoli, controllo degli accessi in base al ruolo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065949"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Creare ruoli e assegnare il ruolo a un Azure Active Directory gruppo

La procedura seguente illustra come creare ruoli in Microsoft Defender Security Center. Si presuppone che siano già stati creati Azure Active Directory gruppi di utenti.

1. Accedere a [Microsoft Defender Security Center](https://securitycenter.windows.com/) con un account con un ruolo amministratore della sicurezza o amministratore globale assegnato.

2. Nel riquadro di spostamento selezionare Impostazioni > **ruoli**.

3. Selezionare **Aggiungi elemento**.

4. Immettere il nome del ruolo, la descrizione e le autorizzazioni che si desidera assegnare al ruolo.

5. Selezionare **Avanti** per assegnare il ruolo a un gruppo di sicurezza di Azure AD.

6. Usa il filtro per selezionare il gruppo di Azure AD a cui vuoi aggiungere questo ruolo.

7. **Salva e chiudi**.

8. Applica le impostazioni di configurazione.

> [!IMPORTANT]
> Dopo aver creato i ruoli, dovrai creare un gruppo di dispositivi e fornire l'accesso al gruppo di dispositivi assegnandolo a un ruolo appena creato.

### <a name="permission-options"></a>Opzioni di autorizzazione

- **Visualizzare i dati**
    - **Operazioni di sicurezza** - Visualizzare tutti i dati relativi alle operazioni di sicurezza nel portale
    - **Minacce e gestione delle vulnerabilità** - Visualizzare gestione di minacce e vulnerabilità dati nel portale

- **Azioni di correzione attive**
    - **Operazioni di sicurezza:** eseguire azioni di risposta, approvare o ignorare le azioni di correzione in sospeso, gestire gli elenchi consentiti/bloccati per l'automazione e gli indicatori
    - **Minacce e gestione delle vulnerabilità - Gestione delle eccezioni** - Creare nuove eccezioni e gestire le eccezioni attive
    - **Minacce e gestione delle vulnerabilità - Gestione** delle correzioni - Inviare nuove richieste di correzione, creare ticket e gestire le attività di correzione esistenti

- **Analisi degli** avvisi- Gestire gli avvisi, avviare indagini automatizzate, eseguire analisi, raccogliere pacchetti di analisi, gestire tag del dispositivo e scaricare solo file eseguibili portatili (PE) 

- **Gestire le impostazioni di sistema** del portale - Configurare le impostazioni di archiviazione, SIEM e le impostazioni delle API intel per le minacce (si applica a livello globale), impostazioni avanzate, caricamenti automatici di file, ruoli e gruppi di dispositivi

    > [!NOTE]
    > Questa impostazione è disponibile solo nel ruolo amministratore di Microsoft Defender for Endpoint (predefinito).

- **Gestire le impostazioni di sicurezza nel Centro** sicurezza : configurare le impostazioni di eliminazione degli avvisi, gestire le esclusioni delle cartelle per l'automazione, i dispositivi onboard e offboard e gestire le notifiche di posta elettronica, gestire il laboratorio di valutazione

- **Funzionalità di risposta in tempo reale**
    - **Comandi di** base:
        - Avviare una sessione di risposta in tempo reale
        - Eseguire comandi di risposta in tempo reale di sola lettura nel dispositivo remoto (esclusa la copia e l'esecuzione dei file)
    - **Comandi** avanzati:
        - Scaricare un file dal dispositivo remoto tramite risposta live
        - Scaricare file PE e non PE dalla pagina dei file
        - Upload un file nel dispositivo remoto
        - Visualizzare uno script dalla raccolta file
        - Eseguire uno script nel dispositivo remoto dalla raccolta file

Per altre informazioni sui comandi disponibili, vedi [Analizzare i dispositivi con risposta live.](live-response.md)
  
## <a name="edit-roles"></a>Modificare i ruoli

1. Accedere a [Microsoft Defender Security Center](https://securitycenter.windows.com/) account con il ruolo amministratore della sicurezza o amministratore globale assegnato.

2. Nel riquadro di spostamento selezionare Impostazioni > **ruoli**.

3. Seleziona il ruolo che vuoi modificare.

4. Fare clic su **Modifica**.

5. Modificare i dettagli o i gruppi assegnati al ruolo. 

6. Fare **clic su Salva e chiudi.**

## <a name="delete-roles"></a>Eliminare ruoli

1. Accedere a [Microsoft Defender Security Center](https://securitycenter.windows.com/) account con il ruolo amministratore della sicurezza o amministratore globale assegnato.

2. Nel riquadro di spostamento selezionare Impostazioni > **ruoli**.

3. Selezionare il ruolo che si desidera eliminare.

4. Fare clic sul pulsante a discesa e selezionare **Elimina ruolo.**

## <a name="related-topic"></a>Argomento correlato

- [Autorizzazioni di base dell'utente per accedere al portale](basic-permissions.md)
- [Creazione e gestione di gruppi di dispositivi](machine-groups.md)
