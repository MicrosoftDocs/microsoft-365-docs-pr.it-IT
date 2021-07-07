---
title: Integrare Microsoft Teams classi con Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrare Microsoft Teams classi con Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314492"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Usare Microsoft Teams classi con Blackboard Learn Ultra

Il lavoro in team è alla base di ogni organizzazione moderna. Promuovendo la collaborazione, è una caratteristica distintiva di ogni istituto di successo. Puoi migliorare tutte le funzionalità e le funzionalità di Blackboard Learn Ultra associandole a Microsoft Teams classi.

Le classi possono includere conversazioni in tempo reale, riunioni video o interazioni asincrone. Puoi aggiungere esperienze di condivisione e creazione di file per gli studenti, tutte in un'unica posizione. Microsoft Teams con Learn Ultra ridefinire le dinamiche dell'insegnamento e il significato dell'apprendimento efficace.

> [!IMPORTANT]
> Assicurarsi di aver configurato correttamente il campo E-mail dell'istituto nel sistema sis (Sis) degli studenti `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`
>
>L'Microsoft Teams delle classi di autenticazione si basa sul campo di posta elettronica dell'istituto nel SIS per eseguire il mapping al nome dell'entità utente (UPN) del Microsoft Azure Active Directory (AAD) corretto. Se non è stato effettuato il provisioning dei messaggi di posta elettronica dell'istituto, per impostazione predefinita verrà utilizzato il messaggio di posta elettronica esistente. È consigliabile impostare questo campo per ogni utente per assicurarsi che i dati siano sincronizzati correttamente e che non vi sia alcun conflitto di dati di posta elettronica tra Microsoft AAD e Blackboard Learn Ultra.
>
> Se questo campo non è stato impostato in modo appropriato nel mapping SIS, l'integrazione continuerà a funzionare, ma gli utenti potrebbero non essere visualizzati nelle classi Teams create e potrebbero verificarsi errori.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>Supporto del mapping dei dati istituzionali - Campo SIS di posta elettronica dell'istituto

Come parte dell'evoluzione con le integrazioni dei provider  cloud, Blackboard Learn Ultra ha creato un nuovo campo e-mail dell'istituto, sia nell'integrazione di Student Information System Framework che nelle API REST pubbliche, consentendo agli istituti di gestire in modo efficace il processo di sincronizzazione dei dati tra Blackboard Learn Ultra e Microsoft AAD.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>Cosa significa e cosa supporta l'e-mail dell'istituto?

Il **campo Institution Email** consente mapping di campi personalizzati tra le origini dati supportate esternamente da un client e Blackboard Learn Ultra. Se le origini dati sono provider cloud, ad esempio Microsoft, l'UPN (User Principle Name) è un identificatore univoco primario per ogni utente costituito da un prefisso UPN (il nome dell'account dell'utente) e da un suffisso UPN (un nome di dominio DNS) uniti a un simbolo @. In questo modo viene creato un indirizzo di posta elettronica univoco per ogni utente specifico all'interno del Microsoft Azure Active Directory.

Per garantire che i dati siano accurati e che le registrazioni o le appartenenze tra le classi Blackboard Learn Ultra e Microsoft Teams vengano ottenute correttamente, l'indirizzo di posta elettronica di un utente deve corrispondere tra entrambi i sistemi. In Blackboard Learn Ultra, gli utenti possono modificare o sostituire l'indirizzo di posta elettronica esistente nell'interfaccia utente, che potrebbe causare errori di sincronizzazione e l'utente non essere aggiunto correttamente a un team di classe. Il mapping del campo **e-mail** dell'istituto garantisce che questo livello di sicurezza e controllo di convalida possa essere gestito correttamente, indipendentemente dal fatto che gli utenti hanno modificato la propria posta elettronica all'interno di Blackboard Learn Ultra o meno.

 Quando due indirizzi di posta elettronica sono diversi:

- È necessario prendere una decisione sull'origine che ha la precedenza e verrà presa sia come messaggio di posta elettronica dell'utente che dell'istituto.
  Oppure
- Un istituto può impostare un mapping di campo personalizzato nel messaggio di posta elettronica dell'istituto, che può risolvere un potenziale conflitto.

Il **mapping del campo e-mail** institution è ora disponibile per tutti i tipi di integrazione SIS esistenti in Advanced Configuration **Impostazioni** Users Learn  >  **Object Type** Field  >  **Mapping**.

> [!NOTE]
> È importante notare che, per impostazione  predefinita, l'e-mail dell'istituto è impostata sull'indirizzo di posta elettronica della persona per tutti i formati SIS e deve essere univoco per ogni persona.  Tutte le integrazioni esistenti che sono state impostate e in esecuzione avranno questo mapping dei dati, in quanto SIS non riuscirà a importare gli utenti se la posta elettronica è duplicata. Se un istituto richiede la possibilità di modificare l'indirizzo di posta elettronica dell'istituto **in** **personalizzato,** dovrà gestire questo problema tramite la configurazione avanzata Impostazioni nel SIS.

## <a name="requirements"></a>Requisiti

L Microsoft Teams di integrazione delle classi di corsi è disponibile solo per i corsi **Di visualizzazione corso Ultra.** L'istituto deve completare questi requisiti per usarlo:

