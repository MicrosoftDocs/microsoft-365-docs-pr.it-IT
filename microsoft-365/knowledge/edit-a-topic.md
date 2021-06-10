---
title: 'Modificare un argomento esistente in Microsoft Viva Topics '
description: Come modificare un argomento esistente in Microsoft Viva Topics.
author: efrene
ms.author: efrene
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
ms.openlocfilehash: 23c870826261a85aee23af82bb177825f55f4eb2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165394"
---
# <a name="edit-an-existing-topic-in-microsoft-viva-topics"></a>Modificare un argomento esistente in Microsoft Viva Topics 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LA4n]  

</br>

In Viva Topics è possibile modificare un argomento esistente. Potrebbe essere necessario eseguire questa operazione se si desidera correggere o aggiungere ulteriori informazioni a una pagina di argomento esistente. 

> [!Note] 
> Mentre le informazioni in un argomento raccolto dall'IA sono limitate per motivi di [sicurezza,](topic-experiences-security-trimming.md)tenere presente che la descrizione dell'argomento e le informazioni sulle persone che vengono aggiunti manualmente durante la modifica di un argomento esistente sono visibili a tutti gli utenti che dispongono delle autorizzazioni per visualizzare gli argomenti. 

## <a name="requirements"></a>Requisiti

Per modificare un argomento esistente, è necessario:
- Avere una licenza di Viva Topics.
- Disporre delle autorizzazioni per [**Who creare o modificare argomenti.**](./topic-experiences-user-permissions.md) Gli amministratori delle informazioni possono assegnare questa autorizzazione nelle impostazioni delle autorizzazioni per gli argomenti di Viva Topics. 

> [!Note] 
> Gli utenti che dispongono dell'autorizzazione per gestire gli argomenti nel Centro argomenti (responsabili della conoscenza) dispongono già delle autorizzazioni per creare e modificare gli argomenti.

## <a name="how-to-edit-a-topic-page"></a>Come modificare una pagina di argomento

Gli utenti che dispongono dell'autorizzazione **Who** creare o modificare argomenti possono modificare un argomento aprendo <b></b> la pagina dell'argomento da un'evidenziazione dell'argomento e quindi selezionando il pulsante Modifica in alto a destra nella pagina dell'argomento. La pagina dell'argomento può essere aperta anche dalla home page del Centro argomenti in cui è possibile trovare tutti gli argomenti a cui si dispone di una connessione.

   ![Pulsante Modifica](../media/knowledge-management/edit-button.png) </br> 

I knowledge manager possono inoltre modificare gli argomenti direttamente dalla pagina Gestisci argomenti selezionando l'argomento e quindi selezionando <b>Modifica</b> sulla barra degli strumenti.

   ![Modifica argomento in Gestisci argomenti](../media/knowledge-management/manage-topics-edit.png) </br> 

### <a name="to-edit-a-topic-page"></a>Per modificare una pagina dell'argomento

1. Nella pagina dell'argomento selezionare **Modifica.** In questo modo è possibile apportare le modifiche necessarie alla pagina dell'argomento.

   ![Controllo di modifica](../media/knowledge-management/topic-page-edit.png) </br>  


2. Nella sezione <b>Nomi alternativi</b> digitare altri nomi a cui l'argomento potrebbe fare riferimento. 

    ![Nomi alternativi](../media/knowledge-management/alt-names.png) </br> 
3. Nella sezione <b>Descrizione</b> digitare qualche frase per descrivere l'argomento. Se esiste già una descrizione, aggiornarla se necessario.

    ![Sezione Descrizione](../media/knowledge-management/description.png)</br>

4. Nella sezione <b>Persone aggiunte</b> è possibile "aggiungere" una persona per mostrarle che ha una connessione con l'argomento (ad esempio, un proprietario di una risorsa connessa). Iniziare digitandone il nome o l'indirizzo di posta elettronica nella casella <b>Aggiungi</b> un nuovo utente e quindi selezionando l'utente che si desidera aggiungere dai risultati della ricerca. Puoi anche "sbloccarli" selezionando l'icona Rimuovi <b>dall'elenco</b> nella scheda utente.
 
    ![Aggiungere persone aggiunte](../media/knowledge-management/pinned-people.png)</br>

    La sezione <b>Persone suggerite</b> mostra gli utenti che secondo l'intelligenza artificiale potrebbero essere collegati all'argomento dalla loro connessione alle risorse sull'argomento. È possibile modificare il loro stato da Suggeriti a Aggiunti selezionando l'icona aggiungi sulla scheda utente.

   ![Aggiungere un utente consigliato](../media/knowledge-management/suggested-people.png)</br>

