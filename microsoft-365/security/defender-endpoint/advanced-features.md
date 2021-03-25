---
title: Configurare le funzionalità avanzate in Microsoft Defender per Endpoint
description: Attiva funzionalità avanzate come il file di blocco in Microsoft Defender per Endpoint.
keywords: funzionalità avanzate, impostazioni, file di blocco, analisi automatizzata, risoluzione automatica, skype, microsoft defender for identity, office 365, azure information protection, intune
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 059cfbf37c79ff9f99b5e46c8d4329c203aa9665
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215530"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Configurare le funzionalità avanzate in Defender for Endpoint

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

A seconda dei prodotti di sicurezza Microsoft che usi, alcune funzionalità avanzate potrebbero essere disponibili per l'integrazione di Defender per Endpoint con.

## <a name="enable-advanced-features"></a>Abilitare le funzionalità avanzate

1. Nel riquadro di spostamento seleziona **Impostazioni preferenze**  >  **Funzionalità avanzate.**
2. Selezionare la funzionalità avanzata che si desidera  configurare e attivare o disattivare **l'impostazione.**
3. Fare **clic su Salva preferenze.**

Utilizzare le funzionalità avanzate seguenti per proteggere meglio i file potenzialmente dannosi e ottenere informazioni più approfondite durante le indagini di sicurezza.

## <a name="automated-investigation"></a>Indagine automatizzata

Attivare questa funzionalità per sfruttare le funzionalità di analisi e correzione automatizzate del servizio. Per ulteriori informazioni, vedere [Analisi automatizzata.](automated-investigations.md)

## <a name="live-response"></a>Risposta live

Attiva questa funzionalità in modo che gli utenti con le autorizzazioni appropriate possano avviare una sessione di risposta in tempo reale nei dispositivi.

Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).

## <a name="live-response-for-servers"></a>Risposta in tempo reale per i server
Attivare questa funzionalità in modo che gli utenti con le autorizzazioni appropriate possano avviare una sessione di risposta in tempo reale sui server.

Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).


## <a name="live-response-unsigned-script-execution"></a>Esecuzione di script non firmati in tempo reale

L'abilitazione di questa funzionalità consente di eseguire script non firmati in una sessione di risposta in tempo reale.

## <a name="autoresolve-remediated-alerts"></a>Risolvere in modo automatico gli avvisi corretti

Per i tenant creati in Windows 10, versione 1809, la funzionalità di analisi e correzione automatizzata è configurata per impostazione predefinita per risolvere gli avvisi in cui lo stato del risultato dell'analisi automatica è "Nessuna minaccia trovata" o "Correzione".  Se non si desidera che gli avvisi vengono risolti automaticamente, è necessario disattivare manualmente la funzionalità.

