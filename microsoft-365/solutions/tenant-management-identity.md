---
title: 'Passaggio 3: Identità per i tenant di Microsoft 365 per le aziende'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Distribuire il modello di identità corretto per i tenant di Microsoft 365 e applicare l'accesso utente sicuro.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908560"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 3. Identità per i tenant di Microsoft 365 per le aziende

Il tenant di Microsoft 365 include un tenant di Azure Active Directory (Azure AD) per gestire le identità e l'autenticazione per gli accesso. Configurare correttamente l'infrastruttura di gestione delle identità è fondamentale per gestire l'accesso utente e le autorizzazioni di Microsoft 365 per l'organizzazione.

## <a name="cloud-only-vs-hybrid"></a>Solo cloud e ibrido

Ecco i due tipi di modelli di identità e la loro migliore idoneità e vantaggi.


| Modello | Descrizione | Autenticazione delle credenziali utente in Microsoft 365 | Indicato per | Principale vantaggio |
|:-------|:-----|:-----|:-----|:-----|
| Solo cloud | L'account utente esiste solo nel tenant di Azure AD per il tenant di Microsoft 365. | Il tenant di Azure AD per il tenant di Microsoft 365 esegue l'autenticazione con l'account dell'identità cloud. | Organizzazioni che non hanno o necessitano di un'istanza locale di AD DS. | Semplice da usare. Non richiede altri strumenti o server di directory. |
| Ibrido |  L'account utente esiste in Servizi di dominio Active Directory locale e una copia è presente anche nel tenant di Azure AD per il tenant di Microsoft 365. Azure AD Connect viene eseguito in un server locale per sincronizzare le modifiche di Servizi di dominio Active Directory con il tenant di Azure AD. L'account utente in Azure AD potrebbe anche includere una versione con hash della password dell'account utente di Servizi di dominio Active Directory già con hash. | Il tenant di Azure AD per il tenant di Microsoft 365 gestisce il processo di autenticazione o reindirizza l'utente a un altro provider di identità. | Organizzazioni che usano AD DS o un altro provider di identità. | Gli utenti possono usare le stesse credenziali per accedere a risorse locali o basate sul cloud. |
||||||

Ecco i componenti di base dell'identità solo cloud.
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

In questa illustrazione, gli utenti locali e remoti a questo scopo a questo scopo attuino l'accesso con gli account nel tenant di Azure AD del tenant di Microsoft 365.

Ecco i componenti di base dell'identità ibrida.

