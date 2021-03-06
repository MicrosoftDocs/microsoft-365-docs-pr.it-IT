---
title: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota
description: Accedere Microsoft 365 Security Center e quindi configurare l'Microsoft 365 Defender lab di valutazione
keywords: Microsoft 365 Defender di prova, Microsoft 365 Defender installazione pilota, provare a Microsoft 365 Defender, Microsoft 365 Defender di valutazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454734"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>Configurare la versione Microsoft 365 Defender in un ambiente lab 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender 

In questo argomento viene illustrato come configurare un ambiente lab dedicato. Per informazioni sulla configurazione di una versione di valutazione in produzione, vedere la nuova guida di valutazione [e Microsoft 365 Defender](eval-overview.md) pilota. 

## <a name="create-an-office-365-e5-trial-tenant"></a>Creare un tenant Office 365 E5 di valutazione
>[!NOTE]
>Se si dispone già di una sottoscrizione Office 365 o Azure Active Directory, è possibile ignorare i passaggi Office 365 E5 creazione del tenant di valutazione.

1. Vai al portale [Office 365 E5 prodotto e](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) seleziona Versione di valutazione **gratuita.**

   ![Pagina di valutazione of_Office 365 E5 gratuita di Image of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Completare la registrazione della versione di valutazione immettendo l'indirizzo di posta elettronica (personale o aziendale). Fare **clic su Configura account**.

   ![Immagine of_Office pagina di configurazione della registrazione della versione di valutazione di 365 E5](../../media/mtp-eval-10.png)

3. Compilare nome, cognome, numero di telefono dell'azienda, nome della società, dimensioni della società e paese o area geografica.  

   ![Image of_Office 365 E5 trial registration setup page asking for name, phone, and company details](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Il paese o l'area geografica impostata qui determina l'area del data center Office 365 sarà ospitata.
  
4. Scegli la preferenza di verifica: tramite un SMS o una chiamata. Fare **clic su Invia codice di verifica**. 

   ![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)

5. Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti.**

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. Configurare la prima identità, che sarà un amministratore globale per il tenant. Compilare **Nome** e **Password**. Fare **clic su Iscriviti.**

   ![Immagine of_Office configurazione della registrazione della versione di valutazione di 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. Fare **clic su Vai a Installazione** per completare il provisioning Office 365 E5 tenant di valutazione.

   ![Immagine della pagina Office 365 E5 di installazione della registrazione della versione di valutazione che richiede di fare clic sul pulsante Vai all'installazione](../../media/mtp-eval-15.png)

8. Connessione dominio aziendale al tenant Office 365 aziendale. [Facoltativo] Scegliere **Connessione un dominio di cui si è già proprietari** e digitare il nome di dominio. Fare clic su **Avanti**.

   ![Immagine of_Office configurazione di 365 E5 in cui personalizzare l'accesso e la posta elettronica](../../media/mtp-eval-16.png)
 
9. Aggiungere un record TXT o MX per convalidare la proprietà del dominio. Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.

   ![Immagine of_Office configurazione di 365 E5 in cui aggiungere un record TXT di MX per verificare il dominio](../../media/mtp-eval-17.png)
 
10. [Facoltativo] Creare altri account utente per il tenant. È possibile ignorare questo passaggio facendo clic su **Avanti.**

    ![Pagina of_Office configurazione di 365 E5 in cui è possibile aggiungere altri utenti](../../media/mtp-eval-18.png)
 
11. [Facoltativo] Scarica Office app. Fare **clic su** Avanti per ignorare questo passaggio. 

    ![Pagina of_Office 365 E5 in cui puoi installare le tue Office app](../../media/mtp-eval-19.png)

12. [Facoltativo] Eseguire la migrazione dei messaggi di posta elettronica. Anche in questo caso, è possibile ignorare questo passaggio.

    ![Immagine of_Office 365 E5 in cui è possibile impostare se eseguire o meno la migrazione dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. Scegliere i servizi online. Selezionare **Exchange** e fare clic su **Avanti.** 

    ![Immagine of_Office 365 E5 in cui è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. Aggiungere record MX, CNAME e TXT al dominio. Al termine, selezionare **Verifica**.

    ![Immagine of_Office 365 E5 qui è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. Congratulazioni, hai completato il provisioning del tenant Office 365 tenant.

    ![Pagina di conferma del completamento dell'installazione di Of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Abilitare Microsoft 365 di valutazione

>[!NOTE]
>La registrazione a una versione di valutazione offre 25 licenze utente da usare per un mese. Per [informazioni dettagliate, vedere Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)

1. Da [Amministrazione Microsoft 365,](https://admin.microsoft.com/)fare clic su **Fatturazione** e quindi passare a **Acquista servizi.**

2. Seleziona **Microsoft 365 E5** e fai clic su **Avvia versione di valutazione gratuita.** 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. Scegli la preferenza di verifica: tramite un SMS o una chiamata. Una volta deciso, immettere il numero di telefono, selezionare **Chiamami** o **Chiamami** a seconda della selezione.

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. Immetti il codice di verifica e fai clic **su Avvia la versione di valutazione gratuita.**

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. Fai **clic su Prova ora** per confermare la Microsoft 365 E5 versione di valutazione.

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. Passare al Centro **Amministrazione Microsoft 365**  >  **utenti Utenti**  >  **attivi**. Seleziona l'account utente, seleziona **Gestisci licenze prodotto,** quindi scambia la licenza da Office 365 E5 a **Microsoft 365 E5**. Fare clic su **Salva**.

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile selezionare Microsoft 365 E5 licenza](../../media/mtp-eval-28.png)
 
7. Selezionare di nuovo l'account amministratore globale, quindi fare clic **su Gestisci nome utente.**

   ![Immagine of_Microsoft interfaccia di amministrazione di 365 in cui è possibile selezionare Account e quindi Gestire il nome utente](../../media/mtp-eval-29.png)

8. [Facoltativo] Modificare il dominio *da onmicrosoft.com* al proprio dominio, a seconda di ciò che è stato scelto nei passaggi precedenti. Fare clic su **Salva modifiche**.

   ![Immagine of_Microsoft pagina dell'interfaccia di amministrazione di 365 in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Passaggio successivo
|[Fase 3: configurare & onboard](config-m365d-eval.md) | Configurare ogni Microsoft 365 Defender pilastro per il Microsoft 365 Defender di prova o l'ambiente pilota e l'onboardboard degli endpoint.
|:-------|:-----|
