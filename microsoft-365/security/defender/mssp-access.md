---
title: Fornire l'accesso msSP (Managed Security Service Provider)
description: Informazioni sulle modifiche da Microsoft Defender Security Center al Centro sicurezza Microsoft 365
keywords: Introduzione al Centro sicurezza Microsoft 365, OATP, MDATP, MDO, MDE, riquadro singolo di vetro, portale convergente, portale di sicurezza, portale di sicurezza, portale di sicurezza defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4ea8c5a07016d3fe875d60501acee2cd46481489
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165730"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Fornire l'accesso msSP (Managed Security Service Provider) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Si applica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Per implementare una soluzione di accesso delegato multi-tenant, eseguire la procedura seguente:

1. Abilitare [il controllo dell'accesso](/windows/security/threat-protection/microsoft-defender-atp/rbac) basato sui ruoli in Defender for Endpoint nel Centro sicurezza Microsoft 365 e connettersi ai gruppi di Azure Active Directory (Azure AD).

2. Configurare i [pacchetti di accesso di](/azure/active-directory/governance/identity-governance-overview) governance per la richiesta di accesso e il provisioning.

3. Gestire le richieste di accesso e i controlli in [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Abilitare i controlli di accesso basati sui ruoli in Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365

1. **Creare gruppi di accesso per le risorse MSSP in Customer AAD: Gruppi**

    Questi gruppi verranno collegati ai ruoli creati in Defender for Endpoint nel Centro sicurezza Microsoft 365. A tale scopo, nel tenant AD del cliente creare tre gruppi. Nell'approccio di esempio vengono creati i gruppi seguenti:

    - Analista di livello 1 
    - Analista di livello 2 
    - Responsabili approvazione analista MSSP  


2. Creare ruoli defender per endpoint per livelli di accesso appropriati in Customer Defender for Endpoint nei ruoli e nei gruppi del Centro sicurezza Microsoft 365.

    Per abilitare RBAC nel Centro sicurezza Microsoft 365 del cliente, accedere a Autorizzazioni **> Endpoints** ruoli & gruppi > Ruoli con un account utente con diritti di amministratore globale o amministratore della sicurezza.

    ![Immagine dell'accesso MSSP](../../media/mssp-access.png)

    Creare quindi ruoli RBAC per soddisfare le esigenze del livello SOC MSSP. Collegare questi ruoli ai gruppi di utenti creati tramite "Gruppi di utenti assegnati".

    Due possibili ruoli:

    - **Analisti di livello 1** <br>
      Eseguire tutte le azioni ad eccezione della risposta in tempo reale e gestire le impostazioni di sicurezza.

    - **Analisti di livello 2** <br>
      Funzionalità di livello 1 con l'aggiunta della [risposta in tempo reale](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Per ulteriori informazioni, vedere [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).



## <a name="configure-governance-access-packages"></a>Configurare i pacchetti di accesso alla governance

1.  **Aggiungere MSSP come organizzazione connessa in Customer AAD: Identity Governance**
    
    L'aggiunta di MSSP come organizzazione connessa consentirà al provider mssp di richiedere e disporre degli accessi di cui è stato eseguito il provisioning. 

    A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Connected organization. Aggiungere una nuova organizzazione e cercare il tenant dell'analista MSSP tramite l'ID tenant o il dominio. Ti consigliamo di creare un tenant AD separato per gli analisti MSSP.

2. **Creare un catalogo delle risorse in Customer AAD: Identity Governance**

    I cataloghi delle risorse sono una raccolta logica di pacchetti di accesso, creati nel tenant AD del cliente.

    A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Catalogs e aggiungere **New Catalog.** In questo esempio, verrà chiamato **MSSP Accesses**. 

    ![Immagine del nuovo catalogo](../../media/goverance-catalog.png)

    Per ulteriori informazioni, vedere [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).


3. **Creare pacchetti di accesso per le risorse MSSP Customer AAD: Identity Governance**

    I pacchetti di accesso sono la raccolta di diritti e accessi a cui un richiedente verrà concesso all'approvazione. 

    A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Access Packages e aggiungere **New Access Package.** Creare un pacchetto di accesso per i responsabili approvazione MSSP e ogni livello di analista. Ad esempio, la configurazione dell'analista di livello 1 seguente crea un pacchetto di accesso che:

    - Richiede a un membro del gruppo AD **Responsabili approvazione analisti MSSP** di autorizzare nuove richieste
    - Ha revisioni di accesso annuali, in cui gli analisti SOC possono richiedere un'estensione di accesso
    - Può essere richiesto solo dagli utenti nel tenant SOC MSSP
    - Access scade automaticamente dopo 365 giorni

    ![Immagine del nuovo pacchetto di accesso](../../media/new-access-package.png)

    Per ulteriori informazioni, vedere [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Fornire il collegamento della richiesta di accesso alle risorse MSSP da Customer AAD: Identity Governance**

    Il collegamento al portale My Access viene utilizzato dagli analisti SOC di MSSP per richiedere l'accesso tramite i pacchetti di accesso creati. Il collegamento è durevole, ovvero lo stesso collegamento può essere utilizzato nel tempo per i nuovi analisti. La richiesta dell'analista viene inviata in una coda per l'approvazione da parte dei responsabili approvazione degli analisti **MSSP.**


    ![Immagine delle proprietà di accesso](../../media/access-properties.png)

    Il collegamento si trova nella pagina di panoramica di ogni pacchetto di accesso.

## <a name="manage-access"></a>Gestire accessi 

1. Esaminare e autorizzare le richieste di accesso in Customer e/o MSSP myaccess.

    Le richieste di accesso vengono gestite nel cliente Accesso personale dai membri del gruppo Responsabili approvazione analista MSSP.

    A tale scopo, accedere all'account myaccess del cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Esempio:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Approvare o rifiutare le richieste nella **sezione Approvazioni** dell'interfaccia utente.

     A questo punto, è stato effettuato il provisioning dell'accesso dell'analista e ogni analista deve essere in grado di accedere al Centro sicurezza Microsoft 365 del cliente: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` con le autorizzazioni e i ruoli a cui sono stati assegnati.

> [!IMPORTANT]
> L'accesso delegato a Microsoft Defender for Endpoint nel Centro sicurezza Microsoft 365 attualmente consente l'accesso a un singolo tenant per finestra del browser.