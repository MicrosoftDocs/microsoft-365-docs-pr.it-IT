---
title: Caricare i dati non di Office 365 in Evidence
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
description: ''
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083836"
---
# <a name="load-non-office-365-data-into-evidence"></a>Caricare i dati non di Office 365 in Evidence

Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365. Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un working set, in modo da essere analizzati con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.

>[!Note]
>Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione. Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Informazioni preliminari
Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:

- Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.

- Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.

- Un caso di eDiscovery esistente.

- Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias @ NomeDominio* . L' *alias @ DomainName* deve essere Users Office 365 alias and Domain. È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice. La cartella radice può contenere solo le cartelle *alias @ DomainName* , non devono essere presenti file liberi nella cartella radice.

- Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.

- Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in Advanced eDiscovery

1. Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.  Fare clic sulla scheda **working set** , quindi selezionare il working set a cui si desidera caricare i dati non di Office 365.  Se non è stato ancora creato un working set, è possibile farlo adesso.  Infine, fare clic su **Gestisci set di lavoro** e quindi **visualizzare i caricamenti** nella sezione dati non di Office 365

2. Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.

![Caricare file](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.  Dopo la preparazione, fare clic sul pulsante **Avanti: carica file** .

![Importazione non Office 365-preparazione](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.  L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.

> [!NOTE]
> Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** . Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.  I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.

![Importazione/caricamento di file non di Office 365](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Non Office 365 Import-AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Infine, tornare alla conformità & di sicurezza e fare clic sul pulsante **Avanti: elabora file** .  Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.  È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel working set.  Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.

![File del processo di importazione non Office 365](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

