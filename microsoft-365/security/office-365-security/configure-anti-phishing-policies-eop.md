---
title: Configurare il criterio anti-phishing predefinito in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come modificare le impostazioni di anti-spoofing disponibili nei criteri anti-phishing predefiniti nelle organizzazioni di Office 365 con le cassette postali di Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537534"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Configurare il criterio anti-phishing predefinito in EOP

Le organizzazioni di Office 365 con le cassette postali di Exchange Online e le organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online dispongono di un criterio antiphishing predefinito. Questo criterio contiene un numero limitato di funzionalità di anti-spoofing che sono abilitate per impostazione predefinita. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

Le organizzazioni di Office 365 che dispongono di cassette postali di Exchange Online possono modificare il criterio anti-phishing predefinito nel centro sicurezza & conformità di Office 365 o in PowerShell di Exchange Online. Le organizzazioni di EOP autonome senza le cassette postali di Exchange Online non possono modificare i criteri anti-phishing predefiniti.

Per informazioni sulla creazione e la modifica dei criteri di anti-phishing ATP più avanzati disponibili in Office 365 Advanced Threat Protection, vedere [configurare i criteri di anti-phishing ATP in office 365](configure-atp-anti-phishing-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per aggiungere, modificare ed eliminare i criteri di anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).

- Per le impostazioni consigliate per il criterio anti-phishing predefinito, vedere [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Consentire l'applicazione dei criteri aggiornati fino a 30 minuti.

- Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica in Office 365](how-policies-and-protections-are-combined.md).

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito

Il criterio anti-phishing predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri. Per modificare il criterio anti-phishing predefinito, eseguire le operazioni seguenti:

1. Nel centro sicurezza & conformità, accedere a **criterio** \> di **gestione** \> delle minacce **anti-phishing**.

2. Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.

3. Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** . Nella sezione **spoofing** fare clic su **modifica**.

   Si noti che queste impostazioni sono identiche alle impostazioni di spoofing disponibili nei criteri di anti-phishing ATP.

   - **Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso. Per disattivarla, fare scorrere l'interruttore su **disattivata**. Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Office 365; è invece possibile abilitare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Abilita funzionalità mittente non autenticato**: aggiunge un punto interrogativo alla foto del mittente se il messaggio non supera i controlli di autenticazione della posta elettronica. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings). Il valore predefinito è **Attivato**. Per disattivarla, fare scorrere l'interruttore su **disattivata**.

   - **Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:

     **Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:

     - **Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** (questo è il valore predefinito).
     - **Mettere in quarantena il messaggio**

   - **Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:

       - **Abilitare la protezione antispoofing**
       - **Abilitare la funzionalità mittente non autenticato**

   Al termine, fare clic su **Salva** su qualsiasi pagina.

4. Tornare alla pagina **Edit your Policy Office365 antiphishing default** , rivedere le impostazioni e fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing predefiniti

1. Nel centro sicurezza & conformità e passare a **criteri** \> di **gestione** \> delle minacce **ATP anti-phishing**.

2. Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Utilizzo di PowerShell di Exchange Online per configurare i criteri di anti-phishing predefiniti

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>Utilizzo di PowerShell per visualizzare i criteri anti-phishing predefiniti

Per visualizzare i criteri anti-phishing predefiniti, eseguire il comando seguente:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>Utilizzo di PowerShell per modificare il criterio anti-phishing predefinito

Per modificare i criteri anti-phishing predefiniti, utilizzare la sintassi seguente:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

In questo esempio viene modificata l'azione per i messaggi falsificati che non riescono a controllare l'autenticazione in quarantena.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato correttamente il criterio anti-phishing predefinito, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere **a criterio di** \> **gestione** \> delle minacce **anti-phishing** \> fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