5. Nella sezione <b>File e pagine aggiunti</b> è possibile aggiungere un file o una pagina del sito di SharePoint associata all'argomento.

   ![Sezione File e pagine aggiunti](../media/knowledge-management/pinned-files-and-pages.png)</br>
 
    Per aggiungere un nuovo file, selezionare <b>Aggiungi,</b>selezionare il sito SharePoint dai siti frequenti o seguiti e quindi selezionare il file dalla raccolta documenti del sito.

    È anche possibile usare l'opzione <b>Da un collegamento</b> per aggiungere un file o una pagina fornendo l'URL. 

   > [!Note] 
   > I file e le pagine aggiunti devono trovarsi nello stesso tenant Microsoft 365 tenant. Se vuoi aggiungere un collegamento a una risorsa esterna nell'argomento, puoi aggiungerlo tramite l'icona canvas nel passaggio 9.

6. La <b>sezione File e pagine suggeriti</b> mostra i file e le pagine che l'intelligenza artificiale suggerisce di associare all'argomento.

   ![Sezione File e pagine suggeriti](../media/knowledge-management/suggested-files-and-pages.png)</br>

    È possibile sostituire una pagina o un file suggerito con un file o una pagina bloccata selezionando l'icona aggiungi.

7.  La sezione <b>Siti correlati</b> mostra i siti con informazioni sull'argomento. 

    ![Sezione Siti correlati](../media/knowledge-management/related-sites.png)</br>

    È possibile aggiungere un sito correlato <b>selezionando</b> Aggiungi e quindi cercando il sito o selezionandolo nell'elenco dei siti frequenti o recenti.</br>
    
    ![Selezionare un sito](../media/knowledge-management/sites.png)</br>

8. La <b>sezione Argomenti correlati</b> mostra le connessioni esistenti tra gli argomenti. È possibile aggiungere una connessione a un argomento diverso selezionando il <b>pulsante Connessione a</b> un argomento correlato, quindi digitando il nome dell'argomento correlato e selezionandolo dai risultati della ricerca. 

   ![Sezione Argomenti correlati](../media/knowledge-management/related-topic.png)</br>  

    È quindi possibile fornire una descrizione del modo in cui gli argomenti sono correlati e selezionare <b>Aggiorna</b>.</br>

   ![Descrizione degli argomenti correlati](../media/knowledge-management/related-topics-update.png)</br> 

   L'argomento correlato aggiunto verrà visualizzato come argomento connesso.

   ![Argomenti correlati connessi](../media/knowledge-management/related-topics-final.png)</br> 

   Per rimuovere un argomento correlato, selezionare l'argomento che si desidera rimuovere, quindi selezionare <b>l'icona Rimuovi argomento.</b></br>
 
   ![Rimuovere l'argomento correlato](../media/knowledge-management/remove-related.png)</br>  

   Selezionare quindi <b>Rimuovi</b>.</br>

   ![Conferma rimozione](../media/knowledge-management/remove-related-confirm.png)</br> 


9. È anche possibile aggiungere elementi statici alla pagina, ad esempio testo, immagini o collegamenti, selezionando l'icona dell'area di disegno, disponibile sotto la breve descrizione. Selezionandolo si aprirà SharePoint casella degli strumenti da cui è possibile scegliere l'elemento che si desidera aggiungere alla pagina.

   ![Icona Canvas](../media/knowledge-management/webpart-library.png)</br> 


10. Selezionare **Pubblica** o **Ripubblica** per salvare le modifiche. **La** ripubblicazione sarà l'opzione disponibile se l'argomento è stato pubblicato in precedenza.


## <a name="see-also"></a>Vedere anche