- Avere Blackboard Learn Ultra Learn SaaS con l'opzione Di spostamento di base ultra abilitata

- Abilita LTI per l'uso nei corsi.

  a. Passare al pannello **di amministrazione** Provider di  >  **strumenti LTI** Gestisci proprietà  >  **globali**.

  b. Selezionare **LTI Enabled in Courses** e, facoltativamente, selezionare Enabled in **Organizations**.

  c. Selezionare **Invia**.

- Deve essere configurato LTI

- Aggiungere Blackboard Learn Ultra Teams Classes LTI Integration

- Aggiungere Microsoft Teams classi LTI 1.3 Tool

- Aggiungere lo strumento API REST e condivisione di risorse tra origini

- Configurare e approvare classi Microsoft Teams integrazione

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Aggiungere lo strumento Blackboard Learn Ultra Teams Classes LTI 1.3

1. Nel Pannello **di amministrazione** selezionare Provider di **strumenti LTI.**

2. Selezionare **register LTI 1.3 Tool**.

3. Nel campo **ID client** digitare oppure copiare e incollare questo ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Esaminare tutte le impostazioni pre-popolate e in **Stato strumento** e quindi selezionare **Abilitato.**

5. In **Criteri dell'istituto** selezionare **Ruolo in Corso, Nome** e Indirizzo di posta **elettronica,** quindi selezionare **Sì** per entrambi.

6. Selezionare **Consenti accesso al servizio di livello** e Consenti accesso al servizio di **appartenenza**.

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Aggiungere lo strumento Microsoft Teams Classes LTI 1.3

1. Nel Pannello **di amministrazione** selezionare Provider di **strumenti LTI.**

2. Selezionare **register LTI 1.3 Tool**.

3. Nel campo **ID client** digitare oppure copiare e incollare questo ID:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. Esaminare tutte le impostazioni pre-popolate e in *Stato strumento e* selezionare *Abilitato.*

5. In **Criteri dell'istituto** selezionare **Ruolo in Corso, Nome e** Indirizzo di posta **elettronica.** Selezionare **Sì** per entrambi.

6. Selezionare **Consenti accesso al servizio di livello** e Consenti accesso al servizio di **appartenenza**.

## <a name="add-the-rest-api-tool"></a>Aggiungere lo strumento API REST

1. Nel Pannello **di amministrazione** passa a **Integrazioni e** seleziona **Integrazioni API Rest.**

2. Selezionare **Crea integrazione**.

3. Nel campo **ID applicazione** digitare oppure copiare e incollare questo ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Digitare un utente per questa integrazione.

   Questo utente sarà quello con accesso all'API principale da cui è associata l'applicazione.

5. Selezionare **Invia**.

## <a name="add-the-cross-origin-resource-sharing"></a>Aggiungere la condivisione di risorse tra origini

1. Nel pannello **Amministratore,** accedere a **Integrazioni e** selezionare **Condivisione risorse tra origini*.

2. Selezionare **Crea configurazione**.

3. Nel campo **Origine** digitare copiare e incollare l'URL:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. Nel campo **Intestazioni consentite** digitare **Autorizzazione**.

5. Impostare **Disponibile** su **Sì**.

6. Selezionare **Invia**.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Configurare e approvare le classi Microsoft Teams integrazione

Per integrare correttamente l'istanza di Blackboard Learn Ultra con le classi Microsoft Teams, devi assicurarti che l'applicazione Blackboard Learn Ultra sia approvata per l'accesso all'interno del tenant Microsoft Azure. Si tratta di un processo che dovrà essere completato dall'amministratore globale dell'Microsoft 365 dell'istituto.

Questo processo può essere eseguito prima o dopo aver configurato le applicazioni LTI nella blackboard Learn Ultra Instance.

### <a name="before-configuring-the-lti-applications"></a>Prima di configurare le applicazioni LTI

Se si sceglie di approvare l'app Azure Learn Ultra Teams Classes di Blackboard prima di configurare le integrazioni LTI, sarà necessario reindirizzare all'endpoint di consenso dell'amministratore di **Microsoft Identity Platform.** L'URL viene visualizzato:

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> Devi sostituire **{Tenant} con il** tuo ID tenant Microsoft Azure istituzionale specifico.

### <a name="after-configuring-the-lti-applications"></a>Dopo aver configurato le applicazioni LTI

1. Nel Pannello **di amministrazione,** accedere a **Strumenti e utilità** e selezionare Microsoft Teams Amministratore **integrazione.**

2. Selezionare **Abilita Microsoft Teams**.

3. Aggiungi il **tuo ID tenant Microsoft** nel campo di testo disponibile.

4. Scegliere una delle opzioni seguenti:

   - Se l'app ha il pre-consenso, mostrerà un piccolo segno di spunta. Se viene visualizzato il segno di spunta, selezionare **Invia**.

   - Se il consenso non è stato approvato, seguire la procedura descritta per generare l'URL per il consenso e inviarlo all'amministratore globale Microsoft 365 per l'approvazione.

5. Dopo aver confermato l'approvazione, selezionare **Riprova** per confermare e quindi selezionare **Invia**.
