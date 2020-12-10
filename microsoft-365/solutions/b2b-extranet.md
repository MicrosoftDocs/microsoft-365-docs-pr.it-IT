---
title: Creare una Extranet B2B con guest gestiti.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come creare un sito Extranet o un team B2B con clienti gestiti provenienti da un'organizzazione partner.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613597"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Creare una Extranet B2B con guest gestiti.

È possibile utilizzare la [gestione dei diritti di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) per creare una rete Extranet B2B per collaborare con un'organizzazione partner che utilizza Azure Active Directory. Questo consente agli utenti di eseguire la registrazione automatica nel sito o nel team Extranet e di ricevere l'accesso tramite un flusso di lavoro di approvazione.

Con questo metodo di condivisione delle risorse per la collaborazione, l'organizzazione partner può contribuire a mantenere e approvare gli ospiti alla fine, riducendo l'onere per il reparto IT e consentendo ai più familiari del contratto di collaborazione di gestire l'accesso degli utenti.

In questo articolo vengono illustrati i passaggi per creare un pacchetto di risorse (in questo caso, un sito o un team) che è possibile condividere con un'organizzazione partner tramite un modello di registrazione di accesso self-service. 

Prima di iniziare, creare il sito o il team che si desidera condividere con l'organizzazione partner e abilitarlo per la condivisione degli ospiti. Per ulteriori informazioni, vedere [collaborare con gli utenti di un sito](collaborate-in-site.md) o [collaborare con gli ospiti di un team](collaborate-as-team.md) . È inoltre consigliabile esaminare [creare un ambiente di condivisione Guest sicuro](create-secure-guest-sharing-environment.md) per informazioni sulle funzionalità di sicurezza e conformità che è possibile utilizzare per gestire i criteri di governance durante la collaborazione con gli utenti.

## <a name="license-requirements"></a>Requisiti di licenza

L'utilizzo di questa funzionalità richiede una licenza P2 di Azure AD Premium. 

Nubi specializzate, come Azure Germany e Azure China 21Vianet, non sono attualmente disponibili per l'uso.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrate le procedure descritte in questo articolo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Connettere l'organizzazione partner

Per invitare gli ospiti da un'organizzazione partner, è necessario aggiungere il dominio del partner come organizzazione connessa in Azure Active Directory.

