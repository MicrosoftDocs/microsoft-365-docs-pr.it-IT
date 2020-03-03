---
title: Attivazione o disattivazione di App integrate
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Vengono fornite informazioni sulle app integrate e su come attivarle per consentire alle app di terze parti di accedere ai dati di Office 365 degli utenti.
ms.openlocfilehash: 3c7c92e16b375fc374563e87ea2f6166c7384a29
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361387"
---
# <a name="turning-integrated-apps-on-or-off"></a>Attivazione o disattivazione di App integrate

Se l'opzione App integrate è attivata, gli utenti dell'organizzazione possono consentire l'accesso di app di terze parti alle loro informazioni di Office 365. Un'eventuale app di terze parti usata da qualcuno potrebbe ad esempio chiedere l'autorizzazione per accedere al calendario e per modificare i file contenuti in una cartella di OneDrive di questa persona.

## <a name="turning-integrated-apps-on-or-off"></a>Attivazione o disattivazione di App integrate
<a name="__toc379982114"> </a>

Ecco come attivare o disattivare App integrate.

1. Nell'interfaccia di amministrazione, andare alla pagina dei [componenti &amp; aggiuntivi dei servizi](https://go.microsoft.com/fwlink/p/?linkid=2053743) di **Impostazioni** \> e quindi selezionare **app integrate**.

2. Nella pagina **app integrate** , selezionare l'opzione per abilitare o disabilitare le app integrate.

## <a name="more-info-on-integrated-apps"></a>Altre informazioni sulle app integrate
<a name="__toc379982114"> </a>

Le app integrate possono essere create nell'organizzazione oppure provenire da un'altra organizzazione di Office 365 o da una terza parte.

Se l'opzione App integrate è attivata, le eventuali app che vengono usate chiedono l'autorizzazione per impostare il livello di accesso necessario per accedere alle informazioni dell'utente. Ogni utente può concedere l'accesso solo alle app di cui è proprietario e che accedono alle proprie informazioni di Office 365. Non può invece concedere l'accesso alle informazioni degli altri utenti.

Con App integrate di Office 365 vengono usati due tipi di autorizzazione, ossia le autorizzazioni utente e le autorizzazioni di amministratore. Se ad esempio le app integrate sono abilitate per l'organizzazione e un utente usa un'app di terze parti, quest'ultima può chiedere l'autorizzazione dell'utente per leggere i dettagli del suo profilo, modificare o eliminare file, leggere gli elementi contenuti nelle raccolte siti e inviare messaggi di posta elettronica a nome dell'utente.

![Autorizzazioni utente per App integrate](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

Se un amministratore registra un'app per tutti gli utenti di un'organizzazione, gli viene chiesto l'autorizzazione per consentire all'app di accedere alle informazioni e alle risorse nell'organizzazione. Quando in seguito altri utenti dell'organizzazione useranno l'app, non visualizzeranno la richiesta di autorizzazione. L'amministratore che registra un'app deve verificare l'attendibilità di chi la pubblica. Per informazioni sulla registrazione di app, vedere [Aggiunta, aggiornamento e rimozione di applicazioni](https://go.microsoft.com/fwlink/p/?LinkID=518600).

![Autorizzazioni dell'amministratore per App integrate](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

Se l'opzione App integrate viene disattivata, le app già installate e con l'autorizzazione per accedere alle informazioni non verranno disinstallate e le autorizzazioni non verranno rimosse. Anche se questa opzione è disattivata, gli amministratori possono comunque registrare app per renderle disponibili agli utenti e consentire l'accesso alle informazioni. Per informazioni sulla rimozione di un'applicazione registrata e delle relative autorizzazioni, vedere [Aggiunta, aggiornamento e rimozione di applicazioni](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).


