---
title: Eseguire l'acquisizione di un amministratore interno
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Informazioni su come verificare la proprietà della posta elettronica e del dominio per assumere il controllo di un tenant non gestito creato da un utente in modalità self-service Microsoft 365.
ms.openlocfilehash: f6378c708e0533c2da2d38bfe5eb8009515423c7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393848"
---
# <a name="perform-an-internal-admin-takeover"></a>Eseguire l'acquisizione di un amministratore interno

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 

Se sei un amministratore e vuoi assumere un tenant non gestito creato da un'iscrizione utente self-service, puoi farlo con un'acquisizione da parte di un amministratore interno.

> [!NOTE]
> Una registrazione self-service per qualsiasi servizio cloud che usa Azure AD aggiungerà l'utente a una directory azure AD non gestita o "shadow" e creerà un tenant non gestito. Un tenant non gestito è una directory senza un amministratore globale. Per determinare se un tenant è gestito o non gestito, vedere [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Passaggio 1: Verificare l'indirizzo di posta elettronica

> [!NOTE]
> Se il servizio self-service è abilitato nel tenant, gli utenti possono sottoscrivere servizi gratuiti, ad esempio Power BI, autonomamente. Questi passaggi presuppongono che una sottoscrizione utente in modalità self-service abbia creato il tenant non gestito che si desidera assumere come amministratore. Nel primo passaggio viene creato un contesto utente nel tenant non gestito, usando Power BI per illustrare il percorso di acquisizione dell'amministratore.

1. Per iscriverti Power BI, vai al sito [di Power BI](https://powerbi.com) e seleziona Avvia la versione di valutazione gratuita di Start gratuito (nella casella Condividi  >   con Power BI Pro). 

2. Iscriversi con un account utente che utilizza il nome di dominio dell'organizzazione (ad esempio `powerbiadmin@contoso.com` ). Se l'account è già in uso, accedere utilizzando la password corrente.

3. Controllare il codice di verifica nel messaggio di posta **elettronica** e immettere il codice per convalidare l'indirizzo di posta elettronica.
    
## <a name="step-2-create-a-new-account"></a>Passaggio 2: Creare un nuovo account

1. Quando immetti il codice di verifica, verrà visualizzata una pagina in cui puoi creare un nuovo account. 
    
2. Compilare i campi nome utente e password con l'account che si desidera utilizzare, quindi selezionare **Avvia**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Passaggio 3: verificare la proprietà del dominio e diventare l'amministratore

1. Verrà **aperta la procedura guidata** Diventa amministratore. Se la procedura guidata non viene avviata, cerca il riquadro **Amministratore** e selezionalo. 

2. Selezionare **Sì, voglio essere l'amministratore.**

3. Verificare di essere proprietari del dominio che si desidera assumere aggiungendo un record TXT al registrar. La procedura guidata fornirà il record TXT da aggiungere, nonché un collegamento al sito Web del registrar e un collegamento a istruzioni dettagliate.
    
4. Dopo aver aggiunto il record TXT al sito del registrar, tornare alla procedura guidata e selezionare Ok, il **record è stato aggiunto.**
    
> [!NOTE]
> L'assunzione del tenant shadow non inciderà sulle informazioni o sui servizi esistenti. Tuttavia, se tutti gli utenti del dominio si sono registrati per i servizi che richiedono una licenza, ti verrà chiesto di acquistare licenze per loro come parte dell'assunzione del ruolo di amministratore. Puoi acquistare o rimuovere licenze al termine del processo di configurazione dell'amministratore.
  
## <a name="related-content"></a>Contenuto correlato

YouTube: [3 passaggi per eseguire un'acquisizione](https://www.youtube.com/watch?v=xt5EsrQBZZk) da amministratore IT per Power BI e Microsoft 365 (video)\
[Acquisizione dell'amministratore in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (articolo)\
[Uso dell'iscrizione in modalità self-service nell'organizzazione](self-service-sign-up.md) (articolo)\
[Informazioni sul ruolo Power BI amministratore del servizio](/power-bi/service-admin-role) (articolo)