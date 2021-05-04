---
title: Limiti per i criteri di conservazione e i criteri per le etichette di conservazione
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Comprendere il numero massimo di criteri ed elementi per criterio in relazione ai criteri di conservazione e ai criteri per le etichette di conservazione
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107658"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Limiti per i criteri di conservazione e i criteri per le etichette di conservazione

>*[Indicazioni per la sicurezza e conformità dell'assegnazione di licenze Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Quando si utilizzano [criteri di conservazione e criteri per le etichette di conservazione](retention.md#retention-policies-and-retention-labels) per conservare o eliminare automaticamente i dati dell’organizzazione, vi sono alcuni limiti massimi da tenere in considerazione.

## <a name="maximum-number-of-policies-per-tenant"></a>Numero massimo di criteri nel tenant

Un tenant singolo può avere al massimo 10.000 criteri (con qualsiasi configurazione).  Questo numero massimo include i differenti criteri di conservazione e altri criteri di conformità, ad esempio i criteri di prevenzione della perdita dei dati.

Numero massimo di criteri di conservazione per carico di lavoro:

- Exchange Online (con qualsiasi configurazione): 1.800
- SharePoint o OneDrive (tutti i siti inclusi automaticamente): 13
- SharePoint o OneDrive (specifici percorsi inclusi o esclusi): 2.600

## <a name="maximum-number-of-items-per-policy"></a>Numero massimo di elementi per criterio

Se si utilizza la configurazione facoltativa per restringere l'ambito delle impostazioni di conservazione a utenti specifici, gruppi di Microsoft 365 specifici o siti specifici, vi sono alcuni limiti per ciascun criterio da tenere in considerazione: 

Numero massimo di elementi per criterio di conservazione:

  - 1.000 cassette postali (degli utenti o di gruppo)
  - 1.000 gruppi di Microsoft 365
  - 1.000 utenti per le chat private di Teams
  - 100 siti (OneDrive o SharePoint)

Poiché queste limitazioni sono stabilite per criterio, se è necessario usare specifiche inclusioni o esclusioni che determinano un superamento di tali limiti, è possibile creare altri criteri con le stesse impostazioni di conservazione. Vedere la sezione successiva per alcuni[scenari e soluzioni di esempio](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) che usano più criteri di conservazione per tale ragione.

Tuttavia, l’uso di più criteri determina costi amministrativi superiori, perciò occorre verificare sempre se le inclusioni e le esclusioni siano davvero necessarie. Tenere presente che la configurazione predefinita che si applica all'intero percorso non ha alcuna limitazione, e che questa configurazione potrebbe essere una soluzione migliore rispetto alla creazione e alla gestione di più criteri.

> [!TIP]
> Se è necessario creare e gestire più criteri per questo scenario, si consiglia di usare di usare [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) per una configurazione più efficiente.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Esempi di utilizzo di più criteri per evitare il superamento dei limiti massimi

Gli esempi seguenti forniscono alcune soluzioni per i casi in cui non è possibile specificare semplicemente il percorso di un criterio di conservazione ed è necessario tenere in considerazione il numero massimo di elementi indicato nella sezione precedente.

Esempio di Exchange:

- **Requisito**: in una organizzazione che ha più di 40.000 cassette postali degli utenti, la posta elettronica deve essere conservata per sette anni per gran parte degli utenti, ma un sottoinsieme di utenti identificati (425) deve conservare la posta elettronica solo per 5 anni. 

- **Soluzione**: creare un criterio di conservazione per la posta elettronica di Exchange con un periodo di conservazione di sette anni, ed escludere il sottoinsieme di utenti. Creare poi un secondo criterio di conservazione per la posta elettronica di Exchange, con un periodo di conservazione di cinque anni, e includere il sottoinsieme di utenti. 
    
    In entrambi casi, il numero incluso ed escluso è inferiore a un numero massimo di cassette postali specificate per un singolo criterio, e il sottoinsieme di utenti deve essere escluso esplicitamente dalla primo criterio perché ha [periodo di conservazione più lungo](retention.md#the-principles-of-retention-or-what-takes-precedence) del secondo criterio. Se il sottoinsieme di utenti richiede un periodo di conservazione più lungo, non è necessario escluderli dal primo criterio.
     
    Con questa soluzione, se un nuovo dipendente entra nell'organizzazione, la sua cassetta postale viene automaticamente inclusa nel primo criterio per sette anni, e non ci sono conseguenze per il numero massimo supportato. Tuttavia, i nuovi utenti che richiedono il periodo di conservazione di 5 anni si sommano ai numeri da includere ed escludere e questo limite viene raggiunto a 1.000.

Esempio di SharePoint:

- **Requisito**: l'organizzazione ha diverse migliaia di siti di SharePoint, ma soltanto 2000 siti richiedono un periodo di conservazione da 10 anni, e 8000 siti richiedono un periodo di conservazione da quattro anni.

- **Soluzione**: creare 20 criteri di conservazione per SharePoint con un periodo di conservazione da 10 anni che includa 100 siti specifici, e creare 80 criteri di conservazione per SharePoint con un periodo di conservazione da quattro anni che includa 100 siti specifici.
    
    Poiché non è necessario conservare tutti i siti di SharePoint, bisogna creare criteri di conservazione che specificano i siti. Dato che i criteri di conservazione non supportano più di 100 siti specifici, è necessario creare criteri specifici per i due periodi di conservazione. Questo criterio di conservazione hanno il numero massimo di siti inclusi, perciò un nuovo criterio di conservazione deve essere creato per il prossimo nuovo sito che richiede la conservazione, indipendentemente dal periodo di conservazione.