---
title: Creare e gestire tag di dispositivi
description: Usare i tag del dispositivo per raggruppare i dispositivi per acquisire il contesto e abilitare la creazione dinamica dell'elenco come parte di un evento imprevisto
keywords: tag, tag dispositivo, gruppi di dispositivi, gruppi, correzione, livello, regole, gruppo aad, ruolo, assegnare, classificare
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
ms.openlocfilehash: 83dd2483b93b2f4fe520973ce05346f59baf2f28
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453584"
---
# <a name="create-and-manage-device-tags"></a>Creare e gestire tag di dispositivi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aggiungere tag nei dispositivi per creare un'affiliazione a un gruppo logico. I tag del dispositivo supportano la mappatura corretta della rete, consentendo di collegare tag diversi per acquisire il contesto e consentire la creazione di elenchi dinamici come parte di un incidente. I tag possono essere usati come filtro nella **visualizzazione elenco** Dispositivi o per raggruppare i dispositivi. Per altre informazioni sul raggruppamento dei dispositivi, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)

Puoi aggiungere tag nei dispositivi usando i modi seguenti:

- Usando il portale
- Impostando un valore della chiave del Registro di sistema

> [!NOTE]
> Potrebbe verificarsi una latenza tra il momento in cui un tag viene aggiunto a un dispositivo e la relativa disponibilità nell'elenco dei dispositivi e nella pagina del dispositivo.  

Per aggiungere tag del dispositivo usando l'API, vedere [Aggiungere o rimuovere l'API dei tag del dispositivo](add-or-remove-machine-tags.md).

## <a name="add-and-manage-device-tags-using-the-portal"></a>Aggiungere e gestire i tag per i dispositivi tramite il portale

1. Selezionare il dispositivo in cui gestire i tag. È possibile selezionare o cercare un dispositivo in una delle seguenti visualizzazioni:

   - **Dashboard delle operazioni di** sicurezza: selezionare il nome del dispositivo nella sezione Dispositivi principali con avvisi attivi.
   - **Coda degli avvisi**: selezionare il nome del dispositivo accanto all'icona del dispositivo dalla coda degli avvisi.
   - **Elenco dispositivi**: selezionare il nome del dispositivo nell'elenco dei dispositivi.
   - **Casella di ricerca**: selezionare Dispositivo dal menu a discesa e inserire il nome del dispositivo.

     È anche possibile accedere alla pagina di avviso tramite le visualizzazioni file e IP.

2. Selezionare **Gestisci tag** dalla riga Azioni di risposta.

    :::image type="content" alt-text="Immagine del pulsante Gestisci tag." source="images/manage-tags-option.png":::

3. Digitare per trovare o creare tag

    :::image type="content" alt-text="Immagine dell'aggiunta di tag in un dispositivo1." source="images/create-new-tag.png":::

I tag vengono aggiunti alla visualizzazione del dispositivo e verranno visualizzati anche nella **visualizzazione elenco** Dispositivi. Puoi quindi usare il filtro **Tag** per visualizzare l'elenco pertinente dei dispositivi.

>[!NOTE]
> Il filtro potrebbe non funzionare sui nomi di tag che contengono parentesi.<br>
> Quando si crea un nuovo tag, viene visualizzato un elenco di tag esistenti. L'elenco mostra solo i tag creati tramite il portale. I tag esistenti creati dai dispositivi client non verranno visualizzati.

È inoltre possibile eliminare i tag da questa visualizzazione.

:::image type="content" alt-text="Immagine dell'aggiunta di tag in un dispositivo2." source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Aggiungere tag dispositivo impostando un valore di chiave del Registro di sistema

>[!NOTE]
> Applicabile solo nei dispositivi seguenti:
>- Windows 10 versione 1709 o successiva
>- Windows Server, versione 1803 o successiva
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> Il numero massimo di caratteri che è possibile impostare in un tag è 200.

I dispositivi con tag simili possono essere utili quando devi applicare un'azione contestuale a un elenco specifico di dispositivi.

Usa la seguente voce della chiave del Registro di sistema per aggiungere un tag in un dispositivo:

- Chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Valore della chiave del Registro di sistema (REG_SZ): `Group`
- Dati chiave del Registro di sistema: `Name of the tag you want to set`

>[!NOTE]
>Il tag del dispositivo fa parte del report delle informazioni sul dispositivo generato una volta al giorno. In alternativa, puoi scegliere di riavviare l'endpoint che trasferirebbe un nuovo report di informazioni sul dispositivo.
> 
> Se devi rimuovere un tag aggiunto usando la chiave del Registro di sistema precedente, cancella il contenuto dei dati della chiave del Registro di sistema invece di rimuovere la chiave "Group".
