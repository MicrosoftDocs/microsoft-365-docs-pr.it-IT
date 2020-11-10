---
title: 'Configurare la gestione delle informazioni (anteprima) '
description: Come configurare la gestione delle informazioni.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988999"
---
# <a name="set-up-knowledge-management-preview"></a>Configurare la gestione delle informazioni (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Altre informazioni su Project Cortex](https://aka.ms/projectcortex).

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la [gestione delle informazioni](knowledge-management-overview.md). 

> [!Important]
> È importante pianificare il modo migliore per impostare e configurare la gestione della conoscenza nell'ambiente in uso. Ad esempio, è necessario prendere in considerazione quanto segue:
- I siti di SharePoint che si desidera analizzare per gli argomenti.
- Gli utenti a cui si desidera rendere visibili gli argomenti.
- Gli utenti che si desidera concedere le autorizzazioni per la gestione degli argomenti nell'argomento centro.
- Gli utenti che si desidera concedere le autorizzazioni per la creazione o la modifica di argomenti nel centro argomenti.
- Il nome che si desidera assegnare al centro dell'argomento.

> [!Note]
> Potrebbe essere utile creare gruppi di sicurezza per assegnare agli utenti le autorizzazioni necessarie per visualizzare gli argomenti, gestire l'argomento e creare e modificare gli argomenti.

Un amministratore può anche [apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione](topic-experiences-discovery.md) tramite le impostazioni di gestione delle informazioni nell'interfaccia di amministrazione di Microsoft 365.

## <a name="requirements"></a>Requisiti 
È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare le attività relative alla conoscenza organizzativa.

## <a name="set-up-your-knowledge-network"></a>Configurare la rete di conoscenze

Se si configura la rete della Knowledge base, è possibile effettuare le seguenti operazioni:

- Individuazione dell'argomento: selezione di origini e argomenti di argomento da escludere dall'individuazione.
- Visibilità sull'argomento: selezione degli utenti che possono visualizzare gli argomenti come elementi salienti, nelle pagine di ricerca e nell'argomento.
- Autorizzazioni per l'argomento: selezione degli utenti autorizzati a creare, modificare e gestire gli argomenti.
- Centro argomenti: creare il centro argomenti.
- Revisione: controllare e applicare le impostazioni.

Per configurare la rete delle informazioni:

1. Nell'interfaccia di amministrazione di Microsoft 365 (admin.microsoft.com), selezionare **Setup** e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .
2. Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.<br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.<br/>

    ![Per iniziare](../media/content-understanding/k-get-started.png) </br>

4. Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento. Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione. Questo include:</br>
    a. **Tutti i siti** : tutti i siti di SharePoint nel tenant. Questo acquisisce i siti correnti e futuri.</br>
    b. **All, eccetto siti selezionati** : digitare i nomi dei siti che si desidera escludere.  È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. </br>
    c. **Solo siti selezionati** : digitare i nomi dei siti che si desidera includere. È inoltre possibile caricare un elenco di siti. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti. </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/ksetup1.png) </br>
   
5. Nella sezione **Escludi argomenti per nome** è possibile scegliere di includere i nomi degli argomenti che non si desidera siano inclusi nei risultati individuati. Utilizzare questa impostazione per impedire l'inclusione di argomenti sensibili nell'ambito della rete della Knowledge base. Le opzioni includono:</br>
    a. **Non escludere argomenti** </br>
    b. **Escludi argomenti per nome** : se sono presenti argomenti che non si desidera vengano visualizzati dagli utenti nell'ambito della rete della Knowledge base.</br>

    ![Escludi argomenti](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a>Come escludere gli argomenti per nome    

    Se è necessario escludere gli argomenti, fare clic su **Scarica il modello. csv** dopo aver selezionato **Escludi argomenti per nome**. Utilizzare Excel. Modello CSV che include un elenco di argomenti che si desidera escludere dai risultati dell'individuazione.

    ![Escludi argomenti nel modello CSV](../media/content-understanding/csv1.png) </br>

    Nel modello CSV, immettere le informazioni seguenti sugli argomenti che si desidera escludere:

    - **Nome** : digitare il nome dell'argomento che si desidera escludere. Questa operazione può essere eseguita in due modi:</br>
        - Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL* ).</br>
        - Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.  Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco* , *saldatura ad arco al plasma* o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.</br>
    - **Espansione (facoltativo)** : se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.</br>
    - **MatchType-exact/partial** : digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .</br>

    Dopo aver completato e salvato il file del modello CSV, selezionare **Sfoglia** per individuarlo e selezionarlo.
    
    Selezionare **Avanti**.</br>

6. Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento. Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento. È possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>
    c. **Nessuno**</br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti. 

7. Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti. Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Solo persone o gruppi di sicurezza selezionati**</br>
8. Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</br>
    a. **Tutti gli utenti dell'organizzazione**</br>
    b. **Utenti o gruppi di sicurezza selezionati**</br>

    ![Autorizzazioni per la gestione degli argomenti](../media/content-understanding/ksetup3.png) </br>

    Selezionare **Avanti**.</br>
9. Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.  Nella casella **nome centro argomenti** Digitare un nome per il centro degli argomenti. Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione sito** . </br>

Selezionare **Avanti**.</br>

   ![Creare centro informazioni](../media/content-understanding/ksetup4.png) </br> 

10. Nella pagina **Verificare e completare** , è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche. Al termine, selezionare **Attiva**.

    ![Fine e Revisione](../media/content-understanding/ksetup5.png) </br> 

11. Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni. Scegliere **Fatto**.</br>

    ![Attivato](../media/content-understanding/ksetup6.png) </br> 

12. Verrà restituito alla pagina **Connect people to Knowledge** . In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione. 

    ![Impostazioni applicate](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Dopo l'installazione, un amministratore può [apportare modifiche alle impostazioni di gestione delle informazioni selezionate](topic-experiences-discovery.md) in qualsiasi momento tornando alla pagina.


## <a name="see-also"></a>Vedere anche



  






