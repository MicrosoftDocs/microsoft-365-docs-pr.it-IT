---
title: Configurare gruppi e utenti - Ambiente di sviluppo/test per la campagna politica
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Riepilogo: creare sottoscrizioni di valutazione di Office 365 ed Enterprise Mobility + Security (EMS) con utenti e gruppi per un ambiente di sviluppo/test di una campagna politica.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204965"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Configurare gruppi e utenti per un ambiente di sviluppo/test per la campagna politica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)

 **Riepilogo:** creare sottoscrizioni di valutazione di Office 365 ed Enterprise Mobility + Security (EMS) con utenti e gruppi per un ambiente di sviluppo/test di una campagna politica.

Attenersi alle istruzioni in questo articolo per creare un ambiente di sviluppo/test che include account utente e gruppi semplificati per la soluzione [Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Fase 1: creare l'ambiente di sviluppo/test di Office 365

In questa fase si ottengono le sottoscrizioni di valutazione per Office 365 E5 ed Enterprise Mobility + Security (EMS) E5 per un'organizzazione fittizia che rappresenta una campagna politica.

Per prima cosa, seguire le istruzioni in **Fase 2** di [Configurazione di base semplificata](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).

Iscriversi quindi per l’abbonamento di prova di EMS E5 e aggiungerlo alla stessa organizzazione come abbonamento di prova.

1. Se necessario, accedere all'interfaccia di amministrazione con le credenziali dell'account amministratore globale della sottoscrizione di valutazione. Per informazioni, vedere [Dove accedere](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Scegliere il riquadro **Amministrazione**.

3. Nella scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Fatturazione > Servizi di acquisto** nella barra di spostamento sinistra.

4. Nella pagina **Acquisto di servizi**, individuare la voce **Enterprise Mobility + Security E5**. Posizionare il puntatore del mouse su di essa e fare clic su **Avvia la versione di valutazione gratuita**.

5. Nella pagina **Conferma l'ordine**, fare clic su **Prova adesso**.

6. Nella pagina **Ricevuta ordine**, fare clic su **Continua**.

Abilitare quindi la licenza EMS E5 per l'account amministratore globale.

1. Nella scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti > Utenti attivi** nel riquadro di spostamento sinistro.

2. Fare clic sull'account amministratore globale e quindi su **Modifica** per le **licenze del prodotto**.

3. Nel riquadro **Licenze per i prodotti**, impostare la licenza per i prodotti di **Enterprise Mobility + Security E5** su **Attiva**, fare clic su **Salva** e quindi fare doppio clic su **Chiudi**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Fase 2: creare e configurare i gruppi di Azure Active Directory (AD)

In questa fase, vengono creati e configurati i gruppi di Azure AD per la campagna.

Innanzitutto, creare un set di gruppi per una campagna politica tipica con il portale di Azure.

1. In un'altra scheda del browser, accedere al portale di Azure <https://portal.azure.com>. Se necessario, accedere con le credenziali dell'account amministratore globale della sottoscrizione di valutazione di Office 365 E5.

2. Nel portale di Azure fare clic su **Azure Active Directory > Utenti e gruppi > Tutti i gruppi**.

3. Eseguire la procedura seguente per ciascun nome del gruppo nell'elenco riportato di seguito:

   - Personale senior e strategico

   - IT staff

   - Personale di analisi

   - Personale di base regolare

   - Personale delle operazioni

   - Personale di campo

1. Nel pannello **Tutti i gruppi** fare clic su **+ Nuovo gruppo**.

2. Digitare il nome del gruppo dall'elenco in **Nome**.

3. Selezionare **Utente dinamico** in **Appartenenza**.

4. Selezionare **Sì** per **Abilitare le funzionalità di Office**.

5. Fare clic su **Aggiungere query dinamica**.

6. Selezionare **Reparto** in **Dove aggiungere utenti**

7. Nel campo successivo, selezionare **Uguale a**.

8. Nel campo successivo, digitare il nome del gruppo dall'elenco.

9. Fare clic su **Aggiungi query** e quindi su **Crea**.

10. Fare clic su **Utenti e gruppi - Tutti i gruppi**.

Quindi, configurare i gruppi in modo che ai membri vengano automaticamente assegnate licenze di Office 365 E5 e EMS E5.

1. Nel portale di Azure fare clic su **Azure Active Directory > Licenze > Tutti i prodotti**.

2. Nell'elenco, selezionare **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5**, quindi fare clic su **Assegna**.

3. Nel pannello **Assegnare licenza** fare clic su **Utenti e gruppi**.

4. Nell'elenco dei gruppi, selezionare quanto segue:

   - Personale di analisi

   - Personale di campo

   - Personale IT

   - Personale delle operazioni

   - Personale di base regolare

   - Personale senior e strategico

5. Fare clic su **Seleziona**, quindi su **Assegna**.

6. Chiudere la scheda del portale di Azure nel browser.

## <a name="phase-3-add-your-user-accounts"></a>Fase 3: Aggiungere gli account utente

In questa fase, si aggiungono gli account utente di esempio per la campagna politica.

Successivamente, [connettersi con il modulo di Azure Active Directory PowerShell for Graph](../../enterprise/connect-to-microsoft-365-powershell.md).

Successivamente, inserire il nome dell'organizzazione, la posizione e una password comune; eseguire quindi questi comandi dal prompt dei comandi di PowerShell o Integrated Script Environment (ISE):

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> L'utilizzo di una password comune in questo caso è per rendere automatica e facile la configurazione per un ambiente di sviluppo/test. Non è una scelta consigliata per sottoscrizioni di produzione. Effettuando l'accesso con ognuno di questi nuovi account utente, verrà richiesto di modificare la password.

Seguire questi passaggi per verificare che l'appartenenza ai gruppi dinamici e le licenze basate su gruppi funzionino correttamente.

1. Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Amministratore**.

2. Dalla nuova scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Utenti**.

3. Nell'elenco di utenti, fare clic su **Candidato**.

4. Nel riquadro che elenca le proprietà dell'account utente **Candidato**, verificare che:

   - È un membro del gruppo **Personale senior e strategico** (in **Appartenenze a gruppi**).

   - Dispone delle licenze **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** (in **Licenze per i prodotti**).

5. Chiudere il riquadro dell'account utente **Candidato**.

## <a name="record-values-for-future-reference"></a>Registrare i valori per consultarli in futuro

Registrare questi valori per utilizzarli con le sottoscrizioni di valutazione di Office 365 ed EMS per questo ambiente di sviluppo/test:

- Nome dell'organizzazione della sottoscrizione di valutazione: ![Sottolineato](../../media/Common-Images/TableLine.png)

  Ad esempio, per il nome di dominio della sottoscrizione di valutazione di contoso.onmicrosoft.com, il nome dell'azienda è "contoso".

- Nome amministratore globale: ![Sottolineato](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Registrare la password per l'account e la password iniziale comune per gli altri account utente in un luogo sicuro.

## <a name="next-step"></a>Passaggio successivo

Creare quattro tipi diversi di siti del team di SharePoint Online nell’ambiente di sviluppo/test con [Creare siti del team in un ambiente di sviluppo/test per la campagna politica](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>Vedere anche

[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Creare siti del team in un ambiente di sviluppo/test per la campagna politica](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[Guida al lab test (TLG) per adozione del cloud](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Adozione del cloud e soluzioni ibride](/office365/enterprise/cloud-adoption-and-hybrid-solutions)