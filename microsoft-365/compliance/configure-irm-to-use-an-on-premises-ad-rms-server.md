---
title: Configurare IRM per l'uso di un server AD RMS locale
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare Information Rights Management (IRM) in Exchange Online per l'utilizzo di un server Active Directory Rights Management Service (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876121"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Configurare IRM per l'uso di un server AD RMS locale
  
Per l'utilizzo con le distribuzioni locali, Information Rights Management (IRM) in Exchange Online utilizza Active Directory Rights Management Services (AD RMS), una tecnologia di protezione delle informazioni in Windows Server 2008 e versioni successive. La protezione IRM viene applicata alla posta elettronica applicando un modello dei criteri dei diritti AD RMS a un messaggio di posta elettronica. I diritti sono allegati al messaggio stesso, in modo che la protezione si verifichi online e offline e all'interno e all'esterno del firewall dell'organizzazione.
  
In questo argomento viene illustrato come configurare IRM per utilizzare un server AD RMS. Per informazioni sull'uso delle nuove funzionalità per Office 365 Message Encryption con Azure Active Directory e Azure Rights Management, vedere le domande Office 365 Message Encryption [domande frequenti su Office 365 Message Encryption.](./ome-faq.yml)
  
Per ulteriori informazioni su IRM in Exchange Online, vedere [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 30 minuti

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Information Rights Management" nell'argomento [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions). 

- Il server AD RMS deve eseguire Windows Server 2008 o versioni successive. Per i dettagli sulla distribuzione di AD RMS, vedere l'articolo relativo all'[installazione di un cluster AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Per informazioni su come installare e configurare Windows PowerShell ed eseguire la connessione al servizio, vedere [Connessione a Exchange Online tramite Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo argomento, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di Exchange [in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>Come eseguire l'operazione?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Passaggio 1: Utilizzare la console AD RMS per esportare un dominio di pubblicazione trusted (TPD, trusted publishing domain) da un server AD RMS

Il primo passaggio è l'esportazione in un dominio di pubblicazione trusted da un server SD RMS locale ad un file XML. Il dominio di pubblicazione trusted contiene le impostazioni necessarie per utilizzare le funzionalità RMS:
  
- il certificato concessore di licenze server (SLC) utilizzato per la firma e la crittografia dei certificati e delle licenze

- gli URL utilizzati per la gestione delle licenze e la pubblicazione

- i modelli di criteri per i diritti di AD RMS creati con il certificato SLC specifico per quel dominio di pubblicazione trusted

Quando si importa il dominio di pubblicazione trusted, viene archiviato e protetto in Exchange Online.
  
1. Aprire la console Active Directory Rights Management Services, quindi espandere il cluster AD RMS.

2. Nell'albero della console, espandere **Criteri di attendibilità**, quindi fare clic su **Domini di pubblicazione trusted**.

3. Selezionare il certificato per il dominio che si desidera esportare nel riquadro dei risultati.

4. Nel riquadro **Azioni**, fare clic su **Esporta dominio di pubblicazione trusted**.

5. Nella casella **File del dominio di pubblicazione**, fare clic su **Salva con nome** per salvare il file in un percorso specifico sul computer locale. Immettere un nome file e assicurarsi di specificare l'estensione del nome file  `.xml` e quindi fare clic su **Salva**.

6. Nelle caselle **Password** e **Conferma password**, digitare una password complessa che sarà utilizzata per crittografare il file del dominio di pubblicazione trusted. Sarà necessario specificare questa password durante l'importazione del dominio di pubblicazione trusted nell'organizzazione di posta elettronica basata su cloud. 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Passaggio 2: utilizzare Exchange Management Shell per importare il disco di configurazione di Exchange Online

Dopo aver esportato il dominio di pubblicazione trusted in un file XML, è necessario importarlo in Exchange Online. Quando viene importato un dominio di pubblicazione trusted, vengono importati anche i modelli dell'organizzazione AD RMS. Quando viene importato il primo dominio di pubblicazione trusted, diventa quello predefinito per l'organizzazione basata su cloud. Se si importa un altro dominio di pubblicazione trusted, è possibile utilizzare l'opzione **Predefinito** per fare in modo che sia quello predefinito disponibile per gli utenti. 
  
Per importare il dominio di pubblicazione trusted, eseguire il seguente comando in Windows PowerShell:
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

È possibile ottenere i valori per i parametri  _ExtranetLicensingUrl_ e  _IntranetLicensingUrl_ nella console Active Directory Rights Management Services. Nell'albero della console, selezionare il cluster AD RMS. Gli URL per la gestione delle licenze vengono visualizzati nel riquadro dei risultati. Questi URL vengono utilizzati dai client di posta elettronica quando è necessario eseguire la decrittografia del contenuto e quando Exchange Online deve scegliere quale dominio di pubblicazione trusted utilizzare.
  
Quando si esegue questo comando, viene richiesta una password. Immettere la password specificata durante l'esportazione del dominio di pubblicazione trusted dal server AD RMS.
  
Ad esempio, il comando seguente importa il dominio di pubblicazione trusted, denominato dominio di pubblicazione trusted esportato tramite il file XML esportato dal server AD RMS e salvato nel desktop dell'account amministratore. Il parametro Name viene utilizzato per specificare un nome nel dominio di pubblicazione trusted.
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).
  
#### <a name="how-do-you-know-this-step-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver importato il dominio di pubblicazione trusted, eseguire il cmdlet **Get-RMSTrustedPublishingDomain** per recuperare i domini di pubblicazione trusted dell'organizzazione Exchange Online. Per i dettagli, vedere gli esempi in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Passaggio 3: Utilizzare Exchange Management Shell per distribuire un modello di criteri per i diritti AD RMS

Dopo avere importato il dominio di pubblicazione trusted, è necessario assicurarsi che sia distribuito un modello dei criteri dei diritti AD RMS. Un modello distribuito è visibile Outlook sul Web (in precedenza noto come Outlook Web App), che possono quindi applicare i modelli a un messaggio di posta elettronica.
  
Per tornare ad un elenco di tutti i modelli contenuti nel dominio di pubblicazione trusted predefinito, eseguire il comando riportato di seguito:
  
```powershell
Get-RMSTemplate -Type All | fl
```

Se il valore del parametro  _Type_ è  `Archived`, il modello non è visibile agli utenti. Solo i modelli distribuiti nel dominio di pubblicazione Outlook sul Web.
  
Per distribuire un modello, eseguire il comando riportato di seguito:
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Ad esempio, il comando seguente importa il modello Materiale aziendale riservato.
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) e [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).
  
**Il modello Non inoltrare**
  
Quando si importa il dominio di pubblicazione trusted predefinito dall'organizzazione locale in Exchange Online, viene importato un modello RMS denominato **Non inoltrare**. Per impostazione predefinita, questo modello viene distribuito quando si importa il dominio di pubblicazione trusted predefinito. Non è possibile utilizzare il cmdlet **Set-RMSTemplate** per modificare il modello **Non inoltrare**. 
  
Quando viene applicato il modello **Non inoltrare** ad un messaggio, solo i destinatari specificati nel messaggio possono leggerlo. Inoltre, i destinatari non possono eseguire le operazioni seguenti:
  
- Inoltrare il messaggio ad un altra persona.

- Copiare il contenuto dal messaggio.

- Stampare il messaggio.

> [!IMPORTANT]
> Il modello **Non inoltrare** non può impedire di copiare le informazioni in un messaggio con programmi di acquisizione schermo di terze parti, fotocamere o utenti che trascrivono manualmente le informazioni 
  
È possibile creare ulteriori modelli dei criteri dei diritti AD RMS sul server AD RMS dell'organizzazione locale per soddisfare i requisiti di protezione IRM. Se si creano altri modelli dei criteri dei diritti AD RMS, è necessario esportare nuovamente il dominio di pubblicazione trusted dal server AD RMS locale e aggiornare il dominio di pubblicazione trusted nell'organizzazione di posta elettronica basata su cloud.
  
#### <a name="how-do-you-know-this-step-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver distribuito un modello dei criteri dei diritti AD RMS, eseguire il cmdlet **Get-RMSTemplate** per verificare le proprietà del modello. Per i dettagli, vedere gli esempi in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Passaggio 4: Utilizzare Exchange Management Shell per abilitare IRM

Dopo aver importato il dominio di pubblicazione trusted e distribuito un modello RMS, è necessario abilitare IRM per l'organizzazione di posta elettronica basata su cloud eseguendo il comando riportato di seguito.
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).
  
#### <a name="how-do-you-know-this-step-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver abilitato IRM, eseguire il cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) per verificare la configurazione IRM nell'organizzazione Exchange Online.
  
## <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection2"> </a>

Per verificare di aver importato il dominio di pubblicazione trusted e abilitato IRM, attenersi alla seguente procedura:
  
- Utilizzare il cmdlet **Test-IRMConfiguration** per verificare la funzionalità IRM. Per informazioni dettagliate, vedere "Esempio 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Comporre un nuovo messaggio in Outlook sul Web e proteggerlo  tramite IRM selezionando l'opzione Imposta autorizzazioni dal menu esteso ( ![ Icona Altre opzioni ](../media/ITPro-EAC-MoreOptionsIcon.gif) ).