Per aggiungere un'organizzazione connessa
1. In [Azure Active Directory](https://aad.portal.azure.com)fare clic su **governance delle identità**.
2. Fare clic su **organizzazioni connesse**.
4. Fare clic su **Aggiungi organizzazione connessa**.
5. Digitare un nome e una descrizione per l'organizzazione, quindi fare clic su **Avanti: directory + dominio**.
6. Fare clic su **Aggiungi directory + dominio**.
7. Digitare il dominio per l'organizzazione che si desidera connettere e quindi fare clic su **Aggiungi**.
8. Fare clic su **Connetti** e quindi su **Avanti: sponsor**.
9. Aggiungere persone dall'organizzazione o dall'organizzazione a cui si sta effettuando la connessione per gli utenti a cui si desidera approvare l'accesso.
10. Fare clic su **Avanti: recensione + crea**.
11. Esaminare le impostazioni selezionate e quindi fare clic su **Crea**.

    ![Schermata della pagina organizzazioni connesse in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Scegliere le risorse da condividere

Il primo passaggio per la selezione delle risorse da condividere con un'organizzazione partner consiste nel creare un catalogo che li contenga.

Per creare un catalogo
1. In [Azure Active Directory](https://aad.portal.azure.com)fare clic su **governance delle identità**.
2. Fare clic su **cataloghi**.
3. Fare clic su **nuovo catalogo**.
4. Digitare un nome e una descrizione per il catalogo e assicurarsi che sia **abilitato** sia abilitato **per gli utenti esterni** siano entrambi impostati su **Sì**.
5. Fare clic su **Crea**.

   ![Schermata della pagina cataloghi in Azure Active Directory Identity governance](../media/identity-governance-catalogs.png)

Dopo aver creato il catalogo, è necessario aggiungere il sito o il team di SharePoint che si desidera condividere con l'organizzazione partner.

Per aggiungere risorse a un catalogo
1. In Azure AD Identity governance fare clic su **cataloghi** e quindi fare clic sul catalogo in cui si desidera aggiungere risorse.
2. Fare clic su **risorse** e quindi su **Aggiungi risorse**.
3. Selezionare i team o i siti di SharePoint che si desidera includere nella rete Extranet, quindi fare clic su **Aggiungi**.

   ![Schermata della pagina risorse catalogo in Azure Active Directory Identity governance](../media/identity-governance-catalog-resource.png)

Dopo aver definito le risorse che si desidera condividere, il passaggio successivo consiste nel creare un pacchetto di Access, che definisce il tipo di accesso che gli utenti partner sono concessi e il processo di approvazione per i nuovi utenti partner che richiedono l'accesso.

Per creare un pacchetto di Access
1. In Azure AD Identity governance, fare clic su **cataloghi**, quindi fare clic sul catalogo in cui si desidera creare un pacchetto di accesso.
2. Fare clic su **Access** Packages, quindi fare clic su **nuovo pacchetto di accesso**.
3. Digitare un nome e una descrizione per il pacchetto di accesso e quindi fare clic su **Avanti: ruoli risorse**.
4. Scegliere le risorse del catalogo che si desidera utilizzare per l'Extranet.
5. Per ogni risorsa, nella colonna **ruolo** scegliere il ruolo utente che si desidera concedere agli utenti che utilizzano la rete Extranet.
6. Fare clic su **Avanti: richieste**.
7. In **utenti che possono richiedere l'accesso**, scegliere **per gli utenti non presenti nella directory**.
8. Verificare che l'opzione **specifiche organizzazioni connesse** sia selezionata e quindi fare clic su **Aggiungi directory**.
9. Scegliere l'organizzazione connessa aggiunta in precedenza e quindi fare clic su **Seleziona**
10. In **approvazione**, scegliere **Sì** per **richiedere l'approvazione**.
11. In **primo responsabile approvazione** scegliere uno dei garanti aggiunti in precedenza o scegliere un utente specifico.
12. Fare clic su **Aggiungi fallback** e selezionare un responsabile approvazione fallback.
13. In **attiva**, scegliere **Sì**.
14. Fare clic su **Avanti: ciclo** di vita.
15. Scegliere le impostazioni di scadenza e revisione di Access che si desidera utilizzare e quindi fare clic su **Avanti: recensione + crea**.
16. Esaminare le impostazioni, quindi fare clic su **Crea**.

    ![Screenshot della schermata Access Packages in Azure Active Directory Identity governance](../media/identity-governance-access-packages.png)

Se si è in partnership con un'organizzazione di grandi dimensioni, è possibile che si desideri nascondere il pacchetto di accesso. Se il pacchetto è nascosto, gli utenti dell'organizzazione partner non vedranno il pacchetto sul proprio portale di *accesso* . Al contrario, è necessario inviare un collegamento diretto per iscriversi al pacchetto. Se si nasconde il pacchetto di Access, è possibile ridurre il numero di richieste di accesso inappropriate e consentire anche di mantenere i pacchetti di accesso disponibili organizzati nel portale dell'organizzazione partner.

Per impostare un pacchetto di accesso su nascosto
1. In Azure AD Identity governance, fare clic su **Access** Packages, quindi fare clic sul pacchetto di accesso.
2. Nella pagina **Panoramica** fare clic su **modifica**.
3. In **Proprietà**, scegliere **Sì** per **nascosto**, quindi fare clic su **Salva**.

   ![Schermata di una finestra di modifica delle proprietà di un pacchetto di Access](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Invitare gli utenti partner

Se si imposta il pacchetto di accesso su nascosto, è necessario inviare un collegamento diretto all'organizzazione partner in modo che possano richiedere l'accesso al sito o al team.

Per trovare il collegamento al portale di accesso
1. In Azure AD Identity governance, fare clic su **Access** Packages, quindi fare clic sul pacchetto di accesso.
2. Nella pagina **Panoramica** fare clic su **copia nel** collegamento degli Appunti per il **collegamento portale My Access**.

   ![Schermata delle proprietà del pacchetto di accesso con il collegamento al portale di accesso](../media/identity-governance-access-portal-link.png)

Dopo aver copiato il collegamento, è possibile condividerlo con il contatto nell'organizzazione partner e inviarlo agli utenti del team di collaborazione.

## <a name="see-also"></a>Vedere anche

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)
