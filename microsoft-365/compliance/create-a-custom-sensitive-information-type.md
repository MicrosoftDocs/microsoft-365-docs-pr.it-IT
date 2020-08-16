---
title: Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Scoprire come creare, modificare, rimuovere e testare tipi di informazioni sensibili personalizzati per la prevenzione della perdita dei dati (DLP) nell'interfaccia utente grafica nel Centro sicurezza e conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c54cd9d4969c87bbd83b3048883d8a84dd9bc59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686660"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità

Leggere questo articolo per creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)). I tipi di informazioni sensibili personalizzati creati con questo metodo vengono aggiunti al pacchetto di regole denominato `Microsoft.SCCManaged.CustomRulePack`.

È anche possibile creare tipi di informazioni sensibili personalizzati usando PowerShell e le funzionalità del classificatore Exact Data Match. Per altre informazioni su questi metodi, vedere:
- [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Creare un tipo di informazioni sensibili personalizzato per DLP con Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

> [!NOTE]
> Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:
> - Cinese (semplificato)
> - Cinese (tradizionale)
> - Coreano
> - Giapponese
> 
>Questa versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o alle aree geografiche seguenti:
> - Giappone
> - Corea del Sud
> - Cina
> - RAS di Hong Kong
> - RAS di Macao
> - Taiwan
>
>Il supporto è disponibile per i tipi di informazioni sensibili. Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).

## <a name="before-you-begin"></a>Prima di iniziare

> [!NOTE]
> È necessario avere le autorizzazioni di amministratore globale o di amministratore della conformità per creare, testare e distribuire un tipo personalizzato di informazioni riservate tramite l'interfaccia utente. Vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) di Office 365.

- L'organizzazione deve disporre di un abbonamento, ad esempio Office 365 Enterprise, che includa le funzionalità per la prevenzione della perdita dei dati (DLP). Vedere la descrizione del servizio [Criteri di messaggistica e conformità](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 

- I tipi di informazioni sensibili personalizzati richiedono una certa familiarità con le espressioni regolari (RegEx). Per ulteriori informazioni sul motore Boost.RegEx (in precedenza noto come RegEx++) utilizzato per l'elaborazione del testo, vedere [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

  Il Supporto tecnico Microsoft non può dare assistenza con la creazione di classificazioni personalizzate o modelli di espressioni regolari. I tecnici del supporto possono fornire supporto limitato per la funzionalità, ad esempio fornire esempi di modelli di espressioni regolari a scopo di test o aiutare nella risoluzione dei problemi di un modello di espressione regolare esistente che non si attiva come previsto. Non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente.

- La prevenzione della perdita dei dati usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business. Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario ripetere la ricerca per indicizzazione del contenuto. Il contenuto viene sottoposto a ricerca per indicizzazione in base a una pianificazione, ma è possibile ripetere manualmente la ricerca per indicizzazione del contenuto per una raccolta siti, un elenco o una raccolta. Per altre informazioni, vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, di una raccolta o di un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.

Le impostazioni sono abbastanza chiare e vengono spiegate nella pagina della procedura guidata associata:

- **Nome**

- **Descrizione**

- **Prossimità**

- **Livello di probabilità**

- **Elemento pattern principale** (parole chiave, espressione regolare o dizionario)

- Facoltativo **Elementi pattern di supporto** (parole chiave, espressione regolare o dizionario) e un valore di **costo minimo** corrispondente.

Ecco uno scenario: si desidera un tipo di informazioni sensibili personalizzato che rilevi i numeri dipendente di 9 cifre nel contenuto, con le parole chiave "dipendente", "ID" e "badge". Per creare un tipo di informazioni sensibili personalizzato, procedere come segue:

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.

    ![Posizione dei tipi di informazioni riservate e pulsante Crea](../media/scc-cust-sens-info-type-new.png)

2. Nella pagina **Scegliere un nome e una descrizione** che viene visualizzata, immettere i valori seguenti:

  - **Nome**: ID dipendente.

  - **Descrizione**: Rilevare i numeri ID dipendente di Contoso di 9 cifre.

    ![Pagina con nome e descrizione](../media/scc-cust-sens-info-type-new-name-desc.png)

    Al termine dell'operazione, fare clic su **Avanti**.

