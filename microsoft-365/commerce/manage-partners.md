---
title: Utilizzo dei provider di soluzioni
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: È possibile collaborare con i provider di soluzioni certificati Microsoft per l'acquisto e la gestione di prodotti e servizi per l'organizzazione o l'Istituto di istruzione.
keywords: partner, provider di soluzioni
ms.openlocfilehash: 341a353247635eab491eb0962273eeed09b31599
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594120"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a>Utilizzo dei provider di soluzioni in Microsoft Store for business

È possibile collaborare con i provider di soluzioni certificati Microsoft per l'acquisto e la gestione di prodotti e servizi per l'organizzazione o l'Istituto di istruzione. Sono necessari alcuni passaggi per ottenere le operazioni configurate. 

Il processo è simile al seguente:
- Gli amministratori trovano e contattano un provider di soluzioni utilizzando **trova un provider di soluzioni** in Microsoft Store for business. 
- I provider di soluzioni inviano una richiesta da centro partner ai clienti per diventare il loro provider di soluzioni.
- I clienti accettano l'invito in Microsoft Store for business e iniziano a lavorare con il provider di soluzioni.
- I clienti possono gestire le impostazioni per la relazione con partner in Microsoft Store for business. 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a>Che cosa può fare un provider di soluzioni per l'organizzazione o l'Istituto di istruzione?

Esistono diversi modi in cui un provider di soluzioni può collaborare con l'utente. I provider di soluzioni sceglieranno uno di questi casi quando invieranno la richiesta di collaborare con l'utente.

| Funzione del provider di soluzioni | Descrizione | 
| ------ | ------------------- | 
| Rivenditore | I provider di soluzioni vendono prodotti Microsoft all'organizzazione o all'Istituto di istruzione. |
| Amministratore delegato | Il provider di soluzioni gestisce i prodotti e i servizi per l'organizzazione o l'Istituto di istruzione. In Azure Active Directory (AD), il partner sarà un amministratore globale per il tenant. In questo modo è possibile gestire i servizi come la creazione di account utente, l'assegnazione e la gestione delle licenze e la reimpostazione della password. |
| Reseller & amministratore delegato | Provider di soluzioni per la vendita e la gestione di prodotti e servizi Microsoft per l'organizzazione o l'Istituto di istruzione. |
| Partner | È possibile assegnare al provider di soluzioni un account utente nel tenant e lavorare per conto di altri servizi Microsoft. |
| Partner di Microsoft Products & Services Agreement (MPSA) | Se si è lavorato con più provider di soluzioni tramite il programma MPSA, è possibile consentire ai partner di visualizzare gli acquisti effettuati dall'altro. |
| Partner PC OEM | I provider di soluzioni possono caricare gli ID dispositivo per i computer che si sta [gestendo con Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).   |
| Partner line-of-business (LOB) | I provider di soluzioni possono sviluppare, inviare e gestire app LOB specifiche per l'organizzazione o per la scuola. |

## <a name="find-a-solution-provider"></a>Trovare un provider di soluzioni

È possibile trovare partner in Microsoft Store for Business and Education. 

1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com/) o [Microsoft Store per l'istruzione](https://educationstore.microsoft.com/).
2. Selezionare **trova un provider di soluzioni**.
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. Affinare l'elenco o cercare un provider di soluzioni. 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. Quando si trova un provider di soluzioni con cui si è interessati, fare clic su **contatto**.
5. Completare e inviare il modulo.

Il provider di soluzioni verrà contattato. Si avrà la possibilità di saperne di più. Se si decide di collaborare con il provider di soluzioni, l'utente invierà un invito di posta elettronica da centro partner. 

## <a name="work-with-a-solution-provider"></a>Utilizzo di un provider di soluzioni

Dopo aver trovato un provider di soluzioni e aver deciso di collaborare, ti invierà un invito a collaborare con il centro partner. In Microsoft Store for business o Education, è necessario accettare l'invito. Successivamente, è possibile gestire le autorizzazioni.

**Per accettare un invito a un provider di soluzioni**
1. **Segui il collegamento tramite posta elettronica** : si riceverà un messaggio di posta elettronica con un collegamento per accettare l'invito del provider di soluzioni dal provider di soluzioni. Il collegamento vi consentirà di Microsoft Store for business o Education.
2. **Accetta** invito-su **accetta**invito del partner, selezionare **autorizza** per accettare l'invito, accettare i termini del contratto cloud Microsoft e iniziare a lavorare con il provider di soluzioni. 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a>Privilegi di amministratore delegati

In base alla richiesta effettuata dal provider di soluzioni, parte dell'accettazione dell'invito includerà il consenso per fornire privilegi di amministratore delegati al provider di soluzioni. Ciò avverrà quando la richiesta del provider di soluzioni includerà l'azione di amministratore delegato. Per ulteriori informazioni, vedere [Delegated admin privileges in Azure ad](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad). 

Se non si desidera delegare i privilegi di amministratore al provider di soluzioni, è necessario annullare l'invito anziché accettarlo. 

Se si delegano i privilegi di amministratore a un provider di soluzioni, è possibile rimuoverlo in un secondo momento. 

**Per rimuovere i privilegi di amministratore delegato**
1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com/) o [Microsoft Store per l'istruzione](https://educationstore.microsoft.com/).
2. Seleziona **partner**
3. Scegliere il partner che si desidera gestire.
4. Selezionare **Rimuovi autorizzazioni delegate**. 

Il provider di soluzioni sarà comunque in grado di collaborare con l'utente, ad esempio, come rivenditore. 