![Componenti di base dell'identità ibrida](../media/about-microsoft-365-identity/hybrid-identity.png)

In questa illustrazione, gli utenti locali e remoti a tale tenant a cui si accede con gli account nel tenant di Azure AD che sono stati copiati da Servizi di dominio Active Directory locale.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Sincronizzazione di Servizi di dominio Active Directory locale

A seconda delle esigenze aziendali e dei requisiti tecnici, il modello di identità ibrido e la sincronizzazione della directory sono la scelta più comune per i clienti aziendali che adottano Microsoft 365. La sincronizzazione della directory consente di gestire le identità in Servizi di dominio Active Directory e tutti gli aggiornamenti ad account utente, gruppi e contatti vengono sincronizzati con il tenant di Azure AD del tenant di Microsoft 365.

>[!Note]
>Quando gli account utente di Servizi di dominio Active Directory vengono sincronizzati per la prima volta, non vengono assegnati automaticamente a una licenza di Microsoft 365 e non possono accedere ai servizi di Microsoft 365, ad esempio la posta elettronica. È innanzitutto necessario assegnare loro una posizione di utilizzo. Assegnare quindi una licenza a questi account utente, singolarmente o dinamicamente tramite l'appartenenza ai gruppi.
>

Ecco i due tipi di autenticazione quando si utilizza il modello di identità ibrido.

| Tipo di autenticazione | Descrizione |
|:-------|:-----|
| Autenticazione gestita | Azure AD gestisce il processo di autenticazione usando una versione con hash archiviata localmente della password o invia le credenziali a un agente software locale per essere autenticato da Servizi di dominio Active Directory locale. <br> <br>  Esistono due tipi di autenticazione gestita: la sincronizzazione dell'hash delle password (PHS) e l'autenticazione pass-through (PTA). Con PHS, Azure AD esegue l'autenticazione stessa. Con PTA, Azure AD dispone di SERVIZI di dominio Active Directory che esegue l'autenticazione. |
| Autenticazione federata | Azure AD reindirizza il computer client che richiede l'autenticazione a un altro provider di identità. |
|  |  |

Vedi [la scelta del metodo di autenticazione appropriato](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) per altre informazioni.

## <a name="enforcing-strong-sign-ins"></a>Applicazione di accesso sicuro

Per aumentare la sicurezza degli account di accesso degli utenti, utilizzare le caratteristiche e le funzionalità elencate nella tabella seguente.

| Funzionalità | Descrizione | Ulteriori informazioni | Requisiti per la licenza |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello for Business | Sostituisce le password con l'autenticazione avanzata a due fattori quando si accede a un dispositivo Windows. I due fattori sono un nuovo tipo di credenziale utente che è associato a un dispositivo e a una biometria o a un PIN. | [Panoramica di Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 o E5 |
| Protezione delle password di Azure AD | Rileva e blocca le password deboli note e le relative varianti e può anche bloccare ulteriori termini deboli specifici dell'organizzazione. | [Configurare la protezione con password di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 o E5 |
| Usare l'autenticazione a più fattori | L'autenticazione a più fattori richiede che gli utenti siano soggetti a una verifica aggiuntiva oltre alla password dell'account utente, ad esempio la verifica con un'app per smartphone o un SMS inviato a uno smartphone. Vedi [questo video per](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) istruzioni su come gli utenti configurano l'autenticazione a più fattori. | [MFA per Microsoft 365 per le aziende](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 o E5 |
| Configurazioni di identità e accesso dei dispositivi | Impostazioni e criteri costituiti da funzionalità prerequisiti consigliate e dalle relative impostazioni combinate con l'accesso condizionale, Intune e i criteri di Azure AD Identity Protection che determinano se una determinata richiesta di accesso deve essere concessa e in quali condizioni.  | [Configurazioni di identità e accesso dei dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 o E5 |
| Azure AD Identity Protection | Proteggersi dalla compromissione delle credenziali, in cui un utente malintenzionato determina il nome account e la password di un utente per ottenere l'accesso ai servizi cloud e ai dati di un'organizzazione. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection |
|  |  |  |



## <a name="results-of-step-3"></a>Risultati del Passaggio 3

Per l'identità del tenant di Microsoft 365, è stato determinato:

- Modello di identità da utilizzare.
- Come imporre l'accesso sicuro a utenti e dispositivi.

Ecco un esempio di tenant con i nuovi elementi di identità ibrida evidenziati.

![Esempio di identità ibrida per un tenant](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

In questa figura, il tenant ha:

- Una foresta di Servizi di dominio Active Directory sincronizzata con il tenant di Azure AD tramite un server DirSync e Azure AD Connect.
- Una copia degli account utente di Servizi di dominio Active Directory e di altri oggetti della foresta di Servizi di dominio Active Directory.
- Un set di criteri di accesso condizionale per applicare accessi e accessi protetti in base all'account utente. 

## <a name="ongoing-maintenance-for-identity"></a>Manutenzione continua per l'identità

Su base continuativa, potrebbe essere necessario:

- Aggiungere o modificare account utente e gruppi. Per l'identità solo cloud, gli utenti e i gruppi basati sul cloud vengono mantenuti con strumenti di Azure AD come l'interfaccia di amministrazione di Microsoft 365 o PowerShell. Per l'identità ibrida, gli utenti e i gruppi locali vengono mantenuti con gli strumenti di Servizi di dominio Active Directory.
- Aggiungere o modificare la configurazione dell'identità e dell'accesso al dispositivo per applicare i requisiti di sicurezza per l'accesso.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 4. Eseguire la migrazione dei server e dei dati di Office locali](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Continuare con [la](tenant-management-migration.md) migrazione per eseguire la migrazione dei server Di Office locali e dei relativi dati a Microsoft 365.
