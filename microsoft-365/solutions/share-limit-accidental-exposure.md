---
title: Limitare l'esposizione accidentale
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Informazioni su come limitare l'esposizione accidentale di informazioni quando si condividono file con persone esterne all'organizzazione.
ms.openlocfilehash: 266c395b6165eac4fbb7c3f7a6ed9e77a1287ba4
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527623"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione

Quando si condividono file e cartelle con persone esterne all'organizzazione sono disponibili varie opzioni per ridurre le possibilità di condivisione accidentale di informazioni sensibili. È possibile scegliere tra le opzioni disponibili in questo articolo per soddisfare al meglio le esigenze dell'organizzazione.

## <a name="use-best-practices-for-anyone-links"></a>Usare le procedure consigliate per i collegamenti di tipo “Chiunque”

Se le persone dell'organizzazione devono eseguire la condivisione non autenticata, ma si teme che il contenuto venga modificato da utenti non autenticati, vedere [Procedure consigliate per la condivisione non autenticata](best-practices-anonymous-sharing.md) per istruzioni su come gestire la condivisione non autenticata nell'organizzazione.

## <a name="turn-off-anyone-links"></a>Disattivare i collegamenti di tipo “Chiunque”

È consigliabile lasciare abilitati i collegamenti di tipo *Chiunque* per il contenuto appropriato, perché è il modo più semplice per condividere informazioni e contribuisce a ridurre il rischio che gli utenti cerchino altre soluzioni fuori dal controllo del reparto IT. I collegamenti di tipo *Chiunque* possono essere inoltrati ad altri, ma l'accesso ai file è disponibile solo per gli utenti che dispongono del collegamento.

Se si vuole che le persone esterne all'organizzazione eseguano sempre l'autenticazione per accedere al contenuto di SharePoint, Groups o Teams, è possibile disattivare la condivisione *Chiunque*. In questo modo si impedisce agli utenti di condividere il contenuto senza autenticazione.

Se si disabilitano i collegamenti di tipo *Chiunque*, gli utenti potranno comunque condividerli facilmente con gli utenti guest utilizzando i collegamenti di tipo *Persone specifiche*. In questo caso, per poter accedere al contenuto condiviso, tutte le persone esterne all'organizzazione dovranno eseguire l'autenticazione.

In base alle proprie esigenze, è possibile disabilitare i collegamenti di tipo *Chiunque* per siti specifici o per l'intera organizzazione.

Per disattivare i collegamenti di tipo *Chiunque* per l'organizzazione
1. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.
2. Impostare le impostazioni di condivisione esterna di SharePoint su **Utenti guest nuovi ed esistenti**.</br>
   ![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-organization-external-sharing-controls-new-users.png)
3. Fare clic su **Salva**.

Per disattivare i collegamenti di tipo *Chiunque* per un sito
1. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.
2. Selezionare il sito del team appena creato.
3. Sulla barra multifunzione fare clic su **Condivisione**.
4. Verificare che la condivisione sia impostata su **Utenti guest nuovi ed esistenti**.</br>
   ![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)
5. Se si apportano modifiche, fare clic su **Salva**.

## <a name="domain-filtering"></a>Filtro domini

È possibile usare gli elenchi di domini consentiti o non consentiti per determinare i domini che gli utenti interni possono condividere con persone esterne all'organizzazione.

Con un elenco di domini consentiti è possibile specificare un elenco di domini in cui gli utenti dell'organizzazione possono condividere con persone esterne all'organizzazione. La condivisione con altri domini è bloccata. Se l'organizzazione collabora solo con persone da un elenco di domini specifici, è possibile usare questa funzionalità per impedire la condivisione con altri domini.

Con un elenco di domini non consentiti è possibile specificare un elenco di domini da cui gli utenti dell'organizzazione non possono condividere con persone esterne all'organizzazione. La condivisione con i domini elencati è bloccata. Questa opzione può essere utile, ad esempio, se si vuole impedire che alcuni concorrenti possano accedere a contenuto della propria organizzazione.

Gli elenchi di domini consentiti e non consentiti influiscono solo sulle condivisioni con utenti guest. Gli utenti possono continuare a condividere contenuti con persone da domini non consentiti tramite i collegamenti di tipo *Chiunque*, se questi non sono stati disabilitati. Per ottenere risultati ottimali con gli elenchi di domini consentiti e non consentiti, è consigliabile disabilitare i collegamenti di tipo *Chiunque* come descritto sopra.

Per configurare un elenco di domini consentiti o non consentiti per gli persone esterne all'organizzazione
1. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.
2. In **Impostazioni avanzate per la condivisione esterna** selezionare la casella di controllo **Limitare la condivisione esterna in base al dominio**.
3. Fare clic su **Aggiungi domini**.
4. Selezionare se si vogliono bloccare i domini, digitare i domini e quindi fare clic su **OK**.</br>
   ![Screenshot dell’impostazione di SharePoint Limitare la condivisione esterna in base al dominio](../media/sharepoint-sharing-block-domain.png)
5. Fare clic su **Salva**.

Se si vuole limitare la condivisione in base al dominio a un livello superiore rispetto a SharePoint e OneDrive, è possibile [consentire o bloccare gli inviti agli utenti B2B da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory. (È necessario configurare l’[anteprima dell'integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) perché queste impostazioni influiscano su SharePoint e OneDrive.)

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Limitare la condivisione di file, cartelle e siti con persone esterne all'organizzazione a gruppi di sicurezza specifici

È possibile limitare la condivisione di file, cartelle e siti con persone esterne all'organizzazione ai membri di un gruppo di sicurezza specifico. Questa opzione è utile se si vuole abilitare la condivisione esterna, ma con un flusso di lavoro di approvazione o un processo di richiesta.

Per limitare la condivisione esterna ai membri di un gruppo di sicurezza
1. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.
2. In **Altre impostazioni** seguire il collegamento **Limitare la condivisione esterna ai gruppi di sicurezza**.
3. In **Chi può condividere all'esterno dell'organizzazione** selezionare una o entrambe le caselle di controllo: a. **Consenti solo agli utenti dei gruppi di sicurezza selezionati di condividere con utenti esterni autenticati** per specificare un gruppo di sicurezza che può condividere con utenti autenticati b. **Consenti la condivisione con utenti esterni autenticati e usando collegamenti anonimi ai soli utenti dei gruppi di sicurezza selezionati** per specificare un gruppo di sicurezza che può condividere con utenti autenticati e usando collegamenti di tipo Chiunque
4. Fare clic su **OK**.

Si noti che questo influisce su file, cartelle e siti, ma non sui gruppi di Microsoft 365 o su Teams. Quando i membri invitano gli utenti guest a un gruppo di Microsoft 365 privato o a un team privato in Microsoft Teams, l'invito viene inviato al proprietario del gruppo o del team per l'approvazione.

## <a name="see-also"></a>Vedere anche

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

[Procedure consigliate per la condivisione di file e cartelle con utenti anonimi](best-practices-anonymous-sharing.md)