---
title: Distribuire, gestire e creare report Antivirus Microsoft Defender
description: È possibile distribuire e gestire Antivirus Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo, PowerShell o WMI
keywords: distribuire, gestire, aggiornare, proteggere, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 089a16bb76956cfb0441f8c3eeb5e70d80059845
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275181"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Distribuire, gestire e creare report Antivirus Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile distribuire, gestire e creare report Antivirus Microsoft Defender in diversi modi.

Poiché il client Antivirus Microsoft Defender viene installato come parte di base di Windows 10, la distribuzione tradizionale di un client agli endpoint non è applicabile.

Tuttavia, nella maggior parte dei casi sarà comunque necessario abilitare il servizio di protezione negli endpoint con Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender o Oggetti Criteri di gruppo, descritto nella tabella seguente.

Vedrai anche collegamenti aggiuntivi per:

- Gestione Antivirus Microsoft Defender protezione dei dati, inclusa la gestione degli aggiornamenti di prodotti e protezione
- Creazione di report sulla Antivirus Microsoft Defender protezione

> [!IMPORTANT]
> Nella maggior parte dei Windows 10 la Antivirus Microsoft Defender se trova un altro prodotto antivirus in esecuzione e aggiornato. È necessario disabilitare o disinstallare prodotti antivirus di terze parti prima Antivirus Microsoft Defender funzioneranno. Se si riattiva o si installano prodotti antivirus di terze parti, Windows 10 automaticamente Antivirus Microsoft Defender.

