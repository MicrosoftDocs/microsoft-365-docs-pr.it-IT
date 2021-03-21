---
title: Configurare Gli argomenti di Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come configurare Microsoft Viva Topics
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929445"
---
# <a name="set-up-microsoft-viva-topics"></a>Configurare Gli argomenti di Microsoft Viva

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare [Gli argomenti](topic-experiences-overview.md). 

È importante pianificare il modo migliore per configurare e configurare gli argomenti nell'ambiente. Leggere Plan [for Microsoft Viva Topics](plan-topic-experiences.md) prima di iniziare le procedure descritte in questo articolo.

È necessario essere [abbonati a Viva Topics](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.

Se SharePoint è stato configurato per [richiedere dispositivi gestiti,](/sharepoint/control-access-from-unmanaged-devices)assicurarsi di configurare Gli argomenti da un dispositivo gestito.

## <a name="video-demonstration"></a>Dimostrazione video

Questo video mostra il processo di configurazione degli argomenti in Microsoft 365.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a>Configurare Argomenti

Per configurare gli argomenti

1. Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)selezionare **Installazione** e quindi visualizzare la **sezione File e** contenuto.
2. Nella sezione **File e contenuto** fare clic su Connetti persone alla **conoscenza.**

    ![Connettere le persone alla conoscenza](../media/admin-org-knowledge-options.png) 

3. Nella pagina **Connetti persone alla knowledge** base fare clic su **Introduzione** per iniziare a eseguire il processo di installazione.

    ![Per iniziare](../media/k-get-started.png) 

4. Nella pagina **Scegliere in che modo Viva Topics può trovare gli** argomenti, si configurerà l'individuazione degli argomenti. Nella sezione **Selezione origini argomenti di SharePoint** selezionare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Scegli tra:
    - **Tutti i siti**: tutti i siti di SharePoint nell'organizzazione. Sono inclusi i siti correnti e futuri.
    - **Tutti, ad eccezione dei siti** selezionati: digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera rifiutare esplicitamente dall'individuazione. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. 
    - **Solo siti selezionati:** digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.
    - **Nessun sito:** non includere alcun sito di SharePoint.

    ![Scegliere come trovare gli argomenti](../media/ksetup1.png) 
   
5. Nella sezione **Escludi argomenti per nome** è possibile aggiungere i nomi degli argomenti che si desidera escludere dall'individuazione degli argomenti. Utilizzare questa impostazione per impedire che le informazioni riservate vengano incluse come argomenti. Le opzioni sono:
    - **Non escludere argomenti** 
    - **Escludere gli argomenti in base al nome**

    ![Escludi argomenti](../media/topics-excluded-by-name.png) 

    I responsabili della conoscenza possono anche escludere gli argomenti nel Centro argomenti dopo l'individuazione.

    #### <a name="how-to-exclude-topics-by-name"></a>Come escludere gli argomenti in base al nome    

    Se è necessario escludere gli argomenti, dopo aver selezionato Escludi argomenti per **nome,** scaricare il modello CSV e aggiornarlo con l'elenco di argomenti che si desidera escludere dai risultati dell'individuazione.

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

    Nel modello CSV immettere le informazioni seguenti sugli argomenti che si desidera escludere:

    - **Nome**: digitare il nome dell'argomento che si desidera escludere. Questa operazione può essere eseguita in due modi:
        - Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*
        - Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.  Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.
    - **Sta per (facoltativo):** se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.
    - **MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.

    Dopo aver completato e salvato il file CSV, selezionare **Sfoglia** per individuarlo e selezionarlo.
    
    Selezionare **Avanti**.

6. Nella pagina Chi può visualizzare gli argomenti e dove può **vederli,** configurerai la visibilità degli argomenti. **Nell'impostazione Chi** può visualizzare gli argomenti scegliere chi avrà accesso ai dettagli dell'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nella ricerca e pagine degli argomenti. È possibile selezionare:
    - **Tutti gli utenti dell'organizzazione**
    - **Solo utenti o gruppi di sicurezza selezionati**
    - **Nessuno**

    ![Chi può visualizzare gli argomenti](../media/ksetup2.png)  

    > [!Note] 
    > Anche se questa impostazione consente di selezionare qualsiasi utente nell'organizzazione, solo gli utenti a cui sono assegnate licenze esperienze argomento potranno visualizzare gli argomenti.

