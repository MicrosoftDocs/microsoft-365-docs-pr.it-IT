---
title: Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base
f1.keywords:
- NOCSH
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Usa Dispositivi mobili e sicurezza di base per creare criteri per i dispositivi che proteggono le informazioni dell'organizzazione.
ms.openlocfilehash: f31930f1a753259622520e50da8c255e7cd410e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904289"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base

È possibile usare Dispositivi mobili e sicurezza di base per creare criteri per i dispositivi che consentono di proteggere le informazioni dell'organizzazione in Microsoft 365 da accessi non autorizzati. Puoi applicare criteri a qualsiasi dispositivo mobile dell'organizzazione in cui l'utente del dispositivo ha una licenza di Microsoft 365 applicabile e ha registrato il dispositivo in Dispositivi mobili e sicurezza di base.

## <a name="before-you-begin"></a>Prima di iniziare

> [!IMPORTANT]
> Prima di poter creare criteri per dispositivi mobili, devi attivare e configurare Dispositivi mobili e sicurezza di base. Per altre info, vedi Panoramica della mobilità e della sicurezza di base.

- Informazioni sui dispositivi, le app per dispositivi mobili e le impostazioni di sicurezza supportate da Dispositivi mobili e sicurezza di base. Vedi [Funzionalità della mobilità e della sicurezza di base.](capabilities.md)
- Creare gruppi di sicurezza che includano gli utenti di Microsoft 365 a cui si desidera distribuire i criteri e per gli utenti che si desidera escludere dall'accesso a Microsoft 365. Prima di distribuire un nuovo criterio per l'organizzazione verifica i criteri distribuendoli a un numero limitato di utenti. È possibile creare e usare un gruppo di sicurezza che include solo se stessi o un numero limitato di utenti di Microsoft 365 che possono testare il criterio automaticamente. Per ulteriori informazioni sui gruppi di sicurezza, vedere [Creare, modificare o eliminare un gruppo di sicurezza.](../email/create-edit-or-delete-a-security-group.md)
- Per creare e distribuire i criteri di sicurezza e mobilità di base in Microsoft 365, è necessario essere un amministratore globale di Microsoft 365. Per altre info, vedi [Autorizzazioni nel Centro sicurezza & conformità.](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)
- Prima di distribuire i criteri, consenti all'organizzazione di conoscere i potenziali effetti della registrazione di un dispositivo in Dispositivi mobili e sicurezza di base. A seconda di come si configurano i criteri, ai dispositivi non conformi può essere impedito l'accesso a Microsoft 365 e ai dati, incluse le applicazioni installate, le foto e le informazioni personali in un dispositivo registrato, e i dati possono essere eliminati.

>[!NOTE]
>I criteri e le regole di accesso creati in Basic Mobility and Security for Microsoft 365 Business Standard sostituiscono Exchange ActiveSync criteri cassetta postale dei dispositivi mobili e regole di accesso ai dispositivi creati nell'interfaccia di amministrazione di Exchange. Dopo la registrazione di un dispositivo Exchange ActiveSync Basic Mobility and Security for Microsoft 365 Business Standard, qualsiasi criterio cassetta postale del dispositivo mobile o regola di accesso al dispositivo applicata al dispositivo viene ignorato. Per ulteriori informazioni sulle Exchange ActiveSync, [vedere Exchange ActiveSync in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Passaggio 1: Creare un criterio dispositivo e distribuirne uno in un gruppo di test

Prima di iniziare, assicurati di aver attivato e configurato Basic Mobility and Security. Per istruzioni, vedere [Overview of Basic Mobility and Security.](overview.md)

1. Nel browser digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selezionare **Crea un criterio.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni dei criteri di base per dispositivi mobili e sicurezza":::

3. Nella pagina **Impostazioni criteri** specificare i requisiti che si desidera applicare ai dispositivi mobili dell'organizzazione.

4. **Richiedi gestione del profilo di** posta elettronica: se abilitati, i dispositivi che non dispongono di un profilo di posta elettronica gestito da Dispositivi mobili e sicurezza di base sono considerati non conformi. Un dispositivo non può avere un profilo di posta elettronica gestito quando non è destinato correttamente o se l'utente ha configurato manualmente l'account di posta elettronica nel dispositivo. Quando si lascia Non **abilitato** (impostazione predefinita), questa impostazione non viene valutata per la conformità o la non conformità. Per istruzioni su come gli utenti possono essere conformi quando questa opzione è selezionata, vedere È stato trovato un [account di posta elettronica esistente.](/intune-user-help/existing-company-email-account-found)

