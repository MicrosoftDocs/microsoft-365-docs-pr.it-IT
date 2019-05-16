---
title: 'Passaggio 1: pianificazione per utenti e gruppi'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Pianificare il set di utenti e gruppi che lavoreranno per l'organizzazione.
ms.openlocfilehash: 1f879c789e6b531dec7163fa252e0f85459c823d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072176"
---
# <a name="step-1-plan-for-users-and-groups"></a>Passaggio 1: pianificazione per utenti e gruppi

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Questo passaggio consente di creare un'infrastruttura di gestione delle identità che combina utenti, gruppi e appartenenza a gruppi con caratteristiche di sicurezza nella configurazione corretta. In questo modo è possibile:

- Mantenere il controllo su chi accede alle risorse nell'ambiente.
- Proteggere l'accesso con i controlli che assicurano delle forti garanzie di identità (gli utenti sono chi dicono di essere) e l'accesso da dispositivi sicuri.
- Effettuare il provisioning delle risorse nell'ambiente con le autorizzazioni adeguate per ridurre i rischi di danni e perdita di dati. 
- Monitorare l'ambiente per individuare comportamenti anomali degli utenti e intervenire automaticamente.

## <a name="plan-your-primary-identity-provider"></a>Pianificare il provider di identità primaria

Per creare l'infrastruttura di gestione delle identità, è necessario designare un provider di identità primaria. Questo servizio consente di archiviare gli account utente e i loro attributi, i gruppi e le loro appartenenze e supporta l'amministrazione in corso.

Quando un'organizzazione utilizza Microsoft 365 Enterprise, il provider di identità primaria può essere:

- **Active Directory Domain Services**, un provider di identità Intranet ospitato su computer che eseguono Windows Server. Questa opzione viene generalmente usata dalle organizzazioni che possiedono un provider di identità locale esistente.
- **Azure Active Directory (Azure AD**), un'identità come servizio (IDaaS) basata sul cloud che offre un'ampia gamma di funzionalità per gestire e proteggere l'ambiente. Questa opzione viene generalmente usata dalle organizzazioni che non dispongono di un'infrastruttura locale esistente.

Se l'organizzazione dispone di un provider di identità locale esistente, non è necessario sincronizzare gli account e i gruppi utente da AD DS ad Azure AD per fornire un accesso più semplice ai servizi basati sul cloud di Microsoft 365 Enterprise. È anche possibile usare Azure AD per creare e gestire gruppi presenti solo nel cloud Microsoft.

Una volta impostati gli utenti e i gruppi in Azure AD, è possibile:

- Gestire tutti gli account di Azure AD per tutte le applicazioni cloud. 
- Utilizzare lo stesso set di controlli per proteggere l'accesso alle applicazioni all'interno dell'ambiente.
- Collaborare con partner esterni.
- Monitorare comportamenti anomali degli account, come per esempio tentativi sospetti di accesso, per poi intervenire automaticamente.

Seguire le istruzioni nelle prossime due sezioni per pianificare e implementare gli account e i gruppi utente.

## <a name="categorize-your-users"></a>Categorizzare gli utenti
Gli utenti nelle organizzazioni possono essere categorizzati in molti modi. Per esempio, alcuni sono dipendenti e hanno un contratto permanente. Altri sono fornitori, terzisti o partner con un contratto temporaneo. Altri ancora sono utenti esterni che non dispongono di un account utente, ma che devono avere un accesso garantito a servizi e risorse specifiche per supportare l'interazione e la collaborazione. Ad esempio:

- Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud
- Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.

È consigliabile tener conto dei tipi di utente dell'organizzazione. Come sono raggruppati? Per esempio, è possibile raggruppare gli utenti in base alle funzioni di alto livello o all'obiettivo dell'organizzazione.

Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>Pianificare i gruppi di Active Directory Domain Services e Azure AD

È possibile utilizzare i gruppi in Azure AD in molteplici modi che semplificano la gestione dell'ambiente cloud. Per esempio, per i gruppi di Azure AD è possibile:

- Usare la licenza basata su gruppo per assegnare automaticamente le licenze per Office 365 ed Enterprise Mobility + Security (EMS) agli account utente appena vengono aggiunti in Azure AD o sincronizzati da Active Directory Domain Services. 
- Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi dell'account utente, come per esempio il reparto.  
- Effettuare automaticamente il provisioning degli utenti per le applicazioni Software as a Service (SaaS) e proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori e altre regole di accesso condizionale.
- Effettuare il provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online. I gruppi di Azure AD possono essere utilizzati anche con i criteri di Azure Information Protection per proteggere i file con crittografia e autorizzazioni. 

## <a name="results"></a>Risultati

Dopo aver completato questo passaggio, si ottiene quanto segue:

- Un elenco degli account utente in Azure AD che corrispondono ai dipendenti dell'organizzazione, a fornitori, terzisti e partner esterni che collaborano con l'organizzazione.
- Un set di gruppi e la loro relativa appartenenza in Azure AD che riflette dei set logici di account utente e altri gruppi per il provisioning automatico delle licenze delle impostazioni di sicurezza per i servizi cloud di Microsoft.

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-user-groups) per questo passaggio.

Dopo avere creato gli utenti e i gruppi di Azure AD, è possibile iniziare ad assegnare le licenze e a usare Exchange Online. Per implementare Exchange Online per gli utenti, vedere [Distribuire Exchange Online per Microsoft 365 Enterprise](exchangeonline-workload.md).

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Proteggere le identità con privilegi](identity-designate-protect-admin-accounts.md) |