7. Nella pagina **Autorizzazioni per la gestione degli** argomenti scegliere chi sarà in grado di creare, modificare o gestire gli argomenti. Nella sezione **Utenti che possono creare e modificare argomenti** è possibile selezionare:
    - **Tutti gli utenti dell'organizzazione**
    - **Solo utenti o gruppi di sicurezza selezionati**
    - **Nessuno**

    ![Autorizzazioni per la gestione degli argomenti, che possono creare e modificare argomenti](../media/ksetup3.png) 

8. Nella sezione **Chi può gestire gli argomenti** è possibile selezionare:
    - **Tutti gli utenti dell'organizzazione**
    - **Solo utenti o gruppi di sicurezza selezionati**

    ![Autorizzazioni per la gestione degli argomenti](../media/km-setup-create-edit-topics.png) 

    Selezionare **Avanti**.

9. Nella pagina **Crea centro argomenti** è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire gli argomenti. Nella casella **Nome sito** digitare un nome per il Centro argomenti. Facoltativamente, è possibile digitare una breve descrizione nella **casella Descrizione.** 

   Selezionare **Avanti**.

   ![Creare il Centro informazioni](../media/ksetup4.png)  

10. Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche. Al termine, selezionare **Attiva**.

11. Verrà visualizzata la pagina **Viva Topics activated,** che conferma che il sistema inizierà ad analizzare i siti selezionati per gli argomenti e a creare il sito Centro argomenti. Scegliere **Fatto**.

12. Verrà visualizzata la pagina Connetti **persone alla** conoscenza. In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione. 

    ![Impostazioni applicate](../media/ksetup7.png)    

Si noti che la prima volta che l'individuazione degli argomenti è abilitata, potrebbero essere necessario fino a due settimane prima che tutti gli argomenti suggeriti vengano visualizzati nella visualizzazione Gestisci argomenti. L'individuazione degli argomenti continua quando vengono apportati nuovi contenuti o aggiornamenti al contenuto. È normale avere fluttuazioni nel numero di argomenti suggeriti nell'organizzazione poiché Viva Topics valuta nuove informazioni.

## <a name="assign-licenses"></a>Assegna le licenze

Dopo aver configurato le esperienze di argomento, è necessario assegnare le licenze per gli utenti che si baseranno su Argomenti. Solo gli utenti con una licenza possono visualizzare informazioni su argomenti quali evidenziazioni, schede argomento, pagine di argomenti e il Centro argomenti. 

Per assegnare le licenze:

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.

2. Seleziona gli utenti di cui vuoi ottenere la licenza e fai clic **su Licenze e app.**

3. In **Licenze** selezionare **Viva Topics.**

4. In **App** assicurati che sia selezionata l'opzione Cerca connettori grafico con indice **(Argomenti Viva)** **e Viva Argomenti.**

   > [!div class="mx-imgBorder"]
   > ![Licenze di Microsoft Viva Topics nell'interfaccia di amministrazione di Microsoft 365](../media/topic-experiences-licenses.png)

5. Fare clic su **Salva modifiche**.

## <a name="manage-topic-experiences"></a>Gestire le esperienze degli argomenti

Dopo aver configurato Gli argomenti, è possibile modificare le impostazioni scelte durante l'installazione nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement) Vedere i seguenti riferimenti:

- [Gestire l'individuazione degli argomenti in Microsoft Viva Topics](topic-experiences-discovery.md)
- [Gestire la visibilità degli argomenti in Microsoft Viva Topics](topic-experiences-knowledge-rules.md)
- [Gestire le autorizzazioni per gli argomenti in Microsoft Viva Topics](topic-experiences-user-permissions.md)
- [Modificare il nome del Centro argomenti in Microsoft Viva Topics](topic-experiences-administration.md)

## <a name="see-also"></a>Vedere anche

[Panoramica delle esperienze degli argomenti](topic-experiences-overview.md)
