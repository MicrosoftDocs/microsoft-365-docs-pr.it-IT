---
title: Modificare un argomento esistente in Microsoft Viva Topics
author: chuckedmonson
ms.author: chucked
manager: pamgreen
audience: admin
ms.reviewer: cjtan
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
localization_priority: Normal
description: Informazioni su come modificare un argomento esistente in Microsoft Viva Topics.
ms.openlocfilehash: 6e1f85737298736a3aafcb30cfe103c28654d1c1
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053202"
---
# <a name="edit-an-existing-topic-in-microsoft-viva-topics"></a>Modificare un argomento esistente in Microsoft Viva Topics 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LA4n]  

</br>

In Viva Topics è possibile modificare un argomento esistente. Potrebbe essere necessario eseguire questa operazione se si desidera correggere o aggiungere ulteriori informazioni a una pagina di argomento esistente. 

> [!Note] 
> Mentre le informazioni in un argomento raccolto dall'IA sono limitate per motivi di [sicurezza,](topic-experiences-security-trimming.md)la descrizione dell'argomento e le informazioni sulle persone che vengono aggiunti manualmente durante la modifica di un argomento esistente sono visibili a tutti gli utenti che dispongono delle autorizzazioni per visualizzare gli argomenti. 

## <a name="requirements"></a>Requisiti

Per modificare un argomento esistente, è necessario:
- Avere una licenza di Viva Topics.
- Disporre delle autorizzazioni [per creare o modificare argomenti.](./topic-experiences-user-permissions.md) Gli amministratori delle informazioni possono assegnare questa autorizzazione nelle impostazioni delle autorizzazioni per gli argomenti di Viva Topics. 

> [!Note] 
> Gli utenti che dispongono dell'autorizzazione per gestire gli argomenti nel Centro argomenti (responsabili della knowledge base) dispongono già delle autorizzazioni per creare e modificare gli argomenti.

## <a name="how-to-edit-a-topic-page"></a>Come modificare una pagina di argomento

Gli utenti che dispongono dell'autorizzazione *Who* creare o modificare argomenti possono modificare un argomento aprendo  la pagina dell'argomento da un'evidenziazione dell'argomento e quindi selezionando il pulsante Modifica in alto a destra nella pagina dell'argomento. La pagina dell'argomento può essere aperta anche dalla home page del Centro argomenti in cui è possibile trovare tutti gli argomenti a cui si dispone di una connessione.

   ![Screenshot che mostra il pulsante Modifica.](../media/knowledge-management/edit-button.png) </br> 

