---
title: Distribuire, gestire e creare report in Microsoft Defender Antivirus
description: È possibile distribuire e gestire Microsoft Defender Antivirus con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo, PowerShell o WMI
keywords: distribuire, gestire, aggiornare, protezione, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a9cd04300e67f956b50f07c02f3dc00c515f02eb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691510"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Distribuire, gestire e creare report in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi distribuire, gestire e segnalare Microsoft Defender Antivirus in diversi modi.

Poiché il client Microsoft Defender Antivirus è installato come parte di base di Windows 10, la distribuzione tradizionale di un client agli endpoint non è applicabile.

Tuttavia, nella maggior parte dei casi sarà comunque necessario abilitare il servizio di protezione negli endpoint con Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender o Oggetti Criteri di gruppo, descritto nella tabella seguente.

Vedrai anche collegamenti aggiuntivi per:

- Gestione della protezione di Microsoft Defender Antivirus, inclusa la gestione degli aggiornamenti di prodotti e protezione
- Creazione di report sulla protezione di Microsoft Defender Antivirus

> [!IMPORTANT]
> Nella maggior parte dei casi, Windows 10 disabiliterà Microsoft Defender Antivirus se trova un altro prodotto antivirus in esecuzione e aggiornato. Devi disabilitare o disinstallare prodotti antivirus di terze parti prima che Microsoft Defender Antivirus funzioni. Se riattiva o installi prodotti antivirus di terze parti, Windows 10 disabilita automaticamente Microsoft Defender Antivirus.

