---
title: Gestire l'individuazione degli argomenti in Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come amministrare l'individuazione degli argomenti in Microsoft Viva Topics.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768975"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Gestire l'individuazione degli argomenti in Microsoft Viva Topics

È possibile gestire le impostazioni di individuazione degli argomenti [nell'Microsoft 365 di amministrazione.](https://admin.microsoft.com) Per eseguire queste attività, è SharePoint amministratore globale o amministratore globale.

## <a name="to-access-topics-management-settings"></a>Per accedere alle impostazioni di gestione degli argomenti:

1. Nell'Microsoft 365 di amministrazione fare clic su **Impostazioni** e quindi **su Impostazioni organizzazione.**
2. Nella scheda **Servizi** fare clic su **Esperienze argomento.**

    ![Connessione persone alla conoscenza](../media/admin-org-knowledge-options-completed.png) 

3. Selezionare la **scheda Individuazione** argomenti. Per informazioni su ogni impostazione, vedere le sezioni seguenti.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selezionare SharePoint'argomento

È possibile modificare i siti SharePoint dell'organizzazione che verranno sottoposti a ricerca per indicizzazione per gli argomenti.

Se si desidera includere o escludere un elenco specifico di siti, è possibile utilizzare il modello di .csv seguente:

``` csv
Site name,URL
```

Se si aggiungono siti con Selezione sito, questi vengono aggiunti all’elenco di siti esistenti da includere o escludere. Se si carica un file .csv, viene sovrascritto qualsiasi elenco esistente. Se in precedenza sono stati inclusi o esclusi siti specifici, è possibile scaricare l'elenco come file .csv, apportare modifiche e caricare il nuovo elenco.

Per scegliere i siti per l'individuazione degli argomenti

1. Nella scheda **Individuazione argomenti**, in **Selezionare origini argomenti di SharePoint**, selezionare **Modifica**.
2. Nella pagina **Seleziona SharePoint di** argomenti selezionare quali siti SharePoint verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Tra questi vi sono anche:
    - **Tutti i siti**: tutti SharePoint siti nel tenant. In questo modo vengono catturati i siti correnti e futuri.
    - **Tutti, ad eccezione dei siti** selezionati: digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera rifiutare esplicitamente dall'individuazione. I siti creati in futuro verranno inclusi come origini per l’individuazione di argomenti. 
    - **Solo siti selezionati:** digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l’individuazione di argomenti.
    - **Nessun sito:** gli argomenti non verranno generati o aggiornati automaticamente con SharePoint contenuto. Gli argomenti esistenti rimangono nel Centro argomenti.

    ![Screenshot dell'interfaccia SharePoint'interfaccia utente delle origini degli argomenti](../media/k-manage-select-topic-source.png)
   
3. Fare clic su **Salva**.

## <a name="exclude-topics-by-name"></a>Escludere gli argomenti per nome

È possibile escludere gli argomenti dall’individuazione caricando un elenco usando un file .csv. Se in precedenza sono stati esclusi alcuni argomenti, è possibile scaricare il file .csv, apportare modifiche e caricarlo di nuovo.

1. Nella scheda **Individuazione argomenti**, in **Escludi**, selezionare **Modifica**.
2. Fare **clic su Escludi argomenti per nome.**
3. Se è necessario creare un elenco, scaricare il modello di .csv e aggiungere gli argomenti che si desidera escludere (vedere Utilizzo del modello di .csv *seguente).* Quando il file è pronto, fare clic **su Sfoglia** e caricare il file. Se è presente un elenco esistente, è possibile scaricare il .csv contenente l'elenco.
4. Fare clic su **Salva**.

    ![Screenshot dell'interfaccia utente degli argomenti di esclusione](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Utilizzo del modello .csv

È possibile copiare il modello csv seguente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Nel modello CSV immettere le informazioni seguenti sugli argomenti da escludere:

- **Nome**: digitare il nome dell’argomento da escludere. È possibile eseguire questa operazione in due modi:
    - Corrispondenza esatta: è possibile escludere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*
    - Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.  Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.
- **Sta per (facoltativo):** se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.
- **MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Vedere anche

[Gestire la visibilità degli argomenti in Microsoft 365](topic-experiences-knowledge-rules.md)

[Gestire le autorizzazioni per gli argomenti in Microsoft 365](topic-experiences-user-permissions.md)

[Modificare il nome del centro argomenti in Microsoft 365](topic-experiences-administration.md)
