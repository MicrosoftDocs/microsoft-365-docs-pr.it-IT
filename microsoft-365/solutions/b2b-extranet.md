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
description: Informazioni su come creare un sito Extranet B2B o un team con utenti guest gestiti da un'organizzazione partner.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904757"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Creare una Extranet B2B con guest gestiti.

È possibile usare [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) per creare una extranet B2B per collaborare con un'organizzazione partner che usa Azure Active Directory. In questo modo gli utenti possono registrarsi autonomamente nel sito Extranet o nel team e ricevere l'accesso tramite un flusso di lavoro di approvazione.

Con questo metodo di condivisione delle risorse per la collaborazione, l'organizzazione partner può aiutare a mantenere e approvare gli utenti guest, riducendo l'onere per il reparto IT e consentendo ai più familiari con il contratto di collaborazione di gestire l'accesso degli utenti.

In questo articolo vengono descritti i passaggi per creare un pacchetto di risorse (in questo caso un sito o un team) che è possibile condividere con un'organizzazione partner tramite un modello di registrazione di accesso self-service. 

Prima di iniziare, creare il sito o il team che si desidera condividere con l'organizzazione partner e abilitarlo per la condivisione guest. Per [ulteriori informazioni,](collaborate-in-site.md) vedere Collaborare con gli utenti guest in un sito o Collaborare con gli utenti guest di un [team.](collaborate-as-team.md) È inoltre consigliabile consultare Creare un ambiente di condivisione [guest](create-secure-guest-sharing-environment.md) sicuro per informazioni sulle funzionalità di sicurezza e conformità che è possibile utilizzare per mantenere i criteri di governance quando si collabora con gli utenti guest.

## <a name="license-requirements"></a>Requisiti di licenza

L'uso di questa funzionalità richiede una licenza di Azure AD Premium P2. 

I cloud specializzati, come Azure Germany e Azure China 21Vianet, non sono attualmente disponibili per l'uso.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrate le procedure descritte in questo articolo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Connettere l'organizzazione partner

Per invitare guest da un'organizzazione partner, è necessario aggiungere il dominio del partner come organizzazione connessa in Azure Active Directory.

