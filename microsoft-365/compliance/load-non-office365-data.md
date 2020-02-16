---
title: Caricare i dati non di Office 365 in Evidence
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
description: ''
ms.openlocfilehash: 4db0b40d485c4c1107bdcb0d49616cadb15b1915
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072169"
---
# <a name="load-non-office-365-data-into-evidence"></a>Caricare i dati non di Office 365 in Evidence

Non tutti i documenti che potrebbe essere necessario analizzare in un'indagine dati saranno disponibili in Office 365. Con la funzionalità di importazione di contenuto non Office 365 è possibile caricare documenti che non risiedono in Office 365 in elementi di prova in modo che possano essere analizzati in un'analisi dei dati.

>[!Note]
>Per l'analisi dei dati è necessario un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione. Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Informazioni preliminari

Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:

- Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.

- Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.

- Un caso di eDiscovery esistente.

- Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias@domainname*. I *alias@domainname* devono essere utenti di Office 365 alias e Domain. È possibile raccogliere tutte le cartelle di *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non devono essere presenti file liberi nella cartella radice.

- Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.

- Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a>Caricare il contenuto non Office 365 in un'indagine sui dati

1. Aprire * * * * indagini sui dati * *, quindi l'analisi in cui verranno caricati i dati non di Office 365.  Fare clic sulla scheda **Evidence** , quindi selezionare il set di prove su cui si desidera caricare i dati non di Office 365.  Se non è stato ancora creato un set di prove, è possibile farlo adesso.  Infine, fare clic su **Gestisci elementi di prova** e quindi **Visualizza i caricamenti** nella sezione dati non di Office 365

2. Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.

![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.  Al termine della preparazione, fare clic sul pulsante **Avanti: carica file** .

![Prepararsi per l'importazione di dati non di Office 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.  L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.

> [!NOTE]
> Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** . Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.  I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.

![Caricare i file per l'importazione di dati non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Utilizzo di AzCopy per importare dati non di Office 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Infine, tornare alla conformità & di sicurezza e fare clic sul pulsante **Avanti: elabora file** .  Questo avvia l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.  È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completati, i nuovi file sono disponibili nel set di evidenze.  Al termine dell'elaborazione, è possibile chiudere la procedura guidata.

![File di processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

