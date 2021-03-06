---
title: Caricare dati non di Microsoft 365 in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come importare dati non Microsoft 365 in un set di revisione per l'analisi in Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903502"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Caricare dati non di Microsoft 365 in un insieme da rivedere

Non tutti i documenti che è necessario analizzare in Advanced eDiscovery si trovano in Microsoft 365. Con la funzionalità di importazione dei dati non di Microsoft 365 in Advanced eDiscovery, è possibile caricare in un insieme da rivedere i documenti che non si trovano in Microsoft 365. In questo articolo viene illustrato come portare i documenti non Microsoft 365 in Advanced eDiscovery per l'analisi.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisiti per caricare contenuto non Office 365 contenuto

L'utilizzo della funzionalità di caricamento non Microsoft 365 descritta in questo articolo richiede che si abbia quanto segue:Using the upload non-Microsoft 365 feature described in this article requires that you have the following:

- A tutti i custodi a cui si desidera associare Microsoft 365 contenuto non Microsoft 365 deve essere assegnata la licenza appropriata. Per ulteriori informazioni, vedere [Introduzione a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Un caso Advanced eDiscovery esistente.

- I custodi devono essere aggiunti al caso prima di poter caricare e associare i dati non Microsoft 365 al caso.

- I dati non Microsoft 365 devono essere un tipo di file supportato da Advanced eDiscovery. Per altre informazioni, vedere [Tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Tutti i file caricati in un insieme da rivedere devono trovarsi in cartelle e ciascuna cartella è associata a un responsabile specifico. I nomi di queste cartelle devono seguire il seguente formato di denominazione: *alias@nomedominio*. La denominazione alias@nomedominio deve contenere alias e dominio di Microsoft 365 dell'utente. È possibile raccogliere tutte le alias@domainname in una cartella radice. La cartella radice può contenere solo alias@domainname cartelle. I file non disponibili nella cartella radice non sono supportati.

   La struttura delle cartelle per i dati non Microsoft 365 che si desidera caricare è simile all'esempio seguente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei custodi nel caso.

   ![Struttura di cartelle di caricamento dati non Microsoft 365 dati](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Un account assegnato al gruppo di ruoli Manager eDiscovery (e aggiunto come amministratore di eDiscovery).

- Lo strumento AzCopy v8.1 installato in un computer che ha accesso alla struttura di cartelle di contenuto non Microsoft 365 contenuto. Per installare AzCopy, vedere [Trasferire dati con AzCopy v8.1 in Windows](/previous-versions/azure/storage/storage-use-azcopy). Assicurarsi di installare AzCopy nel percorso predefinito, ovvero **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**. È necessario utilizzare AzCopy v8.1. Altre versioni di AzCopy potrebbero non funzionare quando si caricano dati non Microsoft 365 in Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Upload contenuto non Microsoft 365 in Advanced eDiscovery

1. In quanto responsabile di eDiscovery o amministratore di eDiscovery, aprire Advanced eDiscovery e passare al caso in cui i dati non Microsoft 365 verranno caricati.  

2. Fare **clic su Rivedi** set e quindi selezionare il set di recensioni in cui caricare i dati non Microsoft 365 revisione.  Se non si dispone di un set di recensioni, è possibile crearne uno. 
 
3. Nell'insieme da rivedere fare clic su **Gestisci insieme da rivedere**, quindi selezionare **Visualizzare i caricamenti** nel riquadro **Dati non di Microsoft 365**.

4. Fare clic su **Caricare i file** per avviare la procedura guidata di importazione dei dati.

   ![Carica file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   Il primo passaggio nella procedura guidata consente di preparare una posizione sicura di Archiviazione di Azure fornita da Microsoft in cui caricare i file.  Al termine della preparazione, il pulsante **Successivo: Carica file** diventa attivo.

   ![Importazione non Microsoft 365: preparare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Fare clic su **Successivo: Carica file**.

6. Nella pagina **Upload file** eseguire le operazioni seguenti:

   ![Importazione non Microsoft 365: Upload file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Nella casella **Percorso dei** file verificare o digitare il percorso della cartella radice in cui sono archiviati i dati non Microsoft 365 che si desidera caricare. Ad esempio, per il percorso dei file di esempio visualizzati nella sezione Prima di **iniziare,** digitare **%USERPROFILE\Downloads\nonO365**. Se si specifica la posizione corretta, il comando AzCopy visualizzato nella casella sotto il percorso verrà aggiornato correttamente.

   b. Fare **clic su** Copia negli Appunti per copiare il comando visualizzato nella casella.

7. Avviare un Windows prompt dei comandi, incollare il comando copiato nel passaggio precedente e quindi premere **INVIO** per avviare il comando AzCopy.  Dopo aver avviato il comando, i file non Microsoft 365 verranno caricati nel percorso Archiviazione di Azure preparato nel passaggio 4.

   ![Importazione non Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Come indicato in precedenza, è necessario utilizzare AzCopy v8.1 per utilizzare correttamente il comando fornito nella pagina Upload **file.** Se il comando AzCopy fornito non riesce, vedere [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Tornare al Centro sicurezza & conformità e fare clic su **Avanti: Elaborare i file** nella procedura guidata.  In questo modo inizia l'elaborazione, l'estrazione di testo e l'indicizzazione dei file non di Microsoft 365 caricati nella posizione di Archiviazione di Azure.  

9. Tenere traccia dello stato di  avanzamento dell'elaborazione  dei file nella pagina Elabora file o nella scheda Processi visualizzando un processo denominato Aggiunta di dati non Microsoft 365 a un **set di revisione**.  Al termine del processo, i nuovi file saranno disponibili nel set di revisione.

   ![Importazione non Microsoft 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Al termine dell'elaborazione, è possibile chiudere la procedura guidata.