> [!TIP]
> Per i tenant creati prima di tale versione, è necessario attivare manualmente questa funzionalità dalla [pagina Funzionalità](https://securitycenter.windows.com/preferences2/integration) avanzate.

> [!NOTE]
>
> - Il risultato dell'azione di risoluzione automatica può influire sul calcolo del livello di rischio del dispositivo basato sugli avvisi attivi rilevati in un dispositivo.
> - Se un analista delle operazioni di sicurezza imposta manualmente lo stato di un avviso su "In corso" o "Risolto", la funzionalità di risoluzione automatica non lo sovrascriverà.

## <a name="allow-or-block-file"></a>Consenti o blocca file

Il blocco è disponibile solo se l'organizzazione soddisfa questi requisiti:

- Usa Microsoft Defender Antivirus come soluzione antimalware attiva e,
- La funzionalità di protezione basata su cloud è abilitata

Questa funzionalità consente di bloccare i file potenzialmente dannosi nella rete. Il blocco di un file ne impedirà la lettura, la scrittura o l'esecuzione nei dispositivi dell'organizzazione.

Per attivare **Consenti o blocca** file:

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Funzionalità avanzate** Consenti o blocca  >  **file.**

1. Attivare o disattivare **l'impostazione.** 

    ![Immagine delle impostazioni avanzate per la funzionalità blocca file](images/atp-preferences-setup.png)

1. Seleziona **Salva preferenze** nella parte inferiore della pagina.

Dopo aver attivata questa funzionalità, puoi [bloccare i file](respond-file-alerts.md#allow-or-block-file) tramite la scheda **Aggiungi** indicatore nella pagina del profilo di un file.

## <a name="custom-network-indicators"></a>Indicatori di rete personalizzati

L'attivazione di questa funzionalità consente di creare indicatori per indirizzi IP, domini o URL, che determinano se saranno consentiti o bloccati in base all'elenco di indicatori personalizzato.

Per usare questa funzionalità, i dispositivi devono eseguire Windows 10 versione 1709 o successiva. Devono inoltre disporre della protezione di rete in modalità blocco e della versione 4.18.1906.3 o successiva della piattaforma antimalware, vedere [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Per ulteriori informazioni, vedere [Manage indicators.](manage-indicators.md)

> [!NOTE]
> La protezione di rete sfrutta i servizi di reputazione che elaborano le richieste in posizioni che potrebbero essere esterne alla posizione selezionata per i dati di Defender for Endpoint.

## <a name="show-user-details"></a>Mostra dettagli utente

Attivare questa funzionalità per visualizzare i dettagli utente archiviati in Azure Active Directory. I dettagli includono l'immagine, il nome, il titolo e le informazioni del reparto di un utente durante l'analisi delle entità dell'account utente. Le informazioni sull'account utente sono disponibili nelle visualizzazioni seguenti:

- Dashboard delle operazioni di sicurezza
- Coda avvisi
- Pagina dettagli dispositivo

Per ulteriori informazioni, vedere [Investigate a user account](investigate-user.md).

## <a name="skype-for-business-integration"></a>Integrazione di Skype for Business

L'abilitazione dell'integrazione di Skype for Business consente di comunicare con gli utenti tramite Skype for Business, la posta elettronica o il telefono. Ciò può essere utile quando è necessario comunicare con l'utente e ridurre i rischi.

> [!NOTE]
> Quando un dispositivo viene isolato dalla rete, è disponibile un popup in cui è possibile scegliere di abilitare le comunicazioni di Outlook e Skype che consentono le comunicazioni all'utente mentre sono disconnessi dalla rete. Questa impostazione si applica alle comunicazioni Skype e Outlook quando i dispositivi sono in modalità isolamento.

## <a name="azure-advanced-threat-protection-integration"></a>Integrazione di Azure Advanced Threat Protection

L'integrazione con Azure Advanced Threat Protection consente di eseguire il pivot direttamente in un altro prodotto di sicurezza microsoft Identity. Azure Advanced Threat Protection aumenta un'indagine con informazioni aggiuntive su un account sospetto compromesso e risorse correlate. Abilitando questa funzionalità, arricchirai la funzionalità di indagine basata su dispositivo tramite pivot nella rete da un punto di vista di identificazione.

> [!NOTE]
> Per abilitare questa funzionalità, è necessario disporre della licenza appropriata.

## <a name="office-365-threat-intelligence-connection"></a>Connessione di Office 365 Threat Intelligence

Questa funzionalità è disponibile solo se si dispone di un componente aggiuntivo di Office 365 E5 o Threat Intelligence attivo. Per ulteriori informazioni, vedere la pagina del prodotto Office 365 Enterprise E5.

Quando si attiva questa funzionalità, sarà possibile incorporare i dati di Office 365 Advanced Threat Protection in Microsoft Defender Security Center per condurre un'indagine completa sulla sicurezza tra le cassette postali di Office 365 e i dispositivi Windows.

> [!NOTE]
> Per abilitare questa funzionalità, è necessario disporre della licenza appropriata.

Per ricevere l'integrazione contestuale dei dispositivi in Office 365 Threat Intelligence, è necessario abilitare le impostazioni di Defender for Endpoint nel dashboard sicurezza & conformità. Per ulteriori informazioni, vedere [Analisi e risposta alle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

## <a name="microsoft-threat-experts"></a>Microsoft Threat Experts

Tra i due componenti Microsoft Threat Expert, la notifica di attacco mirato è in generale disponibile. La funzionalità esperti su richiesta è ancora in anteprima. Puoi usare la funzionalità esperti su richiesta solo se hai richiesto l'anteprima e l'applicazione è stata approvata. È possibile ricevere notifiche di attacco mirate dagli esperti microsoft threat tramite il dashboard degli avvisi del portale defender per endpoint e tramite posta elettronica se lo si configura.

> [!NOTE]
> La funzionalità Microsoft Threat Experts in Defender for Endpoint è disponibile con una licenza E5 per [Enterprise Mobility + Security.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

L'abilitazione di questa impostazione inoltra i segnali di Defender for Endpoint a Microsoft Cloud App Security per fornire una visibilità più approfondita sull'utilizzo delle applicazioni cloud. I dati inoltrati vengono archiviati ed elaborati nella stessa posizione dei dati di Cloud App Security.

> [!NOTE]
> Questa funzionalità sarà disponibile con una licenza E5 per [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) nei dispositivi che eseguono Windows 10 versione 1709 (OS Build 16299.1085 con [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, versione 1803 (OS Build 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versione 1809 (OS Build 17763.379 con [KB4489899](https://support.microsoft.com/help/4489899)) o versioni successive di Windows 10.

## <a name="azure-information-protection"></a>Azure Information Protection

L'attivazione di questa impostazione consente l'inoltro dei segnali ad Azure Information Protection. Offre ai proprietari e agli amministratori dei dati visibilità sui dati protetti nei dispositivi onboarded e nelle classificazioni dei rischi dei dispositivi.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

Inoltra i segnali di Microsoft Defender for Endpoint a Microsoft Secure Score nel Centro sicurezza Microsoft 365. L'attivazione di questa funzionalità consente a Microsoft Secure Score di visibilità sulla posizione di sicurezza del dispositivo. I dati inoltrati vengono archiviati ed elaborati nella stessa posizione dei dati di Microsoft Secure Score.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Abilitare l'integrazione di Microsoft Defender for Endpoint dal portale di Microsoft Defender per l'identità

Per ricevere l'integrazione contestuale dei dispositivi in Microsoft Defender for Identity, dovrai anche abilitare la funzionalità nel portale di Microsoft Defender per l'identità.

1. Accedere al portale [di Microsoft Defender per l'identità](https://portal.atp.azure.com/) con un ruolo amministratore globale o amministratore della sicurezza.

2. Fare **clic su Crea l'istanza.**

3. Attiva l'impostazione Integrazione **e** fai clic su **Salva.**

Dopo aver completato i passaggi di integrazione in entrambi i portali, potrai visualizzare avvisi pertinenti nella pagina dei dettagli del dispositivo o dei dettagli utente.

## <a name="microsoft-intune-connection"></a>Connessione a Microsoft Intune

Defender for Endpoint può essere integrato con [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) per abilitare l'accesso condizionale basato sul rischio [del dispositivo.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) Quando [accerti questa funzionalità,](configure-conditional-access.md)potrai condividere le informazioni sul dispositivo Defender for Endpoint con Intune, migliorando l'applicazione dei criteri.

> [!IMPORTANT]
> Dovrai abilitare l'integrazione sia in Intune che in Defender per Endpoint per usare questa funzionalità. Per altre informazioni su passaggi specifici, vedi [Configurare l'accesso condizionale in Defender per Endpoint.](configure-conditional-access.md)

Questa funzionalità è disponibile solo se sono disponibili le opzioni seguenti:

- Tenant con licenza per Enterprise Mobility + Security E3 e Windows E5 (o Microsoft 365 Enterprise E5)
- Un ambiente Microsoft Intune attivo, con dispositivi Windows 10 gestiti da Intune [aggiunti ad Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)

### <a name="conditional-access-policy"></a>Criteri di accesso condizionale

Quando abiliti l'integrazione di Intune, Intune creerà automaticamente un criterio di accesso condizionale (CA) classico. Questo criterio CA classico è un prerequisito per la configurazione delle relazioni sullo stato in Intune. Non deve essere eliminato.

> [!NOTE]
> Il criterio CA classico creato da Intune è distinto dai criteri di [accesso](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)condizionale moderni, usati per configurare gli endpoint.

## <a name="preview-features"></a>Funzionalità di anteprima

Scopri le nuove funzionalità nella versione di anteprima di Defender for Endpoint ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.

Avrai accesso alle funzionalità future, su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano in genere disponibili.

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Condividere gli avvisi degli endpoint con Il Centro conformità Microsoft

Inoltra gli avvisi di sicurezza degli endpoint e il relativo stato di valutazione al Centro conformità Microsoft, consentendo di migliorare i criteri di gestione dei rischi insider con avvisi e correggere i rischi interni prima che questi causano danni. I dati inoltrati vengono elaborati e archiviati nella stessa posizione dei dati di Office 365.

Dopo aver configurato gli indicatori di violazione [dei](/microsoft-365/compliance/insider-risk-management-settings#indicators) criteri di sicurezza nelle impostazioni di gestione dei rischi insider, gli avvisi di Defender for Endpoint verranno condivisi con la gestione dei rischi insider per gli utenti applicabili.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiornare le impostazioni di conservazione dei dati](data-retention-settings.md)
- [Configurare le notifiche di avviso](configure-email-notifications.md)
