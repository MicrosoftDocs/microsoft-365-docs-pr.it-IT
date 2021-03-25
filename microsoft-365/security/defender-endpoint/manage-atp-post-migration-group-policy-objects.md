---
title: Gestire Microsoft Defender per Endpoint con oggetti Criteri di gruppo
description: Informazioni su come gestire Microsoft Defender per Endpoint con oggetti Criteri di gruppo
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, PowerShell, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: c21ac21f4369934375d44f5792afb874070ab074
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068541"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Gestire Microsoft Defender per Endpoint con oggetti Criteri di gruppo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> È consigliabile [usare Microsoft Endpoint Manager](https://docs.microsoft.com/mem) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (denominati anche endpoint). Endpoint Manager include [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e Microsoft Endpoint [Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[Altre informazioni su Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview)** 

È possibile usare oggetti Criteri di gruppo in Servizi di dominio Azure Active Directory per gestire alcune impostazioni in Microsoft Defender per Endpoint.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configurare Microsoft Defender per Endpoint con oggetti Criteri di gruppo

Nella tabella seguente sono elencate le varie attività che è possibile eseguire per configurare Microsoft Defender per Endpoint con Oggetti Criteri di gruppo.

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Gestire le impostazioni per gli oggetti utente e computer** <br/><br/>*Personalizzare gli oggetti Criteri di gruppo incorporati o creare oggetti Criteri di gruppo personalizzati e unità organizzative in base alle esigenze dell'organizzazione.*     |[Amministrare Criteri di gruppo in un dominio gestito di Servizi di dominio Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Configurare Microsoft Defender Antivirus** <br/><br/>*Configurare le funzionalità antivirus &, incluse le impostazioni dei criteri, le esclusioni, le correzioni e le analisi pianificate nei dispositivi dell'organizzazione (denominati anche endpoint).*   |[Usare le impostazioni di Criteri di gruppo per configurare e gestire Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Usare Criteri di gruppo per abilitare la protezione recapitata nel cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Gestire le regole di riduzione della superficie di attacco dell'organizzazione** <br/><br/>*Personalizza le regole di riduzione della superficie di attacco escludendo i file & cartelle o aggiungendo testo personalizzato agli avvisi di notifica visualizzati nei dispositivi degli utenti.* |[Personalizzare le regole di riduzione della superficie di attacco con oggetti Criteri di gruppo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Gestire le impostazioni di protezione da exploit**<br/><br/>*Puoi personalizzare le impostazioni di protezione degli exploit, importare un file di configurazione e quindi usare Criteri di gruppo per distribuire il file di configurazione.*  |[Personalizzare le impostazioni di protezione da exploit](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importare, esportare e distribuire configurazioni di protezione da exploit](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Usare Criteri di gruppo per distribuire la configurazione](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Abilitare Protezione di rete** per impedire ai dipendenti di usare app con contenuti dannosi su Internet <br/><br/>*Ti consigliamo di [usare prima la modalità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) di controllo per la protezione di rete in un ambiente di testing per vedere quali app verrebbero bloccate prima dell'implementazione.* |[Attivare la protezione di rete tramite Criteri di gruppo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*[L'accesso controllato](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) alle cartelle viene anche definito protezione antiransomware.*  |[Abilitare l'accesso controllato alle cartelle tramite Criteri di gruppo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configurare Microsoft Defender SmartScreen per** la protezione da siti e file dannosi su Internet.  |[Configurare i Criteri di gruppo di Microsoft Defender SmartScreen e le impostazioni di gestione dei dispositivi mobili (MDM) tramite Criteri di gruppo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Configurare la crittografia e BitLocker** per proteggere le informazioni sui dispositivi dell'organizzazione che eseguono Windows |[Impostazioni di Criteri di gruppo di BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Configurare Microsoft Defender Credential Guard per** la protezione dagli attacchi di furto di credenziali |[Abilitare Windows Defender Credential Guard tramite Criteri di gruppo](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare Microsoft Defender Security Center

Se non l'hai già fatto, configura **Microsoft Defender Security Center** ( ) per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva [https://securitycenter.windows.com](https://securitycenter.windows.com) dell'organizzazione. 

Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali in Microsoft Defender Security Center.

- [Panoramica di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Panoramica della gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard delle operazioni di sicurezza di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gestire Microsoft Defender per Endpoint con Intune](manage-atp-post-migration-intune.md)
