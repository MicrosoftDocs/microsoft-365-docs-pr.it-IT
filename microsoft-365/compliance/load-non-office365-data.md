---
title: Caricare i dati non Microsoft 365 in evidenza
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come utilizzare la caratteristica di importazione di contenuto non Office 365 per caricare i documenti non di Office 365 in una ricerca di dati.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 499b1074b9a1e2026804eab2ac958fe7392e98ea
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034414"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>Caricare i dati non Microsoft 365 in evidenza

Non tutti i documenti che potrebbe essere necessario analizzare in un'indagine di dati si trovano in Microsoft 365. Con la caratteristica di importazione di contenuto non Microsoft 365 è possibile caricare documenti che non risiedono in Microsoft 365 come elementi di prova in modo che possano essere analizzati in un'analisi dei dati.

## <a name="before-you-begin"></a>Prima di iniziare

Se si utilizza la funzionalità carica non Microsoft 365 come descritto in questa procedura, è necessario disporre di:

- Un abbonamento A Microsoft 365 o Office 365 E5.

- Tutti gli utenti di interesse il cui contenuto non Microsoft 365 verrà caricato devono disporre della licenza di componente aggiuntivo E5 o E5.

- Un caso di eDiscovery esistente.

- Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias@domainname*. Il *alias@domainname* deve essere l'alias e il dominio dell'utente. È possibile raccogliere tutte le cartelle di *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non devono essere presenti file liberi nella cartella radice.

- Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato in un computer che ha accesso alla struttura di cartelle di contenuto non Microsoft 365.

- Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>Caricare il contenuto non Microsoft 365 in un'indagine sui dati

1. Aprire **indagini sui dati** e passare all'analisi di caricamento dei dati non Microsoft 365.  Fare clic sulla scheda **Evidence** , quindi selezionare il set di prove a cui si desidera caricare i dati.  Se non è stato ancora creato un set di prove, è possibile farlo adesso.  Infine, fare clic su **Gestisci elementi di prova** e quindi **Visualizza i caricamenti** nella sezione dati

2. Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati Non Microsoft 365.

![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.  Al termine della preparazione, fare clic sul pulsante **Avanti: carica file** .

![Prepararsi per l'importazione di dati non Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non Microsoft 365 pianificati per l'importazione.  L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.

> [!NOTE]
> Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** . Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.  I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.

![Caricare i file per l'importazione di dati non Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Utilizzo di AzCopy per importare dati non Microsoft 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Infine, tornare alla conformità & di sicurezza e fare clic sul pulsante **Avanti: elabora file** .  Questo avvia l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.  È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completati, i nuovi file sono disponibili nel set di evidenze.  Al termine dell'elaborazione, è possibile chiudere la procedura guidata.

![File di processo di importazione non Microsoft 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