3. Nella pagina **Requisiti per la corrispondenza** che viene visualizzata, fare clic su **Aggiungi un elemento** e configurare le impostazioni seguenti:

    - **Rilevare il contenuto che contiene**:
 
      a. Fare clic su **Una qualsiasi di queste condizioni** e selezionare **Espressione regolare**.

      b. Nella casella di espressione regolare, immettere `(\s)(\d{9})(\s)` (numeri di 9 cifre racchiusi da spazi).
  
    - **Elementi di supporto**: fare clic su **Aggiungi gli elementi di supporto** e selezionare **Contiene questo elenco di parole chiave**.

    - Nell'area **Contiene questo elenco di parole chiave** che viene visualizzata, configurare le impostazioni seguenti:

      - **Elenco di parole chiave**: immettere il valore seguente: dipendente,ID,badge.

      - **Numero minimo**: lasciare il valore predefinito 1.

    - Lasciare il valore 60 del **Livello di probabilità** predefinito. 

    - Lasciare il valore 300 della **Prossimità dei caratteri** predefinito.

    ![Pagina Requisiti per la corrispondenza](../media/scc-cust-sens-info-type-new-reqs.png)

    Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Verifica e completamento** che viene visualizzata, controllare le impostazioni e fare clic su **Fine**.

    ![Pagina Verifica e completamento](../media/scc-cust-sens-info-type-new-review.png)

5. La pagina successiva invita a testare il nuovo tipo di informazioni sensibili personalizzato facendo clic su **Sì**. Per ulteriori informazioni, vedere **Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità**. Per testare la regola in un secondo momento, fare clic su [No](#test-custom-sensitive-information-types-in-the-security--compliance-center).

    ![Pagina Suggerimenti per il test](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che sia stato creato correttamente un nuovo tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:

  - Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e verificare che sia presente il nuovo tipo di informazioni sensibili personalizzato.

  - Testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>Modificare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

**Note**:
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- È possibile modificare solo i tipi di informazioni sensibili personalizzati; non è possibile modificare quelli predefiniti. Tuttavia, è possibile usare PowerShell per esportare i tipi di informazioni sensibili personalizzati predefiniti, personalizzarli e importarli come tipi di informazioni sensibili personalizzati. Per ulteriori informazioni, vedere [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md).

- È possibile modificare solo i tipi di informazioni riservate personalizzati creati nell'interfaccia utente. Se è stata usata la [procedura di PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per importare un pacchetto di regole di tipo di informazioni riservate personalizzato, si riceverà un messaggio di errore.

Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**, selezionare il tipo di informazioni sensibili personalizzato da modificare e quindi fare clic su **Modifica**.

  ![Posizione dei tipi di informazioni riservate e pulsante Modifica](../media/scc-cust-sens-info-type-edit.png)

Le stesse opzioni sono disponibili qui come quando è stato creato il tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che sia stato modificato correttamente un tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:

  - Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare le proprietà del tipo di informazioni sensibili personalizzato modificato. 

  - Testare il tipo di informazioni sensibili personalizzato modificato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>Rimuovere tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità 

**Note**:

- È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.

- Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare uno o più tipi di informazioni sensibili personalizzati da rimuovere.

2. Nel menu a comparsa che viene visualizzato, fare clic su **Elimina** (o **Eliminare i tipi di informazioni sensibili** se ne sono stati selezionati più di uno).

    ![Posizione dei tipi di informazioni riservate e pulsante Elimina](../media/scc-cust-sens-info-type-delete.png)

3. Nel messaggio di avviso che viene visualizzato, fare clic su **Sì**.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per accertarsi di aver rimosso correttamente un tipo di informazioni sensibili personalizzato, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare che il tipo di informazioni sensibili personalizzato non sia più presente.

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>Testare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**.

2. Selezionare uno o più tipi di informazioni sensibili personalizzati da testare. Nel menu a comparsa che viene visualizzato, fare clic su **Tipo di test** (o **Test dei tipi di informazioni sensibili** se ne sono stati selezionati più di uno).

    ![Posizione dei tipi di informazioni riservate e pulsante Tipo di test](../media/scc-cust-sens-info-type-test.png)

3. Nella pagina **Carica file da testare** che viene visualizzata, caricare un documento per il test trascinando e rilasciando un file o facendo clic su **Sfoglia** e selezionando un file.

    ![Pagina Carica file da testare](../media/scc-cust-sens-info-type-test-upload.png)

4. Fare clic sul pulsante **Test** per testare il documento per individuare le corrispondenze al criterio nel file.

5. Nella pagina **Risultati corrispondenza** fare clic su **Fine**.

    ![Risultati corrispondenza](../media/scc-cust-sens-info-type-test-results.png)
