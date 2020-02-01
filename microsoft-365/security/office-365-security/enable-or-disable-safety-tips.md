---
title: Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Indica agli amministratori di Office 365 e EOP come abilitare e disabilitare i suggerimenti per la sicurezza nei messaggi di posta elettronica.
ms.openlocfilehash: 6b94d34b6cf8bebc0aa4032f255b874fb7d4affb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599413"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365

Exchange Online Protection (EOP) aggiunge o timbra un suggerimento per la sicurezza ai messaggi di posta elettronica che offre. Questi suggerimenti per la sicurezza forniscono ai destinatari un modo rapido e visivo per determinare se un messaggio è proveniente da un mittente sicuro e verificato, se il messaggio è stato contrassegnato come posta indesiderata da Office 365, se il messaggio contiene elementi sospetti, ad esempio una truffa di phishing, o se sono presenti immagini esterne stato bloccato. Gli amministratori di Office 365 e EOP-standalone possono modificare l'impostazione di un criterio di posta indesiderata per abilitare o disabilitare i suggerimenti di sicurezza visualizzati nella posta elettronica in Outlook e in altri client di posta elettronica desktop.

Office 365 attiva suggerimenti per la sicurezza per impostazione predefinita per l'organizzazione e si consiglia di lasciarli abilitati per contribuire a combattere la posta indesiderata e gli attacchi di phishing. Non è possibile disabilitare i suggerimenti per la sicurezza per Outlook sul Web.

Per vedere alcuni esempi e conoscere le informazioni visualizzate in suggerimenti per la sicurezza, vedere Suggerimenti per la [sicurezza nei messaggi di posta elettronica in Office 365.](safety-tips-in-office-365.md)

Contenuto dell'argomento:

- [Per abilitare o disabilitare i suggerimenti per la sicurezza tramite il centro &amp; sicurezza e conformità di Office 365](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [Per abilitare o disabilitare i suggerimenti per la sicurezza tramite PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>Per abilitare o disabilitare i suggerimenti per la sicurezza tramite il centro &amp; sicurezza e conformità di Office 365
<a name="SandCCsafetytip"> </a>

1. Passare a [https://protection.office.com](https://protection.office.com).

2. Accedere a Office 365 con l'account di lavoro o della scuola.

3. Scegliere \> **criteri**di **gestione delle minacce** .

4. Nella pagina **criterio** scegliere protezione da **posta indesiderata**.

    ![In questa schermata viene illustrato come accedere alla pagina delle impostazioni di protezione da posta indesiderata nel centro sicurezza &amp; e conformità.](../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. Nella pagina impostazioni di protezione da **posta indesiderata** scegliere la scheda **personalizzato** .

    ![In questa schermata viene visualizzato il percorso della scheda personalizzato nella pagina impostazioni di protezione da posta indesiderata nel centro sicurezza &amp; e conformità.](../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. Se necessario, scegliere l'opzione **impostazioni personalizzate** per attivare le impostazioni personalizzate. Se l'opzione impostazioni personalizzate è impostata su **disattivato**, non sarà possibile modificare i criteri di filtro della posta indesiderata.

    ![In questa schermata vengono visualizzate le impostazioni dei criteri di filtro della posta indesiderata personalizzate disattivate.](../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. Espandere il criterio di posta indesiderata da modificare e quindi scegliere **modifica criterio**. Ad esempio, fare clic sulla freccia in giù accanto a **criteri di filtro della posta indesiderata predefiniti**. In alternativa, se si desidera, è possibile creare un nuovo criterio scegliendo **Aggiungi un criterio**.

8. Espandere la **posta indesiderata e le** azioni in blocco.

9. Per abilitare i suggerimenti di sicurezza, sotto suggerimenti per la **sicurezza**, selezionare la casella **di controllo su** . Per disabilitare i suggerimenti per la sicurezza, deselezionare la casella **di controllo su** .

10. Fare clic su **Salva**.

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>Per abilitare o disabilitare i suggerimenti per la sicurezza tramite PowerShell
<a name="pshellsafetytip"> </a>

Gli amministratori possono utilizzare PowerShell di Exchange Online per abilitare o disabilitare i suggerimenti per la sicurezza. Utilizzare il cmdlet Set-HostedContentFilterPolicy per abilitare o disabilitare i suggerimenti per la sicurezza in un criterio di filtro della posta indesiderata.

1. Connettersi a PowerShell per Exchange Online. Per informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Eseguire il cmdlet Set-HostedContentFilterPolicy per abilitare o disabilitare i suggerimenti per la sicurezza:

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

Dove:

- *Nome criterio* è il nome del criterio che si desidera modificare, ad esempio **default**.

- `$true`Attiva suggerimenti di sicurezza per i criteri di filtro della posta indesiderata.

- `$false`Disattiva i suggerimenti di sicurezza per i criteri di filtro della posta indesiderata.

Ad esempio, per disabilitare i suggerimenti per la sicurezza per i criteri di filtro della posta indesiderata predefiniti, eseguire il seguente comando:

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

Per ulteriori informazioni su questo cmdlet, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).

## <a name="still-need-help"></a>Serve ulteriore assistenza?
<a name="pshellsafetytip"> </a>

Se i suggerimenti per la sicurezza sono stati disabilitati, ma vengono ancora visualizzati nei messaggi di posta elettronica, controllare queste operazioni:

- Non è possibile disabilitare i suggerimenti per la sicurezza per Outlook sul Web. Provare a visualizzare lo stesso messaggio di posta elettronica in un altro client, ad esempio Outlook.

- I suggerimenti per la sicurezza sono attivati per impostazione predefinita per tutti gli utenti che utilizzano EOP, inclusi tutti gli utenti di Office 365. Per disabilitare i suggerimenti per la sicurezza visualizzati nella posta elettronica, è necessario disabilitarli utilizzando un criterio di filtro della posta indesiderata, come descritto in questo argomento. Dopo aver configurato il criterio, assicurarsi che sia abilitato. Per informazioni sull'abilitazione dei criteri di filtro della posta indesiderata, vedere [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).

Per altri modi per combattere la posta indesiderata e il phishing, vedere [Office 365 E-mail protezione dalla posta indesiderata](anti-spam-protection.md).
