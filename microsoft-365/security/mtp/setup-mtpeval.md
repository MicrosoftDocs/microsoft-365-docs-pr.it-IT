---
title: Configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender
description: Accedere al Centro sicurezza Microsoft 365 e quindi configurare l'ambiente lab di valutazione di Microsoft 365 Defender
keywords: Configurazione della versione di valutazione di Microsoft Threat Protection, configurazione pilota di Microsoft Threat Protection, provare Microsoft Threat Protection, configurazione del lab di valutazione di Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932983"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Configurare l'ambiente lab di valutazione di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender 


La creazione di un ambiente pilota o un lab di valutazione di Microsoft 365 Defender e la sua distribuzione è un processo in tre fasi:

|[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: preparazione](prepare-mtpeval.md) |![Fase 2: configurazione](../../media/phase-diagrams/setup.png)<br/>Fase 2: configurazione |[![Fase 3: onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: onboard](config-mtpeval.md) | [![Tornare al progetto pilota](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Tornare al playbook pilota](mtp-pilot.md) |
|--|--|--|--|
||*Sei qui!*  | | |


Al momento è in corso la fase di configurazione. Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 e quindi configurare il laboratorio di valutazione o l'ambiente pilota.

Iscriversi a un abbonamento a Office 365 o Azure Active Directory per generare un tenant con estensione *onmicrosoft.com* che è possibile usare per iscriversi alla licenza di Microsoft 365 E5. 

>[!NOTE]
>Se si dispone già di un abbonamento a Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant pilota o di valutazione di Office 365 E5.

In questa fase, si verrà guidati a:
- Creare un tenant di valutazione di Office 365 E5
- Abilitare la sottoscrizione di valutazione di Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Creare un tenant di valutazione di Office 365 E5
>[!NOTE]
>Se si dispone già di un abbonamento a Office 365 o Azure Active Directory, è possibile ignorare i passaggi di creazione del tenant di valutazione di Office 365 E5.

1. Accedere al portale [del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **Versione di valutazione gratuita.**

   ![Immagine of_Office pagina di valutazione gratuita di 365 E5](../../media/mtp-eval-9.png)
  
2. Completare la registrazione della versione di valutazione immettendo il proprio indirizzo di posta elettronica (personale o aziendale). Fare **clic su Configura account.**

   ![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)

3. Compila nome, cognome, numero di telefono dell'azienda, nome della società, dimensione della società e paese o area geografica.  

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5 che richiede nome, telefono e dettagli aziendali](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Il paese o l'area geografica impostata qui determina l'area del data center in cui verrà ospitato Office 365.
  
4. Scegli la preferenza di verifica: tramite un SMS o una chiamata. Fare clic **su Invia codice di verifica.** 

   ![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)

5. Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti.**

   ![Immagine of_Office configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile configurare il nome di dominio personalizzato](../../media/mtp-eval-13.png)
 
6. Configurare la prima identità, che sarà un amministratore globale per il tenant. Immettere **nome** e **password.** Fare **clic su Registrazione.**

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. Fare **clic su Go to Setup** per completare il provisioning del tenant di valutazione di Office 365 E5.

   ![Immagine della pagina di configurazione della registrazione della versione di valutazione di Office 365 E5 che richiede di fare clic sul pulsante Vai all'installazione](../../media/mtp-eval-15.png)

8. Connettere il dominio aziendale al tenant di Office 365. [Facoltativo] Choose **Connect a domain you already own** and type in your domain name. Fare clic su **Avanti**.

   ![Immagine of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)
 
9. Aggiungere un record TXT o MX per convalidare la proprietà del dominio. Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.

   ![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)
 
10. [Facoltativo] Creare altri account utente per il tenant. È possibile ignorare questo passaggio facendo clic su **Avanti.**

    ![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)
 
11. [Facoltativo] Scaricare le app di Office. Fare **clic su** Avanti per ignorare questo passaggio. 

    ![Immagine of_Office 365 E5 in cui è possibile installare le app di Office](../../media/mtp-eval-19.png)

12. [Facoltativo] Eseguire la migrazione dei messaggi di posta elettronica. Anche in questo caso, è possibile ignorare questo passaggio.

    ![Immagine of_Office 365 E5 in cui è possibile impostare se eseguire o meno la migrazione dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. Scegliere i servizi online. Selezionare **Exchange** e fare clic su **Avanti.** 

    ![Immagine of_Office 365 E5 in cui è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. Aggiungere record MX, CNAME e TXT al dominio. Al termine, selezionare **Verifica.**

    ![Immagine of_Office 365 E5 qui è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. Congratulazioni, il provisioning del tenant di Office 365 è stato completato.

    ![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Abilitare la sottoscrizione di valutazione di Microsoft 365

>[!NOTE]
>La registrazione a una versione di valutazione offre 25 licenze utente da usare per un mese. Per informazioni dettagliate, vedere Provare o acquistare [un abbonamento a M365.](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1)

1. [Dall'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)fare clic su **Fatturazione** e quindi passare ad Acquisto **di servizi.**

2. Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita.** 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. Scegli la preferenza di verifica: tramite un SMS o una chiamata. Dopo aver deciso, immettere il numero di telefono, selezionare **Sms o** **Chiamami a** seconda della selezione effettuata.

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. Immetti il codice di verifica e fai clic **su Avvia la versione di valutazione gratuita.**

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. Fare **clic su Prova per** confermare la versione di valutazione di Microsoft 365 E5.

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. Passare agli utenti **attivi dell'interfaccia di amministrazione di Microsoft 365.**  >    >   Selezionare l'account utente, selezionare Gestisci licenze di **prodotto,** quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5.** Fare clic su **Salva**.

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile selezionare la licenza di Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. Selezionare di nuovo l'account amministratore globale, quindi fare clic **su Gestisci nome utente.**

   ![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)

8. [Facoltativo] Modificare il dominio *da onmicrosoft.com* al proprio dominio, a seconda di ciò che è stato scelto nei passaggi precedenti. Fare clic su **Salva modifiche**.

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Passaggio successivo
|[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro di Microsoft 365 Defender per il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender ed eseguire l'onboardboard degli endpoint.
|:-------|:-----|
