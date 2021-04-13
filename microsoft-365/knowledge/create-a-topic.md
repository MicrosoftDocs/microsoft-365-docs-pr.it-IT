---
title: Creare un nuovo argomento in Microsoft Viva Topics
description: Come creare un nuovo argomento in Microsoft Viva Topics.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687532"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a>Creare un nuovo argomento in Microsoft Viva Topics

In Viva Topics puoi creare un nuovo argomento se non ne viene individuato uno tramite l'indicizzazione o se la tecnologia IA non ha trovato prove sufficienti per stabilirlo come argomento.

> [!Note] 
> Mentre le informazioni in un argomento raccolto dall'IA sono limitate per motivi di [sicurezza,](topic-experiences-security-trimming.md)tenere presente che la descrizione dell'argomento e le informazioni sulle persone in un argomento creato manualmente sono visibili a tutti gli utenti che dispongono delle autorizzazioni per visualizzare l'argomento. 


## <a name="requirements"></a>Requisiti

Per creare un nuovo argomento, è necessario:
- Avere una licenza Viva Topics.
- Disporre delle autorizzazioni [**per gli utenti che possono creare o modificare argomenti.**](./topic-experiences-user-permissions.md) Gli amministratori della knowledge base possono concedere agli utenti questa autorizzazione nelle impostazioni delle autorizzazioni dell'argomento Viva Topics. 

> [!Note] 
> Gli utenti che dispongono dell'autorizzazione per gestire gli argomenti nel Centro argomenti (responsabili della knowledge base) dispongono già delle autorizzazioni per creare e modificare gli argomenti.

## <a name="to-create-a-topic"></a>Per creare un argomento

È possibile creare un nuovo argomento da due posizioni:

- Home page del Centro argomenti:  qualsiasi utente con licenza con autorizzazione Chi può creare o modificare argomenti (collaboratori) può creare un nuovo argomento dal Centro argomenti selezionando il **menu** Nuovo e selezionando **Pagina Argomento.** 

    ![Nuovo argomento dal Centro argomenti](../media/knowledge-management/new-topic.png)  

- Pagina Gestisci argomenti: qualsiasi  utente con licenza che dispone dell'autorizzazione Chi può gestire gli argomenti (responsabili della knowledge base) può creare un nuovo argomento dalla pagina Gestisci argomenti nel Centro argomenti selezionando Pagina Nuovo **argomento.** 

    ![Nuovo argomento da gestire gli argomenti](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a>Per creare un nuovo argomento:

1. Selezionare l'opzione per creare una nuova pagina argomento dalla barra multifunzione nella pagina Gestisci argomenti.

2.  Nella sezione **Assegnare un nome all'argomento** digitare il nome del nuovo argomento.

    ![Assegnare un nome a questo argomento](../media/knowledge-management/k-new-topic-page.png)  

3. Nella sezione **Nomi alternativi** digitare eventuali altri nomi a cui potrebbe fare riferimento l'argomento. 

    ![Nomi alternativi](../media/knowledge-management/alt-names.png)  

4. Nella sezione **Descrizione** digitare un paio di frasi che descrivono l'argomento. 

    ![Descrizione dell'argomento](../media/knowledge-management/description.png)

4. Nella sezione **Persone** aggiunte puoi "aggiungere" una persona per mostrargli di avere una connessione all'argomento (ad esempio, un proprietario di una risorsa connessa). Iniziare digitando il nome o  l'indirizzo di posta elettronica nella casella Aggiungi un nuovo utente e quindi selezionare l'utente che si desidera aggiungere dai risultati della ricerca. Puoi anche "sbloccarli" selezionando l'icona Rimuovi **dall'elenco** nella scheda utente. Puoi anche trascinare la persona in un'altra posizione dell'elenco.
 
    ![Persone aggiunte](../media/knowledge-management/pinned-people.png)

5. Nella sezione **File e** pagine aggiunti è possibile aggiungere o aggiungere un file o una pagina del sito di SharePoint associata all'argomento.

   ![File e pagine aggiunti](../media/knowledge-management/pinned-files-and-pages.png)
 
    Per aggiungere un nuovo file, **selezionare** Aggiungi , selezionare il sito di SharePoint dai siti frequenti o seguiti e quindi selezionare il file dalla raccolta documenti del sito.

    Puoi anche usare **l'opzione Da un collegamento** per aggiungere un file o una pagina specificando l'URL. 

    > [!Note] 
    > I file e le pagine aggiunti devono trovarsi nello stesso tenant di Microsoft 365. Se vuoi aggiungere un collegamento a una risorsa esterna nell'argomento, puoi aggiungerlo tramite l'icona canvas nel passaggio 8.


6.  La **sezione Siti correlati** mostra i siti che dispongono di informazioni sull'argomento. 

    ![Sezione Siti correlati](../media/knowledge-management/related-sites.png)

    È possibile aggiungere un sito correlato **selezionando** Aggiungi e quindi cercando il sito o selezionandolo nell'elenco dei siti frequenti o recenti.
    
    ![Seleziona sito](../media/knowledge-management/sites.png)

7. La **sezione Argomenti correlati** mostra le connessioni esistenti tra gli argomenti. È possibile aggiungere una connessione a un argomento diverso selezionando il pulsante Connetti **a** un argomento correlato, quindi digitando il nome dell'argomento correlato e selezionandolo dai risultati della ricerca. 

   ![Argomenti correlati](../media/knowledge-management/related-topic.png)  

    È quindi possibile fornire una descrizione del modo in cui gli argomenti sono correlati e selezionare **Aggiorna**.

   ![Descrizione degli argomenti correlati](../media/knowledge-management/related-topics-update.png) 

   L'argomento correlato aggiunto verrà visualizzato come argomento connesso.

   ![Argomenti correlati connessi](../media/knowledge-management/related-topics-final.png) 

   Per rimuovere un argomento correlato, selezionare l'argomento che si desidera rimuovere, quindi selezionare **l'icona Rimuovi argomento.**
 
   ![Rimuovere l'argomento correlato](../media/knowledge-management/remove-related.png)  

   Selezionare quindi **Rimuovi**.

   ![Conferma rimozione](../media/knowledge-management/remove-related-confirm.png) 

8. Puoi anche aggiungere elementi statici alla pagina (ad esempio testo, immagini o collegamenti) selezionando l'icona dell'area di disegno, che puoi trovare sotto la breve descrizione. Selezionandolo verrà aperta la casella degli strumenti di SharePoint da cui è possibile scegliere l'elemento che si desidera aggiungere alla pagina.

   ![Icona Canvas](../media/knowledge-management/webpart-library.png) 

9. Selezionare **Pubblica** per salvare le modifiche. 

Dopo aver pubblicato la pagina, il nome dell'argomento, il nome alternativo, la descrizione e gli utenti aggiunti verranno visualizzati per tutti gli utenti con licenza che visualizzano l'argomento. File, pagine e siti specifici verranno visualizzati nella pagina dell'argomento solo se il visualizzatore dispone delle autorizzazioni di Office 365 per l'elemento. 



## <a name="see-also"></a>Vedere anche