I knowledge manager possono inoltre modificare gli argomenti direttamente dalla pagina **Gestisci** argomenti selezionando l'argomento e quindi selezionando **Modifica** sulla barra degli strumenti.

   ![Screenshot che mostra l'argomento Modifica nella pagina Gestisci argomenti.](../media/knowledge-management/manage-topics-edit.png)

### <a name="to-edit-a-topic-page"></a>Per modificare una pagina dell'argomento

1. Nella pagina dell'argomento selezionare **Modifica.** In questo modo è possibile apportare le modifiche necessarie alla pagina dell'argomento.

   ![Screenshot che mostra il pulsante Modifica nella pagina dell'argomento.](../media/knowledge-management/topic-page-edit.png)  


2. Nella sezione **Nomi alternativi** digitare eventuali altri nomi a cui potrebbe fare riferimento l'argomento. 

    ![Screenshot che mostra la sezione Nomi alternativi.](../media/knowledge-management/alt-names.png)

3. Nella sezione **Descrizione** digitare qualche frase per descrivere l'argomento. Se esiste già una descrizione, aggiornarla se necessario.

    ![Screenshot che mostra la sezione Description.](../media/knowledge-management/description.png)</br>

4. Nella sezione **Persone aggiunte** è possibile "aggiungere" una persona per mostrarle che ha una connessione con l'argomento (ad esempio, un proprietario di una risorsa connessa). Iniziare digitandone il nome o l'indirizzo di posta elettronica nella casella **Aggiungi** un nuovo utente e quindi selezionando l'utente che si desidera aggiungere dai risultati della ricerca. Puoi anche "sbloccarli" selezionando l'icona Rimuovi **dall'elenco** nella scheda utente.
 
    ![Screenshot che mostra la sezione Aggiungi persone aggiunte.](../media/knowledge-management/pinned-people.png)</br>

    La sezione **Persone suggerite** mostra gli utenti che secondo l'intelligenza artificiale potrebbero essere collegati all'argomento dalla loro connessione alle risorse sull'argomento. È possibile modificare il loro stato da Suggeriti a Aggiunti selezionando l'icona aggiungi sulla scheda utente.

   ![Screenshot che mostra l'aggiunta di persone suggerite.](../media/knowledge-management/suggested-people.png)

5. Nella sezione **File e pagine aggiunti** è possibile aggiungere un file o una pagina del sito di SharePoint associata all'argomento.

   ![Screenshot che mostra la sezione File e pagine aggiunti.](../media/knowledge-management/pinned-files-and-pages.png)
 
    Per aggiungere un nuovo file, selezionare **Aggiungi,** selezionare il sito SharePoint dai siti frequenti o seguiti e quindi selezionare il file dalla raccolta documenti del sito.

    È anche possibile usare l'opzione **Da un collegamento** per aggiungere un file o una pagina fornendo l'URL. 

   > [!Note] 
   > I file e le pagine aggiunti devono trovarsi nello stesso tenant Microsoft 365 tenant. Se vuoi aggiungere un collegamento a una risorsa esterna nell'argomento, puoi aggiungerlo tramite l'icona canvas nel passaggio 9.

6. La **sezione File e pagine suggeriti** mostra i file e le pagine che l'intelligenza artificiale suggerisce di associare all'argomento.

   ![Screenshot che mostra la sezione File e pagine suggeriti.](../media/knowledge-management/suggested-files-and-pages.png)

    È possibile sostituire una pagina o un file suggerito con un file o una pagina bloccata selezionando l'icona aggiungi.

7.  Nella sezione **Siti aggiunti** è possibile aggiungere o aggiungere un sito associato all'argomento. 

    ![Screenshot che mostra la sezione Siti aggiunti.](../media/knowledge-management/pinned-sites-section.png)

    Per aggiungere un nuovo sito, **selezionare** Aggiungi e quindi cercare il sito oppure selezionarlo dall'elenco dei siti frequenti o recenti.
    
    ![Screenshot che mostra la sezione Aggiungere o rimuovere un sito aggiunto.](../media/knowledge-management/add-or-remove-pinned-sites.png)

8. La **sezione Siti suggeriti** mostra i siti che l'IA suggerisce di associare all'argomento. 

   ![Screenshot della sezione Siti suggeriti](../media/knowledge-management/suggested-sites-section.png)  

    È possibile modificare un sito suggerito in un sito aggiunto selezionando l'icona aggiunta.


<!---

7.  The <b>Related sites</b> section shows sites that have information about the topic. 

    ![Related sites section](../media/knowledge-management/related-sites.png)</br>

    You can add a related site by selecting <b>Add</b> and then either searching for the site, or selecting it from your list of Frequent or Recent sites.</br>
    
    ![Select a site](../media/knowledge-management/sites.png)</br>

8. The <b>Related topics</b> section shows connections that exists between topics. You can add a connection to a different topic by selecting the <b>Connect to a related topic</b> button, and then typing the name of the related topic, and selecting it from the search results. 

   ![Related topics section](../media/knowledge-management/related-topic.png)</br>  

    You can then give a description of how the topics are related, and select <b>Update</b>.</br>

   ![Related topics description](../media/knowledge-management/related-topics-update.png)</br> 

   The related topic you added will display as a connected topic.

   ![Related topics connected](../media/knowledge-management/related-topics-final.png)</br> 

   To remove a related topic, select the topic you want to remove, then select the <b>Remove topic</b> icon.</br>
 
   ![Remove related topic](../media/knowledge-management/remove-related.png)</br>  

   Then select <b>Remove</b>.</br>

   ![Confirm remove](../media/knowledge-management/remove-related-confirm.png)</br> 

--->

9. È anche possibile aggiungere elementi statici alla pagina, ad esempio testo, immagini o collegamenti, selezionando l'icona dell'area di disegno, disponibile sotto la breve descrizione. Selezionandolo si aprirà SharePoint casella degli strumenti da cui è possibile scegliere l'elemento che si desidera aggiungere alla pagina.

   ![Screenshot che mostra l'icona Canvas.](../media/knowledge-management/webpart-library.png)


10. Selezionare **Pubblica** o **Ripubblica** per salvare le modifiche. **La** ripubblicazione sarà l'opzione disponibile se l'argomento è stato pubblicato in precedenza.