5. Nella pagina **Applicare questo criterio ora?** scegliere i gruppi a cui si desidera applicare il criterio.

6. Selezionare **Crea questo criterio.**

Il criterio viene inserito nel dispositivo di ogni utente e applicato al successivo accesso a Microsoft 365 con il dispositivo mobile. Se prima gli utenti non hanno applicato un criterio al dispositivo mobile, dopo aver distribuito il criterio, ottengono una notifica sul dispositivo che include i passaggi per registrare e attivare Dispositivi mobili e sicurezza di base. Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md) Finché non completano la registrazione in Dispositivi mobili di base e sicurezza ospitati dal servizio Intune, l'accesso alla posta elettronica, OneDrive e altri servizi è limitato. Dopo aver completato la registrazione usando l'app Portale aziendale intune, possono usare i servizi e i criteri vengono applicati al dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Passaggio 2: verificare che i criteri funzionino

Dopo aver creato un criterio dispositivo, verifica che il criterio funzioni come previsto prima di distribuirlo nell'organizzazione.

1. Nel browser digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleziona **Visualizza l'elenco dei dispositivi gestiti.**
3. Verifica lo stato dei dispositivi dell'utente a cui sono stati applicati i criteri. Vuoi che **lo stato** dei dispositivi sia **gestito.**
4. Puoi anche eseguire una cancellazione completa o selettiva su un dispositivo facendo clic su **Reimpostazione** in fabbrica o Rimuovi i dati **aziendali** dal pulsante **Gestisci** dopo aver selezionato un dispositivo. Per istruzioni, vedere [Cancellare un dispositivo mobile in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Passaggio 3: Distribuire un criterio nell'organizzazione

Dopo aver creato un criterio dispositivo e verificato che funzioni come previsto, distribuirlo all'organizzazione.

1. Dal tipo di browser: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selezionare il criterio che si desidera distribuire e scegliere **Modifica** accanto a **Gruppi applicati a.**
3. Cerca un gruppo da aggiungere e fai clic su **Seleziona.**
4. Selezionare **Chiudi** e **modifica impostazione.**
5. Selezionare **Chiudi** e **Modifica criterio.**

Il criterio viene inserito nel dispositivo mobile di ogni utente. Il criterio si applica al successivo accesso a Microsoft 365 dal dispositivo mobile. Se gli utenti non hanno applicato un criterio al dispositivo mobile, ottengono una notifica sul dispositivo con la procedura per registrarlo e attivarlo per dispositivi mobili e sicurezza di base. Dopo aver completato la registrazione, il criterio viene applicato al dispositivo. Per altre info, vedi [Registrare il dispositivo mobile usando Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Passaggio 4: Bloccare l'accesso alla posta elettronica per i dispositivi non supportati

Per proteggere le informazioni dell'organizzazione, è consigliabile bloccare l'accesso dell'app alla posta elettronica di Microsoft 365 per i dispositivi mobili non supportati da Dispositivi mobili e sicurezza di base. Per un elenco dei dispositivi supportati, vedi [Dispositivi supportati.](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)

**Per bloccare l'accesso alle app:**

1. Nel browser digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selezionare **Gestisci impostazioni di accesso ai dispositivi a livello di organizzazione.**
3. Per bloccare i dispositivi non supportati, scegliere Blocca **in** Se un dispositivo non è supportato da Dispositivi mobili e sicurezza di base per **Microsoft 365** e quindi selezionare **Salva.**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opzione di accesso di base per dispositivi mobili e sicurezza":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Passaggio 5: Scegliere i gruppi di sicurezza da escludere dai controlli dell'accesso condizionale

Se si desidera escludere alcuni utenti dai controlli dell'accesso condizionale sui relativi dispositivi mobili e sono stati creati uno o più gruppi di sicurezza per tali utenti, è possibile aggiungere qui i gruppi di sicurezza. Per gli utenti di questi gruppi non verranno applicati criteri per i dispositivi mobili supportati. Questa è l'opzione consigliata se non si desidera più utilizzare Dispositivi mobili e sicurezza di base nell'organizzazione.

1. Nel browser digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selezionare **Gestisci impostazioni di accesso ai dispositivi a livello di organizzazione.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Dispositivi mobili e sicurezza di base creano un'opzione di criteri":::

3. Selezionare **Aggiungi** per aggiungere il gruppo di sicurezza con utenti che si desidera escludere dal blocco dell'accesso a Microsoft 365. Quando un utente è stato aggiunto a questo elenco, può accedere alla posta elettronica di Microsoft 365 quando usa un dispositivo non supportato.

4. Seleziona il gruppo di sicurezza che vuoi usare nel **pannello Seleziona gruppo.**

5. Seleziona il nome e quindi Aggiungi  >  **Salva.**

6. Nel pannello **Impostazioni di accesso ai dispositivi** a livello di organizzazione scegliere **Salva.**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Opzione Di base per dispositivi mobili e sicurezza consente l'accesso":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual è l'impatto dei criteri di sicurezza sui diversi tipi di dispositivo?

Quando applici un criterio ai dispositivi degli utenti, l'impatto su ogni dispositivo varia in qualche modo tra i tipi di dispositivi. Vedere la tabella seguente per visualizzare esempi dell'impatto dei criteri su diversi dispositivi.

|**Criterio di sicurezza**|**Android 4 e versioni successive**|**Samsung KNOX**|**iOS 6 e versioni successive**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato|No|Sì|Sì|Backup crittografato iOS necessario.|
|Blocca backup sul cloud|Sì|Sì|Sì|Blocca backup Google su Android (in grigio), backup cloud su IOS.|
|Blocca sincronizzazione documenti|No|No|Sì|iOS: blocca i documenti nel cloud.|
|Blocca sincronizzazione foto |No|No|Sì|iOS (nativo): blocco lo streaming foto.|
|Blocca acquisizione schermata |No|Sì|Sì|Tentativo bloccato.|
|Blocca videoconferenza |No|No|Sì|FaceTime bloccato su iOS, non su Skype o altri.|
|Blocca invio dati di diagnostica |No|Sì|Sì|Blocco invio segnalazione di arresto anomalo di Google su Android.|
|Blocca l'accesso all'app store |No|Sì|Sì|Icona app store mancante nella home page di Android, disattivata in Windows, mancante in IOS.|
|Richiede una password per l'app store |No|No|Sì|iOS: password necessaria per gli acquisti su iTunes.|
|Blocca connessione con archivi rimovibili |No|Sì|N/D|Android: la scheda SD è disattivata nelle impostazioni, Windows avvisa l'utente, le app installate non sono disponibili|
|Blocca connessione Bluetooth |Vedere le note|Vedere le note|Sì|Non è possibile disabilitare BlueTooth come impostazione in Android. Vengono invece disabilitate tutte le transazioni che richiedono BlueTooth: Distribuzione audio avanzata, Controllo remoto audio/video, dispositivi hands-free, auricolare, accesso alla rubrica telefonica e porta seriale. Durante una di queste transazioni, viene visualizzato un piccolo messaggio popup in fondo alla pagina.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Cosa accade quando si elimina un criterio o si rimuove un utente dal criterio?

Quando si elimina un criterio o si rimuove un utente da un gruppo in cui è stato distribuito il criterio, le impostazioni dei criteri, il profilo di posta elettronica di Microsoft 365 e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi dal dispositivo dell'utente. Vedi la tabella seguente per vedere cosa è stato rimosso per i diversi tipi di dispositivi.

|**Elementi rimossi**|**iOS 6 e versioni successive**|**Android 4 e versioni successive (incluso Samsung KNOX**|
|:-----|:-----|:-----|
|Profili di posta elettronica<sup>gestiti 1</sup>|Sì|No|
|Blocca backup sul cloud|Sì|No|

<sup>1</sup> Se il criterio è stato distribuito con l'opzione **Il** profilo di posta elettronica è gestito selezionato, il profilo di posta elettronica gestito e i messaggi di posta elettronica memorizzati nella cache in tale profilo vengono eliminati dal dispositivo utente.

Il criterio viene rimosso dal dispositivo mobile per ogni utente. Il criterio viene applicato alla successiva archiviazione del dispositivo con Dispositivi mobili e sicurezza di base. Se distribuisci un nuovo criterio che si applica a questi dispositivi utente, gli verrà richiesto di registrare di nuovo in Dispositivi mobili e sicurezza di base.

Puoi anche cancellare completamente un dispositivo o cancellare in modo selettivo le informazioni dell'organizzazione dal dispositivo. Per altre info, vedi [Cancellare i dati di un dispositivo mobile in Dispositivi mobili e sicurezza di base.](wipe-mobile-device.md)

## <a name="related-topics"></a>Argomenti correlati

[Panoramica Basic Mobility + Security](overview.md)

[Funzionalità Basic Mobility + Security](capabilities.md)