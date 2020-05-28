---
title: Transizione di un abbonamento Microsoft 365 Business CSP
description: Informazioni su come è possibile eseguire la transizione di un abbonamento CSP Microsoft 365 business dall'anteprima alla disponibilità generale (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
- AdminSurgePortfolio
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, abbonamento CSP transizione
ms.date: 11/01/2017
ms.openlocfilehash: 5fc532b4a59d8e94068e7e1bae99bf8edac75abb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403431"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Transizione di un abbonamento Microsoft 365 Business CSP

Se hai un abbonamento Microsoft 365 Business Preview CSP, segui questa guida per scoprire come eseguire la transizione dal tuo abbonamento in anteprima a Microsoft 365 Business GA (disponibilità generale).

**Come eseguire la transizione a un abbonamento in anteprima su GA**

1. Accedere al <a href="https://partnercenter.microsoft.com" target="_blank">centro partner</a>.
2. Dal dashboard seleziona **Clienti**, quindi trova e seleziona il nome della società.

    Visualizzerai un elenco degli abbonamenti della società.

    ![Abbonamenti dei clienti nel Centro per i partner](../../media/pc_customer_subscriptions_1.png)
    
3. Nella pagina **abbonamenti** della società selezionare **Aggiungi sottoscrizione**.
4. Nella pagina **nuova sottoscrizione** , selezionare **Small Business** , quindi selezionare **Microsoft 365 business** dall'elenco.
5. Aggiungi il numero di licenze, quindi seleziona **Successivo: Revisione** per esaminare l'abbonamento, poi seleziona **Inoltra**.

    ![Esaminare la nuova sottoscrizione a Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    **Sottoscrizioni basate su licenza** mostrerà **Microsoft 365 Business Preview** e **Microsoft 365 Business**. Verrà sospesa la sottoscrizione di anteprima successiva.

6. Seleziona **Microsoft 365 Business Preview**.
7. Nella pagina **Microsoft 365 business Preview** selezionare **sospesa** per sospendere la sottoscrizione di anteprima.

    ![Sospendere la nuova sottoscrizione a Microsoft 365 Business](../../media/pc_customer_m365bpreview_suspend.png)

8. Seleziona **Invia** per confermare.

    Nella pagina **abbonamenti** confermare che lo stato di **anteprima di Microsoft 365 business** sia **sospeso**.

    ![Conferma che lo stato della sottoscrizione dell'anteprima sia sospeso](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Facoltativamente, puoi convalidare il contratto di licenza. A tale scopo, attieniti alla seguente procedura:
    1. Seleziona **Utenti e licenze** dalla pagina **Sottoscrizioni** dell'azienda.
    2. Nella pagina **utenti e licenze** selezionare un utente.
    3. Nella pagina dell'utente, selezionare la sezione **assegna licenze** e verificare che sia in grado di visualizzare **Microsoft 365 business**.

        ![Conferma che la licenza di Microsoft 365 Business è assegnata all'utente](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Conseguenze per clienti e utenti durante e dopo la transizione

Non vi è alcun impatto sui clienti e gli utenti durante la transizione e dopo la transizione.

## <a name="impact-to-customers-who-dont-transition"></a>Conseguenze per i clienti che non effettuano la transizione

La tabella seguente riepiloga le conseguenze per i clienti che non passano da una sottoscrizione dell'anteprima Microsoft 365 Business a una sottoscrizione Microsoft 365 Business.

|       | Da T-0 a T+30     | Da T+30 a T+60 | Da T+60 a T+120 | Oltre 120 + T  |
|-------|-----------------|--------------|---------------|---------------|
| **Stato** | Periodo di tolleranza | Scaduto      | Disattivato      | Senza provisioning |
| **Impatti del servizio**                                                        |
| **Portale di amministrazione di Microsoft 365 Business** | Nessun impatto sulla funzionalità | Nessun impatto sulla funzionalità | Puoi aggiungere/eliminare gli utenti, acquistare sottoscrizioni.</br> Non è possibile assegnare o revocare le licenze. | La sottoscrizione del cliente e tutti i dati verranno eliminati. L'amministratore può gestire altre sottoscrizioni a pagamento. |
| **App di Office**                         | Nessun impatto sull'utente finale | Nessun impatto sull'utente finale | Office entra in modalità con funzionalità ridotte.</br> Gli utenti possono visualizzare solo i file. | Office entra in modalità con funzionalità ridotte.</br> Gli utenti possono visualizzare solo i file. |
| **Servizi cloud (SharePoint Online, Exchange Online, Skype, Teams e altro)** | Nessun impatto sull'utente finale | Nessun impatto sull'utente finale | Gli utenti finali e gli amministratori non hanno accesso ai dati nel cloud. | La sottoscrizione del cliente e tutti i dati verranno eliminati. |
| **Componenti EM+S** | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Non è più possibile applicare la funzionalità.</br> Per altre info, vedi [Impatto dei dispositivi mobili dopo la scadenza della sottoscrizione](#mobile-device-impacts-upon-subscription-expiration) e [Impatto sui PC Windows 10 alla scadenza della sottoscrizione](#windows-10-pc-impacts-upon-subscription-expiration). | Non è più possibile applicare la funzionalità.</br> Per altre info, vedi [Impatto dei dispositivi mobili dopo la scadenza della sottoscrizione](#mobile-device-impacts-upon-subscription-expiration) e [Impatto sui PC Windows 10 alla scadenza della sottoscrizione](#windows-10-pc-impacts-upon-subscription-expiration). |
| **Windows 10 Business** | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Non è più possibile applicare la funzionalità.</br> Per altre info, vedi [Impatto dei dispositivi mobili dopo la scadenza della sottoscrizione](#mobile-device-impacts-upon-subscription-expiration) e [Impatto sui PC Windows 10 alla scadenza della sottoscrizione](#windows-10-pc-impacts-upon-subscription-expiration). | Non è più possibile applicare la funzionalità.</br> Per altre info, vedi [Impatto dei dispositivi mobili dopo la scadenza della sottoscrizione](#mobile-device-impacts-upon-subscription-expiration) e [Impatto sui PC Windows 10 alla scadenza della sottoscrizione](#windows-10-pc-impacts-upon-subscription-expiration). |
| **Accesso di Azure AD a un PC Windows 10** | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Nessun impatto sull'amministratore</br> Nessun impatto sull'utente finale | Dopo l'eliminazione del tenant, un utente può accedere solo con le credenziali locali. Ricreare l'immagine del dispositivo se non esistono credenziali locali. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Impatto dei dispositivi mobili dopo la scadenza della sottoscrizione

Nella tabella seguente viene riepilogato l'impatto dei criteri di gestione delle app nei dispositivi mobili.

|                            | Licenza completa                      | T+60 giorni dopo la scadenza          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Eliminare i file di lavoro da un dispositivo inattivo** | I file di lavoro vengono rimossi dopo i giorni selezionati | I file di lavoro restano nei dispositivi personali dell'utente |
| **Chiedere agli utenti di salvare tutti i file di lavoro su OneDrive for Business** | I file di lavoro possono essere salvati solo su OneDrive for Business | I file di lavoro possono essere salvati ovunque |
| **Crittografare i file di lavoro** | I file di lavoro sono crittografati | I file di lavoro non sono più crittografati.</br> Vengono rimossi i criteri di sicurezza e i dati di Office sulle app. |
| **Richiedere PIN o impronta digitale per accedere alle app di Office** | Accesso limitato alle app | Nessuna restrizione di accesso a livello di app |
| **Reimpostare il PIN in caso di errore di accesso** | Accesso limitato alle app | Nessuna restrizione di accesso a livello di app |
| **Richiedere agli utenti di accedere nuovamente dopo un periodo di inattività delle app di Office** | Accesso richiesto | Nessuna richiesta di accesso |
| **Negare l'accesso ai file in dispositivi jailbroken o rooted di lavoro** | Non è possibile accedere ai file di lavoro nei dispositivi jailbroken/rooted | L'accesso ai file di lavoro è consentito solo da dispositivi jailbroken/rooted |
| **Consentire agli utenti di copiare il contenuto da app di Office in App personali** | Copia/incolla limitato alle app disponibili come parte dell'abbonamento a Microsoft 365 | Copia/Incolla disponibile per tutte le app |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Impatto dei PC Windows 10 dopo la scadenza della sottoscrizione

La tabella seguente riepiloga l'impatto sui criteri di configurazione del dispositivo Windows 10.

|                            | Licenza completa                      | T+60 giorni dopo la scadenza          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Proteggere il PC da minacce con Windows Defender** | Attiva/Disattiva è fuori controllo utente | L'utente può disattivare Windows Defender sul PC Windows 10 |
| **Proteggere il PC da minacce basate sul Web in Microsoft Edge** | Protezione del PC in Microsoft Edge | L'utente può accendere/spegnere la protezione del PC in Microsoft Edge |
| **Disattivare lo schermo del dispositivo quando è inattivo** | L'amministratore definisce i criteri di intervallo di timeout dello schermo | Il timeout dello schermo può essere configurato dall'utente finale |
| **Consentire agli utenti di scaricare app da Microsoft Store** | L'amministratore stabilisce se un utente può scaricare app da Microsoft Store | L'utente può scaricare app da Microsoft Store in qualsiasi momento |
| **Consentire agli utenti di accedere a Cortana** | L'amministratore definisce i criteri di accesso utente a Cortana | Dispositivi utente per attivare/disattivare Cortana |
| **Consentire agli utenti di ricevere suggerimenti e annunci da Microsoft** | L'amministratore definisce i criteri utente per ricevere suggerimenti e annunci da Microsoft | L'utente può abilitare/disabilitare suggerimenti e annunci da Microsoft |
| **Consentire agli utenti di copiare il contenuto da app di Office in App personali** | L'amministratore definisce i criteri per mantenere aggiornati i dispositivi Windows 10 | Gli utenti possono decidere quando aggiornare Windows |
