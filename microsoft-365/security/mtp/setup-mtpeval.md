---
title: Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota
description: Accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di valutazione di Microsoft 365 Defender
keywords: Installazione di valutazione di Microsoft Threat Protection, installazione pilota di Microsoft Threat Protection, provare Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844825"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Configurare l'ambiente di test lab di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender 


La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft 365 Defender è un processo in tre fasi:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 1: preparazione </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 2: installazione </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Configurare ogni pilastro Microsoft 365 Defender per il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota e onboard your Endpoints" />
      <br/>Fase 3: configurare & onboard </a><br>
</td>


  </tr>
</table>

Si è attualmente in fase di configurazione. Eseguire i passaggi iniziali per accedere a Microsoft 365 Security Center e quindi configurare il laboratorio di valutazione o l'ambiente pilota.

Iscriversi a una sottoscrizione di Office 365 o Azure Active Directory per generare un tenant con *estensione onmicrosoft.com* che è possibile utilizzare per iscriversi alla propria licenza Microsoft 365 E5. 

>[!NOTE]
>Se si dispone già di una sottoscrizione di Office 365 o Azure Active Directory, è possibile ignorare i passaggi di valutazione di Office 365 E5 o di creazione di tenant pilota.

In questa fase, verranno guidati i seguenti aspetti:
- Creare un tenant di valutazione di Office 365 E5
- Abilitare la sottoscrizione di valutazione di Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Creare un tenant di valutazione di Office 365 E5
>[!NOTE]
>Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.