Strumento|Opzioni di distribuzione (<a href="#fn2" id="ref2">2</a>)|Opzioni di gestione (configurazione e criteri a livello di rete o distribuzione di base) ([3](#fn3))|Opzioni di creazione di report  
---|---|---|---  
Microsoft Intune|[Aggiungere le impostazioni di endpoint protection in Intune](/intune/endpoint-protection-configure)|[Configurare le impostazioni di restrizione dei dispositivi in Intune](/intune/device-restrictions-configure)| [Usare la console di Intune per gestire i dispositivi](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Usare il [ruolo del sistema del sito punto di Endpoint Protection][] e abilitare Endpoint Protection con impostazioni client [personalizzate][]|Con [i criteri antimalware predefiniti][] e personalizzati e la gestione dei [client][]|Con l'area [di lavoro di monitoraggio di Configuration Manager predefinita e][] gli avvisi di posta [elettronica][]  
Criteri di gruppo e Active Directory (aggiunti a un dominio)|Usa un oggetto Criteri di gruppo per distribuire le modifiche alla configurazione e verificare che Microsoft Defender Antivirus sia abilitato.|Usare oggetti Criteri di gruppo (GPO) per configurare le opzioni di aggiornamento [per Microsoft Defender Antivirus][] e configurare Windows Defender [funzionalità][]|La creazione di report degli endpoint non è disponibile con Criteri di gruppo. È possibile generare un elenco di [Criteri di gruppo per determinare se le impostazioni][] o i criteri non vengono applicati
PowerShell|Distribuisci con Criteri di gruppo, Microsoft Endpoint Configuration Manager o manualmente nei singoli endpoint.|Utilizzare i cmdlet [Set-MpPreference] [e Update-MpSignature] disponibili nel modulo Defender.|Utilizzare i [cmdlet Get- appropriati disponibili nel modulo Defender][]
Strumentazione gestione Windows|Distribuisci con Criteri di gruppo, Microsoft Endpoint Configuration Manager o manualmente nei singoli endpoint.|Utilizzare il [metodo Set della classe MSFT_MpPreference e][] il metodo Update della MSFT_MpSignature [classe][]|Utilizzare la [MSFT_MpComputerStatus][] e il metodo get delle classi associate nel [provider WMIv2 Windows Defender][]
Microsoft Azure|Distribuire Microsoft Antimalware per Azure nel portale di Azure, usando la configurazione della macchina virtuale di Visual Studio o [i cmdlet di Azure PowerShell.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) È anche possibile [installare Endpoint Protection in Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Configurare [Microsoft Antimalware per macchine virtuali e servizi cloud con i cmdlet](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) di Azure PowerShell o usare esempi di [codice](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Usa [Microsoft Antimalware per macchine virtuali e servizi cloud con i cmdlet di Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) per abilitare il monitoraggio. È inoltre possibile esaminare i report di utilizzo in Azure Active Directory per determinare le attività sospette, incluso il [report][] Dispositivi probabilmente infetti e configurare uno strumento SIEM per segnalare gli eventi di Microsoft [Defender Antivirus][] e aggiungere tale strumento come app in AAD.

1. <span id="fn1" />La disponibilità di alcune funzioni e funzionalità, in particolare correlate alla protezione basata sul cloud, è diversa tra Microsoft Endpoint Manager (Current Branch) e System Center 2012 Configuration Manager. In questa raccolta, ci siamo concentrati su Windows 10, Windows Server 2016 e Microsoft Endpoint Manager (Current Branch). Vedi [Usare la protezione fornita dal cloud Microsoft in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) per una tabella che descrive le principali differenze. [(Torna alla tabella)](#ref2)
  
2.  <span id="fn2" />In Windows 10, Microsoft Defender Antivirus è un componente disponibile senza installazione o distribuzione di un altro client o servizio. Verrà abilitato automaticamente quando i prodotti antivirus di terze parti vengono disinstallati o non aggiornati ( ad eccezione di[Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)). La distribuzione tradizionale non è pertanto necessaria. La distribuzione qui si riferisce alla verifica che il componente Microsoft Defender Antivirus sia disponibile e abilitato su endpoint o server. [(Torna alla tabella)](#ref2)

3. <span id="fn3" />La configurazione delle funzionalità e della protezione, inclusa la configurazione degli aggiornamenti di prodotti e protezione, è descritta ulteriormente nella sezione Configurare le funzionalità di [Microsoft Defender Antivirus](configure-notifications-microsoft-defender-antivirus.md) in questa raccolta. [(Torna alla tabella)](#ref2)

[Ruolo del sistema del sito punto di Endpoint Protection]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[criteri antimalware predefiniti e personalizzati]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[gestione dei client]:  /configmgr/core/clients/manage/manage-clients
[abilitare Endpoint Protection con impostazioni client personalizzate]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Area di lavoro monitoraggio di Configuration Manager]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[avvisi di posta elettronica]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Metodo Set della classe MSFT_MpPreference]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Metodo Update della classe MSFT_MpSignature]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2 Provider]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get- Cmdlet disponibili nel modulo Defender]: /powershell/module/defender/
[Configurare le opzioni di aggiornamento per Microsoft Defender Antivirus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Configurare Windows Defender funzionalità]: configure-microsoft-defender-antivirus-features.md
[Criteri di gruppo per determinare se le impostazioni o i criteri non vengono applicati]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Dispositivi probabilmente infetti]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Eventi di Microsoft Defender Antivirus]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
---|---
[Distribuire e abilitare la protezione di Microsoft Defender Antivirus](deploy-microsoft-defender-antivirus.md) | Mentre il client viene installato come parte di base di Windows 10 e la distribuzione tradizionale non è applicabile, sarà comunque necessario abilitare il client sugli endpoint con Microsoft Endpoint Configuration Manager, Microsoft Intune o Oggetti Criteri di gruppo. 
[Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base](manage-updates-baselines-microsoft-defender-antivirus.md) | L'aggiornamento di Microsoft Defender Antivirus è in due parti: l'aggiornamento del client sugli endpoint (aggiornamenti del prodotto) e l'aggiornamento di Security intelligence (aggiornamenti della protezione). Puoi aggiornare Security intelligence in diversi modi, usando Microsoft Endpoint Configuration Manager, Criteri di gruppo, PowerShell e WMI.
[Monitorare e segnalare la protezione di Microsoft Defender Antivirus](report-monitor-microsoft-defender-antivirus.md) | È possibile usare Microsoft Intune, Microsoft Endpoint Configuration Manager, il componente aggiuntivo Conformità aggiornamenti per Microsoft Operations Management Suite o un prodotto SIEM di terze parti (utilizzando i registri eventi di Windows) per monitorare lo stato di protezione e creare report sulla protezione degli endpoint.