Per aggiungere un'organizzazione connessa
1. In [Azure Active Directory](https://aad.portal.azure.com)fare clic su Governance **dell'identità.**
2. Fare **clic su Organizzazioni connesse**.
4. Fare **clic su Aggiungi organizzazione connessa.**
5. Digitare un nome e una descrizione per l'organizzazione e quindi fare clic su **Avanti: Directory + dominio**.
6. Fare **clic su Aggiungi directory + dominio.**
7. Digitare il dominio dell'organizzazione che si desidera connettere e quindi fare clic su **Aggiungi.**
8. Fare **clic su** Connetti e quindi su **Avanti: Sponsor.**
9. Aggiungere persone dell'organizzazione o dell'organizzazione a cui ci si connette a chi si desidera approvare l'accesso per gli utenti guest.
10. Fare clic su **Avanti: Rivedi + Crea**.
11. Rivedere le impostazioni scelte e quindi fare clic su **Crea.**

    ![Screenshot della pagina delle organizzazioni connesse in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Scegliere le risorse da condividere

Il primo passaggio per selezionare le risorse da condividere con un'organizzazione partner consiste nel creare un catalogo che le contenga.

Per creare un catalogo
1. In [Azure Active Directory](https://aad.portal.azure.com)fare clic su Governance **dell'identità.**
2. Fare **clic su Cataloghi.**
3. Fare **clic su Nuovo catalogo.**
4. Digitare un nome e una descrizione per il catalogo e verificare che **Sia Abilitato** che **Abilitato** per gli utenti esterni siano entrambi impostati su **Sì.**
5. Fare clic su **Crea**.

   ![Screenshot della pagina dei cataloghi in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Dopo aver creato il catalogo, aggiungere il sito o il team di SharePoint che si desidera condividere con l'organizzazione partner.

Per aggiungere risorse a un catalogo
1. In Governance dell'identità di Azure AD, fare **clic su Cataloghi** e quindi sul catalogo in cui si desidera aggiungere risorse.
2. Fare **clic su** Risorse e quindi su Aggiungi **risorse.**
3. Selezionare i team o i siti di SharePoint che si desidera includere nella rete Extranet e quindi fare clic su **Aggiungi**.

   ![Screenshot della pagina delle risorse del catalogo in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Dopo aver definito le risorse che si desidera condividere, il passaggio successivo consiste nel creare un pacchetto di accesso, che definisce il tipo di accesso concesso agli utenti partner e il processo di approvazione per i nuovi utenti partner che richiedono l'accesso.

Per creare un pacchetto di accesso
1. In Governance dell'identità di Azure AD, fare **clic su Cataloghi** e quindi sul catalogo in cui si desidera creare un pacchetto di accesso.
2. Fare **clic su Pacchetti di** accesso e quindi su Nuovo pacchetto di **accesso.**
3. Digitare un nome e una descrizione per il pacchetto di accesso e quindi fare clic su **Avanti: Ruoli risorsa**.
4. Scegliere le risorse del catalogo che si desidera utilizzare per la rete Extranet.
5. Per ogni risorsa, nella **colonna Ruolo** scegliere il ruolo utente che si desidera concedere agli utenti guest che utilizzano l'Extranet.
6. Fare **clic su Avanti: Richieste**.
7. In **Utenti che possono richiedere l'accesso** scegliere Per gli utenti non presenti nella **directory.**
8. Verificare che **l'opzione Organizzazioni connesse specifiche** sia selezionata e quindi fare clic su Aggiungi **directory**.
9. Scegliere l'organizzazione connessa aggiunta in precedenza e quindi fare clic su **Seleziona**
10. In **Approvazione** scegliere **Sì per** Richiedi **approvazione.**
11. In **Primo responsabile approvazione** scegliere uno degli sponsor aggiunti in precedenza o scegliere un utente specifico.
12. Fare **clic su Aggiungi fallback** e selezionare un responsabile approvazione di fallback.
13. In **Abilita** scegliere **Sì.**
14. Fare **clic su Avanti: Ciclo di vita**.
15. Scegliere le impostazioni di scadenza e revisione di accesso che si desidera utilizzare e quindi fare clic su **Avanti: Revisione + Crea.**
16. Rivedere le impostazioni e quindi fare clic su **Crea.**

    ![Screenshot of the access packages screen in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Se stai collaborando con un'organizzazione di grandi dimensioni, potresti voler nascondere il pacchetto di accesso. Se il pacchetto è nascosto, gli utenti dell'organizzazione partner non potranno visualizzare il pacchetto nel *portale Di accesso.* Al contrario, devono essere inviati un collegamento diretto per iscriversi al pacchetto. Nascondere il pacchetto di accesso può ridurre il numero di richieste di accesso inappropriate e può anche aiutare a mantenere i pacchetti di accesso disponibili organizzati nel portale dell'organizzazione partner.

Per impostare un pacchetto di accesso su nascosto
1. In Governance dell'identità di Azure AD, fare clic **su Pacchetti di accesso** e quindi fare clic sul pacchetto di accesso.
2. Nella pagina **Panoramica** fare clic su **Modifica.**
3. In **Proprietà** scegliere **Sì** per **Nascosto** e quindi fare clic su **Salva.**

   ![Screenshot of an edit access package properties screen](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Invitare utenti partner

Se si imposta il pacchetto di accesso su nascosto, è necessario inviare un collegamento diretto all'organizzazione partner in modo che possa richiedere l'accesso al sito o al team.

Per trovare il collegamento al portale di accesso
1. In Governance dell'identità di Azure AD, fare clic **su Pacchetti di accesso** e quindi fare clic sul pacchetto di accesso.
2. Nella pagina **Panoramica** fare clic sul **collegamento Copia** negli Appunti per il collegamento Portale **di Access.**

   ![Screenshot of access package properties with access portal link](../media/identity-governance-access-portal-link.png)

Dopo aver copiato il collegamento, è possibile condividerlo con il contatto presso l'organizzazione partner e inviarlo agli utenti del team di collaborazione.

## <a name="see-also"></a>Vedere anche

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)