1. Andare al [portale del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **versione di valutazione gratuita**.

   ![Image of_Office 365 E5 versione di valutazione gratuita](../../media/mtp-eval-9.png)
  
2. Completare la registrazione di prova inserendo l'indirizzo di posta elettronica (personale o aziendale). Fare clic su **Configura account**.

   ![Pagina immagine of_Office 365 E5 registrazione di prova](../../media/mtp-eval-10.png)

3. Inserire il nome, il cognome, il numero di telefono aziendale, il nome della società, la dimensione dell'azienda e il paese o l'area geografica.  

   ![Immagine of_Office 365 E5 pagina di installazione di registrazione di prova per i dettagli relativi a nome, telefono e società](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Il paese o l'area geografica impostata in questa sezione determina l'area del Data Center in cui verrà ospitata la sede di Office 365.
  
4. Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata. Fare clic su **Invia codice di verifica**. 

   ![Immagine of_Office 365 E5 registrazione di prova pagina di installazione per richiedere la preferenza di verifica](../../media/mtp-eval-12.png)

5. Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti**.

   ![Immagine of_Office pagina di installazione di registrazione di prova 365 E5 in cui è possibile configurare il nome di dominio personalizzato](../../media/mtp-eval-13.png)
 
6. Impostare la prima identità, che sarà un amministratore globale per il tenant. Immettere il **nome** e la **password**. Fare clic su **Iscriviti**.

   ![Immagine of_Office pagina di installazione di registrazione di prova 365 E5 in cui è possibile impostare l'identità aziendale](../../media/mtp-eval-14.png)

7. Fare clic su **Vai al programma di installazione** per completare il provisioning del tenant di valutazione di Office 365 E5.

   ![Immagine della pagina di installazione di registrazione di prova di Office 365 E5 che richiede di fare clic su Vai imposta pulsante](../../media/mtp-eval-15.png)

8. Connettere il dominio aziendale al tenant di Office 365. Optional Scegliere **Connect a Domain your già own** e digitare il nome di dominio. Fare clic su **Avanti**.

   ![Image of_Office pagina di installazione di 365 E5 dove è necessario personalizzare l'accesso e la posta elettronica](../../media/mtp-eval-16.png)
 
9. Aggiungere un record TXT o MX per convalidare la proprietà del dominio. Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.

   ![Image of_Office pagina di installazione di 365 E5 dove è necessario aggiungere un record TXT di MX per verificare il dominio](../../media/mtp-eval-17.png)
 
10. Optional Creare più account utente per il tenant. È possibile ignorare questo passaggio facendo clic su **Avanti**.

    ![Pagina di installazione di Image of_Office 365 E5 dove è possibile aggiungere altri utenti](../../media/mtp-eval-18.png)
 
11. Optional Scaricare le app di Office. Fare clic su **Avanti** per ignorare questo passaggio. 

    ![Image of_Office 365 E5 page dove è possibile installare le app di Office](../../media/mtp-eval-19.png)

12. Optional Eseguire la migrazione dei messaggi di posta elettronica. Anche in questo caso, è possibile ignorare questo passaggio.

    ![Image of_Office 365 E5 dove è possibile impostare se eseguire la migrazione o meno dei messaggi di posta elettronica](../../media/mtp-eval-20.png)
 
13. Scegliere servizi online. Selezionare **Exchange** e fare clic su **Avanti**. 

    ![Image of_Office 365 E5 dove è possibile scegliere i servizi online](../../media/mtp-eval-21.png)

14. Aggiungere i record MX, CNAME e TXT al dominio. Al termine, selezionare **Verifica**.

    ![Image of_Office 365 E5 è possibile aggiungere i record DNS](../../media/mtp-eval-22.png)
 
15. Congratulazioni, è stato completato il provisioning del tenant di Office 365.

    ![Pagina di conferma del completamento dell'installazione di Image of_Office 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Abilitare la sottoscrizione di valutazione di Microsoft 365

>[!NOTE]
>La registrazione per una versione di valutazione fornisce 25 licenze utente da utilizzare per un mese. Per ulteriori informazioni, vedere [provare o acquistare un abbonamento a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .

1. Dall'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/), fare clic su **fatturazione** , quindi passare a **acquisto servizi**.

2. Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita**. 

   ![Pagina immagine of_Microsoft 365 E5 inizio versione di valutazione gratuita](../../media/mtp-eval-24.png)

3. Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata. Dopo aver deciso, immettere il numero di telefono, selezionare **Text me** or **Call me** a seconda della selezione.

   ![Immagine of_Microsoft 365 E5 avvio della pagina di valutazione gratuita per richiedere informazioni di contatto per inviare codice per dimostrare che non sei un robot](../../media/mtp-eval-25.png)
 
4. Immettere il codice di verifica e fare clic su **Avvia la versione di valutazione gratuita**.

   ![Image of_Microsoft 365 E5 avviare la pagina di valutazione gratuita dove è possibile compilare il codice di verifica del sistema inviato per dimostrare che non si è un robot](../../media/mtp-eval-26.png)

5. Fare clic su **prova ora** per confermare la versione di valutazione di Microsoft 365 E5.

   ![Immagine of_Microsoft 365 E5 avviare la pagina di prova gratuita in cui è necessario Clock il pulsante prova ora per iniziare](../../media/mtp-eval-27.png)
 
6. Accedere agli utenti attivi degli utenti dell'interfaccia di **amministrazione di Microsoft 365**  >  **Users**  >  **Active users**. Selezionare l'account utente, selezionare **Gestisci licenze di prodotto** , quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5**. Fare clic su **Salva**.

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile selezionare la licenza Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. Selezionare di nuovo l'account di amministratore globale e quindi fare clic su **Gestisci nome utente**.

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile selezionare account e quindi Gestione nome utente](../../media/mtp-eval-29.png)

8. Optional Modificare il dominio da *onmicrosoft.com* al proprio dominio, a seconda di cosa si è scelto nei passaggi precedenti. Fare clic su **Salva modifiche**.

   ![Image of_Microsoft 365 pagina dell'interfaccia di amministrazione in cui è possibile modificare la preferenza del dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Passaggio successivo
|![Fase 3: configurare & onboard](../../media/config-onboard.png) <br>[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro Microsoft 365 Defender per il laboratorio di valutazione di Microsoft 365 Defender o l'ambiente pilota e onboard your Endpoints.
|:-------|:-----|
