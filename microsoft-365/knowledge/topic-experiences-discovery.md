---
title: Gestire l'individuazione degli argomenti in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come amministrare l'individuazione degli argomenti in Microsoft 365.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698544"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a>Gestire l'individuazione degli argomenti in Microsoft 365

È possibile gestire le impostazioni di individuazione degli argomenti nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com). Per eseguire queste attività, è necessario essere un amministratore globale o un amministratore di SharePoint.

## <a name="to-access-topics-management-settings"></a>Per accedere alle impostazioni di gestione degli argomenti:

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic su **Impostazioni** e quindi su **Impostazioni org**.
2. Nella scheda **Servizi** , fare clic su **Knowledge Network**.

    ![Connettere le persone alla conoscenza](../media/admin-org-knowledge-options-completed.png) 

3. Selezionare la scheda **individuazione degli argomenti** . Per informazioni su ogni impostazione, vedere le sezioni seguenti.

    ![Knowledge-Network-Settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selezionare origini degli argomenti di SharePoint

È possibile modificare i siti di SharePoint nell'organizzazione che verranno sottoposti a ricerca per indicizzazione per gli argomenti.

Se si desidera includere o escludere un elenco specifico di siti, è possibile utilizzare il modello CSV seguente:

``` csv
Site name,URL
```

Se si aggiungono siti utilizzando lo strumento di selezione siti, questi vengono aggiunti all'elenco esistente di siti da includere o escludere. Se si carica un file. csv, sovrascrive qualsiasi elenco esistente. Se in precedenza sono stati inclusi o esclusi siti specifici, è possibile scaricare l'elenco come file. csv, apportare modifiche e caricare il nuovo elenco.

Per scegliere i siti per l'individuazione degli argomenti

1. Nella scheda **individuazione argomento** , in **selezionare origini argomento di SharePoint**, selezionare **modifica**.
2. Nella pagina **Seleziona origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Questo include:
    - **Tutti i siti**: tutti i siti di SharePoint nel tenant. Questo acquisisce i siti correnti e futuri.
    - **All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. 
    - **Solo siti selezionati**: digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.
    - **Nessun sito**: gli argomenti non verranno generati o aggiornati automaticamente con il contenuto di SharePoint. Gli argomenti esistenti rimangono nell'argomento centro.

    ![Schermata dell'interfaccia utente di origini degli argomenti di SharePoint](../media/k-manage-select-topic-source.png)
   
3. Fare clic su **Salva**.

## <a name="exclude-topics-by-name"></a>Escludi argomenti per nome

È possibile escludere gli argomenti dall'individuazione caricando un elenco utilizzando un file. csv. Se sono stati precedentemente esclusi gli argomenti, è possibile scaricare il file. csv, apportare modifiche e caricarlo di nuovo.

1. Nella scheda **individuazione argomento** , in **argomenti Escludi**, selezionare **modifica**.
2. Fare clic su **Escludi argomenti per nome**.
3. Se è necessario creare un elenco, scaricare il modello. csv e aggiungere gli argomenti che si desidera escludere (vedere *utilizzo del modello. CSV di* seguito). Quando il file è pronto, fare clic su **Sfoglia** e caricare il file. Se è presente un elenco esistente, è possibile scaricare il file con estensione CSV contenente l'elenco.
4. Fare clic su **Salva**.

    ![Schermata dell'interfaccia utente argomenti di esclusione](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Utilizzo del modello. csv

È possibile copiare il modello CSV seguente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Nel modello CSV, immettere le informazioni seguenti sugli argomenti che si desidera escludere:

- **Nome**: digitare il nome dell'argomento che si desidera escludere. Questa operazione può essere eseguita in due modi:
    - Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL*).
    - Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.  Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco*, *saldatura ad arco al plasma* o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.
- Acronimo **di (facoltativo)**: se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.
- **MatchType-exact/partial**: digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .

    ![Escludi argomenti nel modello CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Vedere anche

[Gestire la visibilità degli argomenti in Microsoft 365](topic-experiences-knowledge-rules.md)

[Gestire le autorizzazioni per l'argomento in Microsoft 365](topic-experiences-user-permissions.md)

[Modificare il nome del centro argomenti in Microsoft 365](topic-experiences-administration.md)