Strumento|Opzioni di distribuzione (<a href="#fn2" id="ref2">2</a>)|Opzioni di gestione (configurazione e criteri a livello di rete o distribuzione di base) ([3](#fn3))|Opzioni di creazione di report  
---|---|---|---  
Microsoft Intune|[Aggiungere le impostazioni di endpoint protection in Intune](/intune/endpoint-protection-configure)|[Configurare le impostazioni di restrizione dei dispositivi in Intune](/intune/device-restrictions-configure)| [Usare la console di Intune per gestire i dispositivi](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Utilizzare il [ruolo Endpoint Protection del sistema del sito][] e abilitare la Endpoint Protection con impostazioni client [personalizzate][]|Con [i criteri antimalware predefiniti][] e personalizzati e la gestione dei [client][]|Con l'area [di lavoro di monitoraggio di Configuration Manager predefinita e][] gli avvisi di posta [elettronica][]  
Criteri di gruppo e Active Directory (aggiunti a un dominio)|Utilizzare un oggetto Criteri di gruppo per distribuire le modifiche alla configurazione e verificare Antivirus Microsoft Defender abilitata.|Utilizzare oggetti Criteri di gruppo (GPO) per [configurare le opzioni][] di aggiornamento per Antivirus Microsoft Defender e configurare Windows Defender [funzionalità][]|La creazione di report degli endpoint non è disponibile con Criteri di gruppo. È possibile generare un elenco di [Criteri di gruppo per determinare se le impostazioni][] o i criteri non vengono applicati
PowerShell|Distribuire con Criteri di gruppo, Microsoft Endpoint Configuration Manager o manualmente nei singoli endpoint.|Utilizzare i cmdlet [Set-MpPreference] [e Update-MpSignature] disponibili nel modulo Defender.|Utilizzare i [cmdlet Get- appropriati disponibili nel modulo Defender][]
Strumentazione gestione Windows|Distribuire con Criteri di gruppo, Microsoft Endpoint Configuration Manager o manualmente nei singoli endpoint.|Utilizzare il [metodo Set della classe MSFT_MpPreference e][] il metodo Update della MSFT_MpSignature [classe][]|Usa la [MSFT_MpComputerStatus][] e il metodo get delle classi associate nel [provider WMIv2 Windows Defender wmiv2][]
Microsoft Azure|Distribuire Microsoft Antimalware per Azure nel portale [di Azure,](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)usando Visual Studio configurazione della macchina virtuale o Azure PowerShell cmdlet . È anche possibile [installare Endpoint Protection in Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Configurare [Microsoft Antimalware per macchine virtuali e servizi cloud con Azure PowerShell cmdlet o](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) usare esempi di [codice](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Utilizzare [Microsoft Antimalware per macchine virtuali e servizi cloud con Azure PowerShell cmdlet per](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) abilitare il monitoraggio. Puoi anche esaminare i report di utilizzo in Azure Active Directory per determinare le attività sospette, incluso il [report][] Dispositivi probabilmente infetti e configurare uno strumento SIEM per segnalare gli eventi di [Antivirus Microsoft Defender][] e aggiungere tale strumento come app in AAD.

1. <span id="fn1" />La disponibilità di alcune funzioni e funzionalità, in particolare correlate alla protezione basata sul cloud, è diversa tra Microsoft Endpoint Manager (Current Branch) e System Center Configuration Manager 2012. In questa raccolta, ci siamo concentrati su Windows 10, Windows Server 2016 e Microsoft Endpoint Manager (Current Branch). Per una tabella in cui vengono descritte le principali [differenze, vedere Usare](cloud-protection-microsoft-defender-antivirus.md) la protezione fornita dal cloud Microsoft in Antivirus Microsoft Defender. [(Torna alla tabella)](#ref2)
  
2.  <span id="fn2" />In Windows 10, Antivirus Microsoft Defender è un componente disponibile senza l'installazione o la distribuzione di un altro client o servizio. Verrà abilitato automaticamente quando i prodotti antivirus di terze parti vengono disinstallati o non aggiornati ( ad eccezione[di Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)). La distribuzione tradizionale non è pertanto necessaria. La distribuzione qui si riferisce alla Antivirus Microsoft Defender disponibile e abilitata su endpoint o server. [(Torna alla tabella)](#ref2)

3. <span id="fn3" />La configurazione delle funzionalità e della protezione, inclusa la [](configure-notifications-microsoft-defender-antivirus.md) configurazione degli aggiornamenti di prodotti e protezione, è descritta ulteriormente nella sezione Configurare Antivirus Microsoft Defender funzionalità di protezione in questa raccolta. [(Torna alla tabella)](#ref2)

[Endpoint Protection del sistema del sito del punto di distribuzione]: /configmgr/protect/deploy-use/endpoint-protection-site-role
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
[Configurare le opzioni di aggiornamento per Antivirus Microsoft Defender]: manage-updates-baselines-microsoft-defender-antivirus.md
[Configurare Windows Defender funzionalità]: configure-microsoft-defender-antivirus-features.md
[Criteri di gruppo per determinare se le impostazioni o i criteri non vengono applicati]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Dispositivi probabilmente infetti]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Antivirus Microsoft Defender eventi]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
---|---
[Distribuire e abilitare Antivirus Microsoft Defender protezione](deploy-microsoft-defender-antivirus.md) | Mentre il client viene installato come parte di base di Windows 10 e la distribuzione tradizionale non è applicabile, sarà comunque necessario abilitare il client sugli endpoint con Microsoft Endpoint Configuration Manager, Microsoft Intune o Oggetti Criteri di gruppo. 
[Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md) | Esistono due parti per l'aggiornamento Antivirus Microsoft Defender: l'aggiornamento del client sugli endpoint (aggiornamenti del prodotto) e l'aggiornamento di Security intelligence (aggiornamenti di protezione). È possibile aggiornare Security Intelligence in diversi modi, usando Microsoft Endpoint Configuration Manager, Criteri di gruppo, PowerShell e WMI.
[Monitorare e creare report sulla Antivirus Microsoft Defender protezione](report-monitor-microsoft-defender-antivirus.md) | È possibile utilizzare Microsoft Intune, Microsoft Endpoint Configuration Manager, il componente aggiuntivo Conformità aggiornamenti per Microsoft Operations Management Suite o un prodotto SIEM di terze parti (utilizzando i registri eventi di Windows) per monitorare lo stato di protezione e creare report sulla protezione degli endpoint.