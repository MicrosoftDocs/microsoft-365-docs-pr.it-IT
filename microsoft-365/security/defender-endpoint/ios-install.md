---
title: Distribuzione basata su app per Microsoft Defender for Endpoint in iOS
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender for Endpoint in iOS usando un'app
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installazione, distribuzione, disinstallazione, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f2b9a1365a27bb7397aea51dcd5bc9e2631afe2
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624706"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>Distribuire Microsoft Defender per Endpoint in iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Questo argomento descrive la distribuzione di Defender for Endpoint in iOS Portale aziendale Intune dispositivi registrati. Per altre informazioni sulla registrazione dei dispositivi Intune, vedi Registrare dispositivi [iOS/iPadOS in Intune.](/mem/intune/enrollment/ios-enroll)

## <a name="before-you-begin"></a>Prima di iniziare

- Assicurati di avere accesso [all'interfaccia di amministrazione di Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

- Verificare che la registrazione iOS sia stata eseguita per gli utenti. Gli utenti devono disporre di una licenza defender per endpoint assegnata per poter usare Defender per Endpoint in iOS. Per istruzioni [su come assegnare licenze, vedere](/azure/active-directory/users-groups-roles/licensing-groups-assign) Assegnare licenze agli utenti.

> [!NOTE]
> Microsoft Defender per Endpoint su iOS è ora disponibile [nell'App Store di Apple.](https://aka.ms/mdatpiosappstore)

## <a name="deployment-steps"></a>Fasi di distribuzione

Distribuire Defender per Endpoint in iOS tramite Portale aziendale Intune.

### <a name="add-ios-store-app"></a>Aggiungere l'app di iOS Store

1. [Nell'interfaccia di amministrazione di Microsoft Endpoint manager](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **App**  ->  **iOS/iPadOS**  ->  **Aggiungi**  ->  **app dello Store iOS** e fai clic su **Seleziona.**

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)

1. Nella pagina Aggiungi app fai clic su **Cerca nell'App Store** e digita **Microsoft Defender Endpoint** nella barra di ricerca. Nella sezione dei risultati della ricerca fai clic su *Microsoft Defender Endpoint* e fai clic su **Seleziona.**

1. Seleziona **iOS 11.0** come sistema operativo minimo. Esamina le altre informazioni sull'app e fai clic su **Avanti.**

1. Nella sezione *Assegnazioni* passare alla sezione **Obbligatorio** e selezionare **Aggiungi gruppo.** Puoi quindi scegliere i gruppi di utenti che vuoi usare come destinazione di Defender per Endpoint nell'app iOS. Fare **clic su** Seleziona e quindi su **Avanti.**

    > [!NOTE]
    > Il gruppo di utenti selezionato deve essere costituito da utenti registrati in Intune.

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)

1. Nella sezione *Revisione e creazione* verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**. In pochi istanti, l'app Defender for Endpoint dovrebbe essere creata correttamente e dovrebbe essere visualizzata una notifica nell'angolo in alto a destra della pagina.

1. Nella pagina delle informazioni sull'app visualizzata, nella sezione **Monitor** seleziona **Stato** installazione dispositivo per verificare che l'installazione del dispositivo sia stata completata correttamente.

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>Onboarding automatico del profilo VPN (onboarding semplificato)

> [!NOTE]
> L'onboarding automatico del profilo VPN è attualmente in anteprima e i passaggi indicati in questa sezione potrebbero essere sostanzialmente modificati prima che venga rilasciato commercialmente.

Gli amministratori possono configurare la configurazione automatica del profilo VPN. In questo modo verrà automaticamente creato il profilo VPN defender per endpoint senza che l'utente lo faccia durante l'onboarding. Si noti che la VPN viene utilizzata per fornire la funzionalità di protezione Web. Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.

1. [Nell'interfaccia di amministrazione di Microsoft Endpoint manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Profili** di configurazione  ->  **dei dispositivi**  ->  **Crea profilo.**
1. Scegli **Piattaforma** come **iOS/iPadOS** e **Tipo di profilo** come **VPN.** Fare clic su **Crea**.
1. Digitare un nome per il profilo e fare clic su **Avanti.**
1. Seleziona **VPN personalizzata** per Tipo di connessione e nella sezione Vpn di **base** immetti quanto segue:
    - Connection Name = Microsoft Defender for Endpoint
    - Indirizzo del server VPN = 127.0.0.1
    - Metodo di autenticazione = "Nome utente e password"
    - Split Tunneling = Disabilita
    - Identificatore VPN = com.microsoft.scmx
    - Nelle coppie chiave-valore immettere la chiave **AutoOnboard** e impostare il valore su **True.**
    - Tipo di VPN automatica = VPN su richiesta
    - Fare **clic su** Aggiungi per **Regole** su richiesta e selezionare Voglio eseguire le operazioni seguenti = **Stabilire vpn**, Voglio limitare a = Tutti i **domini**.

    ![Screenshot della configurazione del profilo VPN](images/ios-deploy-8.png)

1. Fare clic su Avanti e assegnare il profilo agli utenti di destinazione.
1. Nella sezione *Revisione e creazione* verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.

## <a name="complete-onboarding-and-check-status"></a>Completare l'onboarding e controllare lo stato

1. Dopo aver installato Defender for Endpoint su iOS nel dispositivo, verrà visualizzata l'icona dell'app.

    ![Schermata di uno smart phone Descrizione generata automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. Tocca l'icona dell'app Defender for Endpoint e segui le istruzioni visualizzate per completare la procedura di onboarding. I dettagli includono l'accettazione da parte dell'utente finale delle autorizzazioni iOS richieste da Defender per Endpoint in iOS.

3. Al completamento dell'onboarding, il dispositivo inizierà a essere visualizzato nell'elenco Dispositivi Microsoft Defender Security Center.

    > [!div class="mx-imgBorder"]
    > ![Screenshot di un cellulare Descrizione generata automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Configurare Microsoft Defender per Endpoint per la modalità supervisione

L'app Microsoft Defender for Endpoint su iOS ha capacità specializzate nei dispositivi iOS/iPadOS supervisionati, date le maggiori funzionalità di gestione fornite dalla piattaforma su questi tipi di dispositivi. Per sfruttare queste funzionalità, l'app Defender for Endpoint deve sapere se un dispositivo è in modalità supervisione.

### <a name="configure-supervised-mode-via-intune"></a>Configurare la modalità supervisionata tramite Intune

Intune consente di configurare l'app Defender per iOS tramite un criterio di configurazione dell'app.

   > [!NOTE]
   > Questo criterio di configurazione dell'app per i dispositivi supervisionati è applicabile solo ai dispositivi gestiti e deve essere destinato a tutti i dispositivi iOS gestiti come procedura consigliata.

1. Accedi all'interfaccia [di Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) vai **a** App Criteri di configurazione  >  **app**  >  **Aggiungi**. Fare clic **su Dispositivi gestiti**.

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)

1. Nella pagina *Crea criteri di configurazione* app fornire le informazioni seguenti:
    - Nome criterio
    - Piattaforma: seleziona iOS/iPadOS
    - App di destinazione: **seleziona Microsoft Defender ATP** dall'elenco

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)

1. Nella schermata successiva seleziona **Usa progettazione configurazione** come formato. Specificare la proprietà seguente:
    - Chiave di configurazione: issupervised
    - Tipo di valore: String
    - Valore di configurazione: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)

1. Fare **clic su** Avanti per aprire la pagina Tag **ambito.** I tag di ambito sono facoltativi. Fare clic su **Avanti** per continuare.

1. Nella **pagina Assegnazioni** selezionare i gruppi che riceveranno il profilo. Per questo scenario, è consigliabile scegliere come destinazione **Tutti i dispositivi**. Per ulteriori informazioni sull'assegnazione di profili, vedere [Assegnare profili utente e dispositivo.](/mem/intune/configuration/device-profile-assign)

   Quando si distribuisce ai gruppi di utenti, un utente deve accedere a un dispositivo prima dell'applicazione del criterio.

   Fare clic su **Avanti**.

1. Al termine della pagina Revisione **e** creazione scegliere **Crea.** Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.

1. Successivamente, per le funzionalità avanzate di anti-phishing, puoi distribuire un profilo personalizzato nei dispositivi iOS supervisionati. Seguire la procedura seguente:
    - Scaricare il profilo di configurazione da [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Passare a **Dispositivi profili** di  ->  **configurazione iOS/iPadOS** Crea  ->    ->  **profilo**

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)

    - Specificare un nome del profilo. Quando viene richiesto di importare un file del profilo di configurazione, selezionare quello scaricato in precedenza.
    - Nella sezione **Assegnazione** seleziona il gruppo di dispositivi a cui vuoi applicare il profilo. Come procedura consigliata, questa operazione deve essere applicata a tutti i dispositivi iOS gestiti. Fare clic su **Avanti**.
    - Al termine della pagina Revisione **e** creazione scegliere **Crea.** Il nuovo profilo viene visualizzato nell'elenco dei profili di configurazione.

## <a name="next-steps"></a>Operazioni successive

[Configurare Defender per le funzionalità di Endpoint in iOS](ios-configure-features.md)
