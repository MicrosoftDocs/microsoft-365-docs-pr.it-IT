---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection impedisce agli utenti di stampare tramite stampanti non aziendali o una stampante USB non approvata.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809261"
---
# <a name="device-control-printer-protection"></a>Protezione stampante controllo dispositivo 

Microsoft Defender for Endpoint Device Control Printer Protection impedisce agli utenti di stampare tramite stampanti non aziendali o una stampante USB non approvata.

## <a name="licensing"></a>Licenze 

Prima di iniziare a usare Protezione stampante, è consigliabile [confermare l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) Per accedere e utilizzare Protezione stampante, è necessario disporre di quanto segue:

- Microsoft 365 E3 per la distribuzione di funzionalità/criteri 
- Microsoft 365 E5 per la creazione di report 

## <a name="permission"></a>Autorizzazione 

Per la distribuzione dei criteri in Intune, per distribuire i criteri tramite URI OMA, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi. È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli incorporati con queste autorizzazioni:  

- Ruolo Gestione criteri e profili. 
- Oppure un ruolo personalizzato con le autorizzazioni Crea/Modifica/Aggiornamento/Lettura/Eliminazione/Visualizzazione report attivate per i profili di configurazione dei dispositivi  
- O Amministratore globale

Per visualizzare i report di configurazione dei dispositivi, l'account deve disporre delle autorizzazioni per i report di visualizzazione. È possibile creare ruoli personalizzati o utilizzare i ruoli incorporati con queste autorizzazioni:  

- Amministratore della sicurezza globale
- Amministratore della sicurezza
- Ruolo con autorizzazioni di lettura per la sicurezza 

## <a name="prepare-your-endpoints"></a>Preparare gli endpoint

Verificare che i Windows 10 che si prevede di distribuire Protezione stampante soddisfino questi requisiti.

1. Partecipa al Programma Insider.

1. Devono essere installati gli aggiornamenti seguenti di Windows. 

    - Per Windows 1809: installare Windows aggiornamento [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 
    - Per Windows 1909: installare Windows aggiornamento [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Per Windows 2004 o versioni successive 
    
1. Se stai pianificando di distribuire i criteri tramite Criteri di gruppo, il dispositivo deve essere MDATP aggiunto; se si prevede di distribuire i criteri tramite MEM, il dispositivo deve essere aggiunto a Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Distribuire i criteri di protezione della stampante di Controllo dispositivo

Puoi distribuire i criteri tramite Criteri di gruppo o Intune.

| Titolo | Descrizione | Supporto CSP | Supporto oggetti Criteri di gruppo | Supporto basato sull'utente | Supporto basato su computer |
|:--|:--|:--|:--|:--|:--|
|**Abilita restrizioni stampa controllo dispositivo**|Impedire la stampa degli utenti tramite una stampante non aziendale|Sì|Sì|Sì|Sì|
|**Elenco dei dispositivi di stampa approvati connessi tramite USB**\*|Consenti stampante USB specifica|Sì|Sì|Sì|Sì|
|||||||

\* Questo criterio deve essere usato insieme a Abilita restrizioni di **stampa per il controllo dei dispositivi**
## <a name="deploy-policy-via-intune"></a>Distribuire i criteri tramite Intune 

Per Intune, attualmente Device Control Printer Protection supporta solo URI OMA.

**Scenario 1: impedire la stampa degli utenti tramite una stampante non aziendale** 

 - Applica criteri nel computer: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl 

- Applica criteri sull'utente: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser 

Stringa di supporto CSP con `` <enabled/>`` : 

:::image type="content" source="../../media/customeditrow.png" alt-text="riga di modifica personalizzata":::

**Scenario 2: consentire stampanti USB approvate specifiche**

- Applica criteri nel computer: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices 

- Applica criteri sull'utente: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser  

Stringa di supporto CSP con stampanti USB approvate tramite la proprietà "ApprovedUsbPrintDevices", ad `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` esempio: 

:::image type="content" source="../../media/editrow.png" alt-text="modifica riga":::

## <a name="deploy-policy-via-group-policy"></a>Distribuire criteri tramite Criteri di gruppo 

Se il dispositivo non è aggiunto a Intune, puoi anche distribuire i criteri tramite Criteri di gruppo. 

**Scenario 1: impedire la stampa degli utenti tramite una stampante non aziendale** 

- Applica criteri nel computer: 

    - Configurazione computer > modelli amministrativi > stampante: Abilita restrizioni stampa controllo dispositivo 

- Applica criteri sull'utente: 

    - Configurazione utente > modelli amministrativi > pannello di controllo > stampanti: Abilita restrizioni stampa controllo dispositivo 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="abilitare le restrizioni di stampa dei dispositivi":::
 

**Scenario 2: consentire stampanti USB approvate specifiche**

- Applica criteri nel computer: 

    - Configurazione computer > modelli amministrativi > stampante: elenco dei dispositivi di stampa approvati connessi tramite USB 

- Applica criteri sull'utente:  

    - Configurazione utente > modelli amministrativi > pannello di controllo > stampanti: Elenco dei dispositivi di stampa approvati connessi tramite USB 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="elenco dei dispositivi di stampa usb connessi approvati":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Visualizzare i dati di Protezione stampante di Controllo dispositivo in Microsoft Defender for Endpoint Portal 

Il [Microsoft 365 di sicurezza mostra](https://security.microsoft.com) la stampa bloccata dal criterio Protezione stampante di Controllo dispositivo precedente.
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="ricerca avanzata":::
