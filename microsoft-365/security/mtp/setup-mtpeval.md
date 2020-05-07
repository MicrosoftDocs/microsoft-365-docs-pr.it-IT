---
title: Configurare l'ambiente di test lab di Microsoft Threat Protection
description: Accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di test lab di Microsoft Threat Protection
keywords: Installazione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049616"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Configurare l'ambiente di test lab di Microsoft Threat Protection 

**Si applica a:**
- Microsoft Threat Protection 


La creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la distribuzione di questo è un processo in tre fasi:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection" />
      <br/>Fase 1: preparazione</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurare il laboratorio di valutazione di Microsoft Threat Protection" />
      <br/>Fase 2: installazione</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e onboard your Endpoints" />
      <br/>Fase 3: configurare & onboard</a><br>
</td>


  </tr>
</table>

Si è attualmente in fase di configurazione. Eseguire la procedura iniziale per accedere a Microsoft 365 Security Center e quindi configurare l'ambiente di prova.

Iscriversi a una sottoscrizione di Office 365 o Azure Active Directory per generare un tenant con *estensione onmicrosoft.com* che è possibile utilizzare per iscriversi alla propria licenza Microsoft 365 E5. 

>[!NOTE]
>Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.

In questa fase, verranno guidati i seguenti aspetti:
- Creare un tenant di valutazione di Office 365 E5
- Abilitare la sottoscrizione di valutazione di Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Creare un tenant di valutazione di Office 365 E5
>[!NOTE]
>Se si dispone già di una sottoscrizione di Office 365 o di Azure Active Directory, è possibile ignorare la procedura di creazione del tenant di valutazione di Office 365 E5.

1. Andare al [portale del prodotto Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) e selezionare **versione di valutazione gratuita**.
![Of_page immagine](../../media/mtp-eval-9.png) <br>
  
2. Completare la registrazione di prova inserendo l'indirizzo di posta elettronica (personale o aziendale). Fare clic su **Configura account**.
![Of_page immagine](../../media/mtp-eval-10.png) <br> 

3. Inserire il nome, il cognome, il numero di telefono aziendale, il nome della società, la dimensione dell'azienda e il paese o l'area geografica.  
<br>![Of_page immagine](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Il paese o l'area geografica impostata in questa sezione determina l'area del Data Center in cui verrà ospitata la sede di Office 365.
  
4. Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata. Fare clic su **Invia codice di verifica**. 
![Of_page immagine](../../media/mtp-eval-12.png) <br>

5. Impostare il nome di dominio personalizzato per il tenant, quindi fare clic su **Avanti**.
<br>![Of_page immagine](../../media/mtp-eval-13.png) <br>
 
6. Configurare la prima identità che sarà un amministratore globale per il tenant. Immettere il **nome** e la **password**. Fare clic su **Iscriviti**.
![Of_page immagine](../../media/mtp-eval-14.png) <br>
c
7. Fare clic su **Vai al programma di installazione** per completare il provisioning del tenant di valutazione di Office 365 E5.
<br>![Of_page immagine](../../media/mtp-eval-15.png) <br>

8. Connettere il dominio aziendale al tenant di Office 365. Optional Scegliere **Connect a Domain your già own** e digitare il nome di dominio. Fare clic su **Avanti**.
<br>![Of_page immagine](../../media/mtp-eval-16.png) <br>
 
9. Sarà necessario aggiungere un record TXT o MX per convalidare la proprietà del dominio. Dopo aver aggiunto il record TXT o MX al dominio, selezionare **Verifica**.
<br>![Of_page immagine](../../media/mtp-eval-17.png) <br>
 
10. Optional Creare più account utente per il tenant. È possibile ignorare questo passaggio facendo clic su **Avanti**.
![Of_page immagine](../../media/mtp-eval-18.png) <br>
 
11. Optional Scaricare le app di Office. Fare clic su **Avanti** per ignorare questo passaggio. 
<br>![Of_page immagine](../../media/mtp-eval-19.png) <br>

12. Optional Eseguire la migrazione dei messaggi di posta elettronica. Anche in questo caso, è possibile ignorare questo passaggio.
<br>![Of_page immagine](../../media/mtp-eval-20.png) <br>
 
13. Scegliere servizi online. Selezionare **Exchange** e fare clic su **Avanti**. 
<br>![Of_page immagine](../../media/mtp-eval-21.png) <br>

14. Aggiungere i record MX, CNAME e TXT al dominio. Al termine, selezionare **Verifica**.
<br>![Of_page immagine](../../media/mtp-eval-22.png) <br>
 
15. Congratulazioni, è stato completato il provisioning del tenant di Office 365.
<br>![Of_page immagine](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Abilitare la sottoscrizione di valutazione di Microsoft 365

>[!NOTE]
>La registrazione per una versione di valutazione fornisce 25 licenze utente da utilizzare per un mese. Per ulteriori informazioni, vedere [provare o acquistare un abbonamento a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .

1. Dall'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/), fare clic su **fatturazione** , quindi passare a **acquisto servizi**.

2. Selezionare **Microsoft 365 E5** e fare clic su **Avvia versione di valutazione gratuita**. 
![Of_page immagine](../../media/mtp-eval-24.png) <br>

3. Scegliere la preferenza di verifica: tramite un messaggio di testo o una chiamata. Dopo aver deciso, immettere il numero di telefono, selezionare **Text me** or **Call me** a seconda della selezione.
![Of_page immagine](../../media/mtp-eval-25.png) <br>
 
4. Immettere il codice di verifica e fare clic su **Avvia la versione di valutazione gratuita**. 
<br>![Of_page immagine](../../media/mtp-eval-26.png) <br>

5. Fare clic su **prova ora** per confermare la versione di valutazione di Microsoft 365 E5.
<br>![Of_page immagine](../../media/mtp-eval-27.png) <br>
 
6. Accedere agli utenti**attivi**degli > **utenti** > dell'interfaccia di **amministrazione di Microsoft 365**. Selezionare l'account utente, selezionare **Gestisci licenze di prodotto**, quindi scambiare la licenza da Office 365 E5 a **Microsoft 365 E5**. Fare clic su **Salva**.
![Of_page immagine](../../media/mtp-eval-28.png) <br>
 
7. Selezionare di nuovo l'account di amministratore globale e quindi fare clic su **Gestisci nome utente**.
<br>![Of_page immagine](../../media/mtp-eval-29.png) <br>

8. Optional Modificare il dominio da *onmicrosoft.com* al proprio dominio, a seconda di cosa si è scelto nei passaggi precedenti. Fare clic su **Salva modifiche**.
<br>![Of_page immagine](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Passaggio successivo
||| |:-------|:-----| config-onboard. png) <br>[Fase 3: configurare & onboard](config-mtpeval.md) | Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e onboard your Endpoints.
