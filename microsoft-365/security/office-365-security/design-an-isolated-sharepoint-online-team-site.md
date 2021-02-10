---
title: Progettare un sito del team di SharePoint Online isolato
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Progettare siti del team di SharePoint Online isolati, inclusi determinare i livelli di autorizzazione, assegnare autorizzazioni agli utenti con gruppi di accesso e gruppi di Azure AD annidati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165512"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Progettare un sito del team di SharePoint Online isolato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.

In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione

Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:

- \<site name> Membri

- \<site name> Visitatori

- \<site name> Proprietari

Questi gruppi sono separati dai gruppi di Microsoft 365 e Azure Active Directory (AD) e sono la base per l'assegnazione delle autorizzazioni per le risorse del sito.

Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:

****

|Gruppo di SharePoint|Livello di autorizzazione|
|---|---|
|\<site name> Membri|Modifica|
|\<site name> Visitatori|Lettura|
|\<site name> Proprietari|Controllo completo|
|

 **Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.

Ecco i gruppi e i livelli di autorizzazione di SharePoint predefiniti.

![I gruppi e i livelli di autorizzazione di SharePoint predefiniti per un sito di SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso

È possibile assegnare autorizzazioni agli utenti aggiungendo il proprio account utente o un gruppo di Microsoft 365 o Azure AD di cui l'account utente è membro, ai gruppi di SharePoint. Dopo l'aggiunta, agli account utente, direttamente o indirettamente tramite l'appartenenza a un gruppo di Microsoft 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.

Utilizzo di gruppi di SharePoint predefiniti, ad esempio:

- Ai membri del **\<site name> gruppo Membri** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Modifica

- Ai membri del **\<site name> gruppo visitatori** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Lettura

- Ai membri del **\<site name> gruppo proprietari** di SharePoint, che può includere sia account utente che gruppi, viene assegnato il **livello di** autorizzazione Controllo completo

 **Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.

I gruppi di Azure AD per Microsoft 365 sono gruppi diversi di Microsoft 365. I gruppi di Azure AD vengono visualizzati nell'interfaccia  di amministrazione di Microsoft 365 con il tipo impostato su Sicurezza e non hanno un indirizzo di posta elettronica.  I gruppi di Azure AD possono essere gestiti all'interno di:

- Servizi di dominio Active Directory (AD DS)

    Si tratta di gruppi che sono stati creati nell'infrastruttura di Servizi di dominio Active Directory locale e sincronizzati con l'abbonamento a Microsoft 365. Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo** stato **Sincronizzato con Active Directory.**

- Office 365

    Si tratta di gruppi creati tramite l'interfaccia di amministrazione di Microsoft 365, il portale di Azure o Microsoft PowerShell. Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno lo **stato** **Cloud.**

 **Procedura consigliata:** Se si usa Servizi di dominio Active Directory in locale e si esegue la sincronizzazione con l'abbonamento a Microsoft 365, eseguire la gestione di utenti e gruppi con Servizi di dominio Active Directory.

Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:

****

|Gruppo di SharePoint|Gruppo di accesso basato su Azure AD|Livello di autorizzazione|
|---|---|---|
|\<site name> Membri|\<site name> Membri|Modifica|
|\<site name> Visitatori|\<site name> Visualizzatori|Lettura|
|\<site name> Proprietari|\<site name> Amministratori|Controllo completo|
|

 **Procedura consigliata:** Anche se è possibile usare i gruppi di Microsoft 365 o Azure AD come membri dei gruppi di SharePoint, è consigliabile usare i gruppi di Azure AD. I gruppi di Azure AD, gestiti tramite Servizi di dominio Active Directory o Microsoft 365, offrono una maggiore flessibilità nell'uso dei gruppi annidati per assegnare le autorizzazioni.

Ecco i gruppi di SharePoint predefiniti configurati per l'uso dei gruppi di accesso basati su Azure AD.

![Utilizzo dei gruppi di accesso come membri dei gruppi del sito di SharePoint Online predefiniti.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:

- Nel gruppo di accesso **\<site name> Admins** dovrebbero essere presenti solo alcuni membri, corrispondenti a un numero limitato di amministratori di SharePoint Online che gestiscono il sito del team.

- La maggior parte dei membri del sito è in gruppi **\<site name> di** **\<site name> accesso** Membri o Visualizzatori. Poiché i membri del gruppo **\<site name> di** accesso Membri hanno la possibilità di eliminare o modificare le risorse nel sito, valutare attentamente l'appartenenza. In caso di dubbi, aggiungere il membro del sito al gruppo di accesso **\<site name> Visualizzatori.**

Ecco un esempio dei gruppi di SharePoint e dei gruppi di accesso per un sito isolato denominato ProjectX.

![Esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: usare gruppi di Azure AD annidati

Per un progetto con un numero limitato di persone, un singolo livello di gruppi di accesso basati su Azure AD aggiunti ai gruppi di SharePoint del sito si adatterà alla maggior parte degli scenari. Tuttavia, se si dispone di un numero elevato di persone e tali persone sono già membri di gruppi di Azure AD stabiliti, è possibile assegnare più facilmente le autorizzazioni di SharePoint utilizzando gruppi nidificati o gruppi che contengono altri gruppi come membri.

Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.

 Se si condivide un abbonamento a Microsoft 365 tra più organizzazioni, un singolo livello di appartenenza a un gruppo per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del numero elevato di account utente. In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.

Per utilizzare i gruppi di Azure AD nidificati:

1. Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.

2. Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.

3.  Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.

> [!NOTE]
> Non è possibile usare gruppi di Microsoft 365 annidati.

Ecco un esempio di gruppi di Azure AD annidati per il gruppo di accesso ai membri di ProjectX.

![Esempio di utilizzo di gruppi di accesso annidati per il gruppo di accesso dei membri per il sito ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Poiché tutti gli account utente nei team di ricerca, progettazione e project lead sono destinati a essere membri del sito, è più semplice aggiungere i gruppi di Azure AD al gruppo di accesso Membri di ProjectX.

## <a name="next-step"></a>Passaggio successivo

Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)

[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)
