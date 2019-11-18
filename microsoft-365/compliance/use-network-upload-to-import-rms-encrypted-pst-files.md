---
title: Utilizzare il caricamento di rete per importare i file PST crittografati con RMS su Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Informazioni su come utilizzare il caricamento di rete per importare i file PST crittografati con RMS nelle cassette postali degli utenti in Office 365.
ms.openlocfilehash: c31658ead08fd1c72447f1182af28c32db421842
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686623"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Utilizzare il caricamento di rete per importare i file PST crittografati con RMS su Office 365

**Questo articolo è per gli amministratori. Si sta tentando di importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Utilizzare l'opzione caricamento di rete e il servizio di importazione di Office 365 per importare i file PST nelle cassette postali degli utenti. Caricamento di rete significa che si caricano i file PST un'area di archiviazione temporanea nel cloud Microsoft. Successivamente, il servizio di importazione di Office 365 copia i file PST dall'area di archiviazione nelle cassette postali degli utenti di destinazione. Una nuova funzionalità del servizio di importazione consente di crittografare i file PST prima che vengano caricati e archiviati nel cloud Microsoft. Questi file verranno decrittografati durante l'importazione verso le cassette postali dell'utente. 
  
Di seguito sono riportati i passaggi necessari per crittografare e importare i file PST nelle cassette postali di Office 365:
  
[Passaggio 1: configurare Azure Rights Management per l'importazione PST](#step-1-set-up-azure-rights-management-for-pst-import)

[Passaggio 2: generare una chiave di crittografia per l'importazione PST](#step-2-generate-an-encryption-key-for-pst-import)

[Passaggio 3: ottenere l'ID tenant RMS e l'URL delle licenze](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Passaggio 4: scaricare gli strumenti di importazione PST e copiare l'URL SAS](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Passaggio 5: crittografare e caricare i file PST in Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[Optional Passaggio 6: visualizzazione di un elenco dei file PST caricati in Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Passaggio 7: creare il file di mapping di importazione PST](#step-7-create-the-pst-import-mapping-file)

[Passaggio 8: creare un processo di importazione PST in Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> È necessario eseguire il passaggio 1 del passaggio 4 solo una volta per impostare e configurare l'organizzazione per crittografare e importare i file PST nelle cassette postali di Office 365. Dopo aver eseguito questa procedura, eseguire il passaggio 5 al passaggio 8 ogni volta che si desidera crittografare, caricare e importare un batch di file PST. 
  
Per ulteriori informazioni sull'importazione di dati in Office 365, vedere [Overview of import your organization PST files to office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in [Manage Role](https://go.microsoft.com/fwlink/p/?LinkId=730688)groups.
    
    Per creare processi di importazione nel centro sicurezza & conformità, è inoltre necessario che sia vero uno dei seguenti valori:
    
  - È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
  > [!TIP]
  > Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- È necessario archiviare i file PST che si desidera importare in Office 365 in un file server o in una cartella condivisa all'interno dell'organizzazione. Nel passaggio 5, è possibile eseguire Office 365 ImportTool, che consente di crittografare e caricare i file PST archiviati in questo file server o cartella condivisa in Office 365.
    
- Questa procedura prevede la copia e il salvataggio di una copia della chiave di crittografia, una chiave di archiviazione e di una serie di chiavi e URL di identificazione. Queste informazioni verranno utilizzate nel passaggio 5 per crittografare e caricare i file PST. Adottare le dovute precauzioni per proteggere questi file nello stesso in modo in cui vengono protette password o altre informazioni di sicurezza. Ad esempio, potrebbe essere necessario salvarli in un documento di Microsoft Word protetto da password oppure su un'unità USB crittografata. Vedere la sezione [Ulteriori informazioni](#more-information) per consultare un esempio di queste chiavi, ID e URL. 
    
- È possibile importare i file PST in una cassetta postale inattiva in Office 365. A tale scopo, specificare il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione PST. Per ulteriori informazioni, vedere [passaggio 7](#step-7-create-the-pst-import-mapping-file) . 
    
- In una distribuzione ibrida di Exchange, è possibile importare i file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione PST:
    
  - Specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **true** nel `IsArchive` parametro. 
    
    Per ulteriori informazioni, vedere [passaggio 7](#step-7-create-the-pst-import-mapping-file) . 
    
- Dopo aver importato i file PST in una cassetta postale di Office 365, l'impostazione di conservazione per la cassetta postale è attivata per una durata indefinita. Questo significa che i criteri di conservazione assegnati alla cassetta postale non verranno elaborati fino a quando non si disattiva il blocco di conservazione o si imposta una data per disattivare il blocco. Perché eseguire questa operazione? Se i messaggi importati in una cassetta postale sono obsoleti, potrebbero essere eliminati definitivamente (eliminati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Se si posiziona la cassetta postale su conservazione, il proprietario della cassetta postale consentirà di gestire i messaggi appena importati o di modificare le impostazioni di conservazione per la cassetta postale. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti sulla gestione del blocco di conservazione. 
    
- Se non è necessario crittografare i file PST prima di caricarli in Office 365, vedere [usare il caricamento di rete per importare i file PST in office 365](use-network-upload-to-import-pst-files.md).
    
- Per le domande frequenti sull'utilizzo del caricamento di rete per importare i file PST in Office 365, vedere [domande frequenti sull'importazione di file PST in office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Passaggio 1: configurare Azure Rights Management per l'importazione PST 

L'importazione PST utilizza la funzionalità di crittografia fornita dal servizio Azure Rights Management (Azure RMS) in Office 365. Questo consente di crittografare i file PST prima di caricarli in Office 365. 
  
La configurazione di Azure RMS per l'importazione PST è costituita da tre passaggi:
  
- [Attivazione di Azure RMS](#activating-azure-rms)
    
- [Configurazione di RMS in Exchange Online](#configuring-rms-in-exchange-online)
    
- [Installazione del client Active Directory RMS](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Attivazione di Azure RMS

Azure RMS è disabilitato per impostazione predefinita, ma l'utente o un altro amministratore dell'organizzazione potrebbe averlo attivato. Seguire le istruzioni sull' [attivazione di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) per installare e attivare la tecnologia DRM di Azure.
  
### <a name="configuring-rms-in-exchange-online"></a>Configurazione di RMS in Exchange Online

Dopo aver attivato il servizio Rights Management, il passaggio successivo consiste nell'impostare Information Rights Management (IRM) in Exchange Online per l'utilizzo di Azure RMS. Per ulteriori informazioni, vedere [configurazione di IRM per l'utilizzo di Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. [Connettersi a Exchange Online tramite Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Eseguire il seguente comando per impostare l'URL di condivisione della chiave RMS.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Utilizzare la tabella seguente per determinare il percorso di condivisione della chiave RMS corretta in base alla posizione dell'organizzazione.
    
    |**Posizione**|**Percorso di condivisione della chiave di RMS**|
    |:-----|:-----|
    |Nord America  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Unione Europea  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Asia  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Sud America  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 per il governo (Government Community Cloud)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> solo i clienti che hanno acquistato Office 365 per SKU governative (Government community Cloud) devono utilizzare questo percorso di condivisione della chiave RMS. 
  
    Ad esempio, questo comando consente di configurare il percorso di condivisione della chiave di RMS online in Exchange Online per un cliente che si trova in Nord America.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Eseguire il seguente comando per importare un dominio di pubblicazione trusted (Trusted Publishing Domain) da RMS online all'organizzazione di Office 365. 
    
    ```powershell
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    In un dominio TPD sono contenute le impostazioni necessarie per utilizzare le funzionalità RMS nell'organizzazione, tra cui la crittografia dei file PST.  
    
4. Eseguire il seguente comando per abilitare IRM per l'organizzazione di Office 365.
    
    ```powershell
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Installazione del client Active Directory RMS

L'ultimo passaggio in questa sezione è il download del client Rights Management Services (RMS) 2.1. Questo software contribuisce a proteggere l'accesso a Azure RMS e protegge le informazioni che scorrono attraverso applicazioni che utilizzano Azure RMS. Installare il client RMS nello stesso computer che verrà utilizzato per crittografare e caricare i file PST nel passaggio 5. 
  
1. Scaricare il [client del servizio Rights Management 2,1](https://www.microsoft.com/download/details.aspx?id=38396).
    
2. Eseguire la procedura guidata del client Rights Management Service 2.1 di Active Directory per installare il client.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Passaggio 2: generare una chiave di crittografia per l'importazione PST

Dopo aver configurato Azure RMS, il passaggio successivo consiste nel generare una chiave di crittografia (denominata chiave simmetrica) che verrà utilizzata per crittografare i file PST caricati in Office 365. Per eseguire questa operazione, aggiungere il servizio di importazione PST come entità di servizio in Azure Active Directory. L'aggiunta di questa applicazione come entità di servizio consentirà al servizio di importazione PST di eseguire l'autenticazione direttamente con Azure Active Directory quando si caricano i file PST crittografati nel percorso di archiviazione di Azure nel passaggio 5.
  
1. Avviare il modulo di Azure Active Directory per Windows PowerShell.
    
2. Eseguire il seguente comando per connettersi al servizio online Microsoft.
    
    ```powershell
    Connect-MsolService
    ```

3. Immettere le credenziali di un account amministratore nell'organizzazione di Office 365 e quindi fare clic su **OK**.
    
4. Eseguire il comando seguente per generare una chiave di crittografia (chiamare una chiave simmetrica). Sarà possibile farlo creando una nuova entità di protezione di crittografia PST.
    
    ```powershell
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    Il sistema visualizza la chiave simmetrica e le proprietà della nuova entità di protezione di crittografia PST.
    
    ![Copiare e salvare la chiave simmetrica che viene visualizzata](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Copiare la chiave simmetrica in un testo o file di Word. Come descritto in precedenza, prendere le dovute precauzioni per proteggere il file. Poiché si tratta dell'unica volta in cui la chiave simmetrica viene visualizzata, è consigliabile acquisire la schermata della finestra e salvarla nello stesso file.  
    
    > [!IMPORTANT]
    > Dopo aver creato l'entità di protezione di crittografia PST, non sarà possibile recuperare la chiave simmetrica utilizzando il cmdlet **Get-MsolServicePrincipal**. È per questo motivo che è importante salvare la chiave. 
  
Mantenere il modulo di Azure Active Directory per Windows PowerShell aperto e connesso al servizio Microsoft online. Si eseguirà un comando in questa finestra nel passaggio successivo.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Passaggio 3: ottenere l'ID tenant RMS e l'URL delle licenze

Il passaggio successivo consiste nell'ottenere l'ID tenant e l'URL della posizione di gestione delle licenze per il servizio Azure RMS per l'organizzazione. Copiare e salvare queste informazioni in uno stesso file che contiene la chiave simmetrica del passaggio 2. L'ID e l'URL verranno utilizzati nel passaggio 5 per crittografare i file PST.
  
1. Nel modulo di Azure Active Directory per Windows PowerShell (connesso al servizio Microsoft online), utilizzare il seguente comando per connettersi al servizio Azure RMS nell'organizzazione di Office 365.
    
    ```powershell
    Connect-AadrmService 
    ```

2. Immettere le credenziali di un account amministratore nell'organizzazione di Office 365 e quindi fare clic su **OK**.
    
3. Eseguire il seguente comando per visualizzare l'ID tenant per il servizio Azure RMS nell'organizzazione di Office 365.
    
    ```powershell
    Get-AadrmConfiguration | FL BPOSId
    ```

    Copiare e salvare il valore per la `BPOSId` proprietà. 
    
4. Eseguire il seguente comando per visualizzare il percorso di licenza per il servizio Azure RMS.
    
    ```powershell
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Copiare e salvare il valore per la `LicensingIntranetDistributionPointUrl` proprietà. 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Passaggio 4: scaricare gli strumenti di importazione PST e copiare l'URL SAS

Dopo aver configurato Azure RMS e aver ottenuto gli ID necessari per crittografare i file PST, il passaggio successivo consiste nel scaricare e installare gli strumenti che verranno eseguiti nel passaggio 5 per crittografare e caricare i file PST in Office 365. Questi strumenti sono lo strumento di AzCopy di Azure e lo strumento di crittografia dei dati di Office 365. È inoltre possibile copiare l'URL SAS per la propria organizzazione. Questo URL è una combinazione dell'URL di rete per la posizione di archiviazione di Azure nel cloud Microsoft per l'organizzazione e una chiave di firma di accesso condiviso (SAS). Questa chiave fornisce le autorizzazioni necessarie per caricare i file PST nel percorso di archiviazione di Azure. Salvarlo nello stesso file in cui sono state copiate le altre informazioni nel passaggio 2 e nel passaggio 3. Come indicato in precedenza, prendere precauzioni per proteggere l'URL SAS. 
  
> [!IMPORTANT]
> È necessario utilizzare Azure AzCopy versione 5,0 per caricare correttamente i file PST nel percorso di archiviazione di Azure. Le versioni più recenti dello strumento AzCopy non sono supportate per l'importazione di file PST in Office 365. Assicurarsi di scaricare lo strumento AzCopy dalla pagina **Carica file sulla rete** attenendosi alle procedure descritte in questo passaggio. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando le credenziali di un account amministratore nell'organizzazione di Office 365.
    
3. Nel riquadro sinistro fare clic su **governance dei dati** e quindi fare clic su **Importa**.
    
4. Nella pagina **Importa**, fare clic su **Vai al servizio di importazione**.
    
5. Nella pagina **Importa dati in Office 365** fare clic su **nuovo processo** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif)e quindi fare clic su **carica messaggi di posta elettronica (file PST)**.
    
6. Nel passaggio 2 della pagina **Carica file sulla rete** fare clic su **Mostra URL SAS caricamento di rete**.
    
7. Dopo aver visualizzato l'URL, copiarlo e salvarlo nel file in cui sono state salvate le altre chiavi. Assicurarsi di copiare l'URL completo. 
    
8. Nel passaggio 3, fare clic su **Scarica lo strumento di AzCopy di Azure** per scaricare e installare lo strumento di AzCopy di Azure. 
    
9. Nella finestra popup, fare clic su **Esegui** per installare lo strumento Azure AzCopy. 
    
    > [!IMPORTANT]
    > Assicurarsi di installare lo strumento di AzCopy di Azure nel percorso predefinito, che si `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` trova su un computer che esegue Windows a 64 bit. Ciò è dovuto al fatto che, quando si esegue O365ImportTool. exe nel passaggio 5, si cerca lo strumento AzCopy in questa posizione. 
  
10. Dopo aver installato lo strumento di Azure AzCopy, fare clic su **Scarica Office 365 Data Encryption and Import Tool**.
    
11. Nella finestra popup, fare clic su **Salva** \> con **nome** per salvare il file O365ImportTool. zip in una cartella del computer locale. 
    
12. Estrarre il file O365ImportTool.zip.
    
13. Fare clic su **Annulla** per chiudere la pagina **Carica file sulla rete** . 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Passaggio 5: crittografare e caricare i file PST in Office 365

Dopo aver completato il passaggio 1 al passaggio 4, è possibile utilizzare lo strumento O365ImportTool. exe per crittografare e caricare i file PST in Office 365. Questo strumento consente di crittografare i file PST e quindi di caricarli e archiviarli in una posizione di archiviazione di Azure nel cloud Microsoft. Per completare questo passaggio, è necessario che i file PST siano posizionati in una condivisione file o in un file server dell'organizzazione. In questa procedura, tale posizione viene definita anche come directory di origine. A ogni esecuzione dello strumento O365ImportTool.exe, è possibile specificare una directory di origine differente. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
2. Accedere alla directory nella quale è stato installato lo strumento O365ImportTool.exe durante il passaggio 4.
    
3. Eseguire il seguente comando per crittografare e caricare i file PST in Office 365.
    
    ```powershell
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori. Tenere presente che le informazioni dei passaggi precedenti vengono utilizzate nei valori di questi parametri.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Specifica la directory di origine nell'organizzazione che contiene i file PST che verranno caricati in Office 365.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Specifica il percorso di licenza per il servizio Azure RMS. Utilizzare il valore della `LicensingIntranetDistributionPointUrl` proprietà ottenuta nel passaggio 3. Tenere presente che il valore di questo parametro è racchiuso tra virgolette doppie ("").  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Specifica l'identità dell'organizzazione di Azure RMS. Utilizzare il valore della `BPOSId` proprietà ottenuta nel passaggio 3.  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Specifica la chiave simmetrica ottenuta nel passaggio 2. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Specifica se si desidera carica i file PST sulla rete o trasferirli su un disco rigido. Il valore `upload` indica che il caricamento dei file viene eseguito tramite la rete. Il valore `drive` indica che si sta spedendo il PST su un disco rigido.  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Specifica la destinazione in Office 365 in cui verrà caricato il file PST; si tratta del percorso di archiviazione di Azure per l'organizzazione. Il valore di questo parametro è costituito dall'URL di caricamento di rete dall'URL SAS copiato nel passaggio 4. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/><br/> **Suggerimento:** (facoltativo) è possibile specificare una sottocartella nel percorso di archiviazione di Azure per caricare i file PST crittografati. A tale scopo, aggiungere un percorso di sottocartella (dopo "ingestiondata") nell'URL di caricamento della rete. Nel primo esempio non viene specificata una sottocartella. Questo significa che il PST verrà caricato nella radice (denominata *ingestiondata* ) del percorso di archiviazione di Azure. Nel secondo esempio vengono caricati i file PST in una sottocartella (denominata *EncryptedPSTs* ) nel percorso di archiviazione di Azure.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> Oppure  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Specifica la chiave SAS per l'organizzazione. Il valore di questo parametro è costituito dalla chiave SAS dall'URL SAS copiato nel passaggio 4. Si noti che il primo carattere della chiave SAS è un punto interrogativo ("?"). Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Questa opzione opzionale consente di specificare la modalità ricorsiva in modo che lo strumento O365ImportTool. exe copierà i file PST che si trovano in sottocartelle nella directory di origine specificata dal `/srcdir:` parametro.  <br/><br/> **Nota:** Se si include questo parametro, i file PST nelle sottocartelle avranno un percorso di file diverso nel percorso di archiviazione di Azure dopo che sono stati caricati. È necessario specificare il percorso esatto nel file CSV creato al passaggio 7.           | `/recurse` <br/> |
   
    Di seguito è riportato un esempio di sintassi dello strumento O365ImportTool.exe nella quale verranno utilizzati i valori effettivi di ogni parametro:
    
    ```powershell
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento della crittografia e del caricamento dei file PST. Nel messaggio finale viene riportato il numero complessivo di file che sono stati crittografati e caricati.  
    
    > [!TIP]
    > Una volta eseguito il comando O365ImportTool.exe e verificato che tutti i parametri sono corretti, salvare una copia relativa alla sintassi della riga di comando nello stesso file (protetto) nel quale sono state copiate le informazioni ottenute nei passaggi precedenti. È quindi possibile copiare e incollare il comando in un prompt dei comandi ogni volta che si desidera eseguire lo strumento O365ImportTool. exe per crittografare e caricare i file PST in Office 365. Gli unici valori che potrebbe essere necessario modificare sono quelli per i `/srcdir:` parametri e `/upload-dest:` . 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Optional Passaggio 6: visualizzazione di un elenco dei file PST caricati in Office 365

Come passaggio facoltativo, è possibile installare e utilizzare Microsoft Azure Storage Explorer (che è uno strumento gratuito open source) per visualizzare l'elenco dei file PST caricati nel BLOB di Azure. Per eseguire questa operazione, sono disponibili tre validi motivi:
  
- Verificare che i file PST dalla cartella condivisa o dal server di file dell'organizzazione siano stati correttamente caricati nel BLOB di Azure.

- Verificare che i file PST siano crittografati. I file PST crittografati `.pfile` hanno un'estensione aggiunta al nome file PST; ad esempio, `pilarp.pst.pfile`.
    
- Verificare il nome del file (e il percorso della sottocartella se ne è stato incluso uno) per ognuno di essi. Ciò è particolarmente utile quando si crea il file di mapping PST nel passaggio successivo poiché è necessario specificare sia il nome del file sia il percorso della cartella per ogni file PST. La verifica di questi nomi consente di ridurre i potenziali errori nel file di mapping PST.
    
Microsoft Azure Storage Explorer è in anteprima. 
  
 > [!IMPORTANT]
>  Non è possibile utilizzare l'esploratore di archiviazione di Azure per caricare o modificare i file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 è l'utilizzo di AzCopy. Inoltre, non è possibile eliminare i file PST caricati nel BLOB di Azure. Se si tenta di eliminare un file PST, si riceve un errore relativo all'assenza delle autorizzazioni necessarie. Tenere presente che tutti i file PST vengono eliminati automaticamente dall'area di archiviazione di Azure. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
Per installare Azure Storage Explorer e connettersi all'area di archiviazione di Azure:
  
1. Scaricare e installare lo [strumento Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Avviare Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **account di archiviazione** nel riquadro sinistro, quindi fare clic su **Connetti a spazio di archiviazione di Azure**. 
    
    ![Fare clic con il pulsante destro del mouse su account di archiviazione e quindi scegliere Connetti a archiviazione](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Nella casella in **connessione a spazio di archiviazione di Azure**, incollare l'URL SAS ottenuto nel passaggio 4, quindi fare clic su **Avanti**. 
    
    ![Incollare l'URL SAS nella casella della pagina di archiviazione per la connessione ad Azure](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. Nella pagina **Riepilogo connessione** è possibile esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**. 
    
5. In **account di archiviazione**espandere il nodo **(Service SAS)** e quindi espandere il nodo **contenitori BLOB** . 
    
6. Fare clic con il pulsante destro del mouse su **ingestiondata**, quindi selezionare **Apri editor contenitori BLOB**.
    
    ![Fare clic con il pulsante destro del mouse su ingestiondata, quindi selezionare Apri editor contenitori BLOB](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Viene visualizzata l'area di archiviazione di Azure, con un elenco dei file PST caricati nel passaggio 5.
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Al termine dell'utilizzo di Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **ingestiondata**e quindi scegliere Disconnetti per disconnettersi dall' **area di archiviazione** di Azure. In caso contrario, verrà visualizzato un errore al successivo tentativo di associazione. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Passaggio 7: creare il file di mapping di importazione PST

Dopo che i file PST sono stati crittografati e caricati nel percorso di archiviazione di Azure per l'organizzazione di Office 365, il passaggio successivo consiste nel creare un file con valori delimitati da virgole (CSV) che specifichi le cassette postali degli utenti a cui verranno importati i file PST. È necessario inviare il file CSV nel passaggio successivo a quello di creazione del processo di importazione PST.
  
1. [Scaricare una copia del file di mapping di importazione PST](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
2. Aprire o salvare il file CSV nel computer locale. Nell'esempio seguente viene visualizzato un file di mapping di importazione PST completo (aperto nel Blocco note). È molto più facile usare Microsoft Excel per modificare il file CSV.
    
    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    Nella prima riga o in quella dell'intestazione del file CSV vengono elencati i parametri che verranno usati dal servizio di importazione PST per importare i file PST nelle cassette postali dell'utente. Ogni nome di parametro è separato da una virgola. Ogni riga al di sotto di quella dell'intestazione riporta i valori del parametro che consentono di importare un file PST in una cassetta postale specifica. È necessaria una riga per ogni file PST da importare nella cassetta postale di un utente. Assicurarsi di sostituire i dati segnaposto nel file di mapping con i dati effettivi.
    
    > [!NOTE]
    > Non apportare modifiche nella riga di intestazione, compresi i parametri SharePoint. Questi verranno ignorati durante il processo di impostazione PST. 
  
3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio Office 365 in cui verranno importati i dati. Per importare i file PST nelle cassette postali `Exchange`degli utenti, utilizzare.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Specifica il percorso della cartella nel percorso di archiviazione di Azure in cui sono stati caricati i file PST nel passaggio 5.  <br/>  Se non è stato incluso un nome di sottocartella facoltativo nell'URL di rete `/upload-dest:` nel parametro del passaggio 5, lasciare vuoto questo parametro nel file CSV. Se è stato incluso un nome di sottocartella, specificarlo in questo parametro. Il valore di questo parametro è distinzione tra maiuscole e minuscole. In entrambi i casi, *non* includere "ingestiondata" nel valore del `FilePath` parametro.  <br/> <br/>**Importante:** Il caso del nome del percorso del file deve essere lo stesso che è stato utilizzato se è stato incluso un nome di sottocartella facoltativo nell'URL SAS `/upload-dest:` nel parametro del passaggio 5. Ad esempio, se si utilizza `EncryptedPSTs` il nome della sottocartella nel passaggio 5 e quindi si `encryptedpsts` utilizza il `FilePath` parametro nel file CSV, l'importazione del file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambe le istanze.           |(lasciare vuoto)  <br/> Oppure  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato nella cassetta postale.  Il valore di questo parametro è distinzione tra maiuscole e minuscole. Poiché i file PST caricati nel percorso di archiviazione di Azure sono crittografati, viene `.pfile` aggiunta un'estensione al nome file PST. È necessario aggiungere l' `.pfile` estensione al nome dei file pst nel file CSV.  <br/><br/> **Importante:** Il caso del nome del file PST nel file CSV deve corrispondere al file PST caricato nel percorso di archiviazione di Azure nel passaggio 5. Ad esempio, se si utilizza `annb.pst.pfile` il `Name` parametro nel file CSV, ma il nome del file pst effettivo è `AnnB.pst`, l'importazione per il file PST avrà esito negativo. Assicurarsi che il nome del file PST nel documento CSV utilizzi lo stesso caso del file PST effettivo.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale nella quale verrà importato il file PST.   <br/> Per importare un file PST in una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere questo GUID, eseguire il seguente comando di PowerShell in Exchange Online:`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **Nota:** In alcuni casi, è possibile disporre di più cassette postali con lo stesso indirizzo di posta elettronica, in cui una cassetta postale è una cassetta postale attiva e l'altra è in uno stato di eliminazione temporanea (o inattivo). In questi casi, è necessario specificare il GUID della cassetta postale per identificare in modo univoco la cassetta postale in cui importare il file PST. Per ottenere questo GUID per le cassette postali attive, eseguire il seguente `Get-Mailbox - <identity of active mailbox> | FL Guid`comando di PowerShell:. Per ottenere il GUID per le cassette postali eliminate temporaneamente (o inattive), eseguire il comando seguente.`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:  <br/> Valore **false** Importa il file PST nella cassetta postale principale dell'utente.  <br/> **Vero** Importa il file PST nella cassetta postale di archiviazione dell'utente.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **Nota:** Per importare un file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale, è sufficiente specificare **true** per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale `Mailbox` locale dell'utente per il parametro.           | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali a cui è stato importato il file PST.  <br/>  Se si omette questo parametro, il file PST verrà importato in una nuova cartella denominata **importata** che si trova a livello di radice della cassetta postale (allo stesso livello della cartella posta in arrivo e delle altre cartelle di cassette postali predefinite).  <br/>  Se si specifica `/`, gli elementi del file pst verranno importati direttamente nella cartella posta in arrivo dell'utente.  <br/>  Se si specifica `/<foldername>`, gli elementi del file pst verranno importati in una sottocartella denominata * \<FolderName\> * . Ad esempio, se è stato `/ImportedPst`utilizzato, gli elementi verrebbero importati in una sottocartella denominata **ImportedPst**. Questa sottocartella sarà disponibile nella cartella posta in arrivo dell'utente.  <br/><br/> **Suggerimento:** Valutare l'esecuzione di alcuni batch di test per sperimentare questo parametro in modo da poter determinare il percorso della cartella migliore in cui importare i file di PST.           |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro facoltativo consente di specificare un valore numerico per la tabella codici da utilizzare per l'importazione dei file PST nel formato di file ANSI. Questo parametro viene utilizzato per l'importazione di file PST dalle organizzazioni cinesi, giapponesi e coreane (CJK), in quanto generalmente utilizzano un set di caratteri a doppio byte (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano i caratteri DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle vengono spesso alterati dopo l'importazione. Per un elenco dei valori supportati da utilizzare per questo parametro, vedere [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/><br/> **Nota:** Come indicato in precedenza, si tratta di un parametro facoltativo e non è necessario includerlo nel file CSV. In alternativa, è possibile includerla e lasciare il valore vuoto per una o più righe.           |(lasciare vuoto)  <br/> Oppure  <br/>  `932`(ovvero l'identificatore di tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Passaggio 8: creare un processo di Importazione PST in Office 365

L'ultimo passaggio consiste nel creare il processo di importazione PST nel servizio di importazione di Office 365. Come descritto in precedenza, verrà inviato il file di mapping di importazione PST creato al passaggio 7. Dopo aver creato il nuovo processo, il servizio di importazione utilizzerà le informazioni contenute nel file di mapping per annullare la crittografia e importare i file PST (caricati in Office 365 nel passaggio 5) nella cassetta postale utente specificata. 
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando le credenziali di un account amministratore nell'organizzazione di Office 365.
    
3. Nel riquadro sinistro fare clic su **governance dei dati** e quindi fare clic su **Importa**.
    
4. Nella pagina **Importa**, fare clic su **Vai al servizio di importazione**.
    
5. Nella pagina **Importa dati in Office 365** fare clic su **nuovo processo**![Aggiungi icona](media/ITPro-EAC-AddIcon.gif)e quindi fare clic su **carica messaggi di posta elettronica (file PST)**.
    
6. Nella pagina **Carica file sulla rete**, fare clic sulle caselle di controllo **Ho effettuato il caricamento dei file** e **Ho accesso al file di mapping**, quindi selezionare **Avanti**.  
    
7. Immettere un nome per il processo di importazione PST e fare clic su **Avanti**.
    
8. Fare **** ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per selezionare il file di mapping PST creato al passaggio 7. 
    
9. Una volta visualizzato il nome del file CSV nell'elenco, selezionarlo e fare clic su **Convalida** per verificare se nel file CSV sono presenti errori.  
    
    > [!NOTE]
    > Come spiegato in precedenza, quando i file PST sono crittografati `.pfile` , viene aggiunta un'estensione al nome file PST. È necessario aggiungere l' `.pfile` estensione al nome dei file pst nel file CSV. In caso contrario, la convalida del file CSV avrà esito negativo. 
  
    Il file CSV deve essere convalidato per creare un processo di importazione PST. Se la convalida ha esito negativo, fare clic sul collegamento **Non valido** nella colonna **Stato**. Viene aperta una copia del file di mapping di importazione PST e viene visualizzato un messaggio di errore per ogni riga del file con errore. 
    
10. Quando il file di mapping PST viene convalidato, leggere i termini e le condizioni, quindi fare clic sulla casella di controllo.
    
11. Fare clic su **Fine** per inviare il processo. 
    
    Il processo viene visualizzato nell'elenco dei processi di importazione PST nella pagina **Importa dati in Office 365** . 
    
12. Selezionare il processo e fare **clic su**![Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) l'icona Aggiorna per aggiornare le informazioni sullo stato visualizzate nel riquadro dei dettagli. 
    
13. In quest'ultimo, fare clic su **Visualizza dettagli** per visualizzare lo stato più recente del processo selezionato. 
 
## <a name="more-information"></a>Altre informazioni

- Perché importare i file PST in Office 365?
    
  - È un ottimo modo per eseguire la migrazione della posta elettronica dell'organizzazione a Office 365.
    
  - In questo modo, è possibile soddisfare le esigenze di conformità dell'organizzazione, permettendo all'utente di:
    
  - Abilitare le cassette postali di archiviazione per fornire agli altri utenti ulteriore spazio di archiviazione per la cassetta postale.
    
  - Bloccare le cassette postali per preservarne i contenuti.
    
  - Usare gli strumenti di Microsoft eDiscovery per cercare contenuti nelle cassette postali.
    
  - Utilizzare criteri di conservazione per controllare la durata di conservazione dei contenuti della cassetta postale.
    
  - Eseguire una ricerca nel registro di controllo di Office 365 per gli eventi relativi alle cassette postali.
    
  - Il servizio offre protezione da perdita dei dati. I file PST che vengono importati nelle cassette postali di Office 365 ereditano le funzionalità di disponibilità elevata di Exchange Online, anziché l'archiviazione dei dati nel computer di un utente.
    
  - I dati sono disponibili per l'utente da tutti i dispositivi in quanto vengono memorizzati nel cloud.
    
- Di seguito è riportato un esempio delle chiavi, degli ID e degli URL ottenuti nei passaggi 2, 3 e 4. In questo esempio viene inoltre contenuta la sintassi del comando eseguito nello strumento O365ImportTool. exe per crittografare e caricare i file PST in Office 365. Adottare le dovute precauzioni per proteggere tali file nello stesso in modo in cui vengono protette password o altre informazioni di sicurezza.
    
  ```text
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- Come spiegato in precedenza, il servizio di importazione di Office 365 attiva l'impostazione di conservazione (per una durata indefinita) dopo l'importazione dei file PST in una cassetta postale. Questo significa che la proprietà *RentionHoldEnabled* è impostata `True` in modo che il criterio di conservazione assegnato alla cassetta postale non venga elaborato. In questo modo il proprietario della cassetta postale è in grado di gestire i messaggi appena importati impedendo l'eliminazione o l'archiviazione dei messaggi meno recenti. Di seguito sono riportati alcuni passaggi che è possibile eseguire per gestire questo blocco di conservazione: 
    
  - Dopo un determinato periodo di tempo, è possibile disattivare il blocco di conservazione eseguendo il `Set-Mailbox -RetentionHoldEnabled $false` comando. Per le istruzioni, vedere [posizionare una cassetta postale sul blocco di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - È possibile configurare il blocco di conservazione in modo che sia disattivata in futuro. A tale scopo, eseguire il `Set-Mailbox -EndDateForRetentionHold <date>` comando. Ad esempio, presupponendo che la data odierna sia il 1 ° giugno 2016 e che si desideri disattivare il blocco di conservazione in 30 giorni, è necessario `Set-Mailbox -EndDateForRetentionHold 7/1/2016`eseguire il comando seguente:. In questo scenario, si lascerà la proprietà *RentionHoldEnabled* impostata su `True`. Per ulteriori informazioni, vedere [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - È possibile modificare le impostazioni per i criteri di conservazione assegnati alla cassetta postale, in modo che gli elementi meno recenti importati non vengano immediatamente eliminati o spostati nella cassetta postale di archiviazione dell'utente. Ad esempio, è possibile estendere l'età di conservazione per un criterio di eliminazione o di archiviazione assegnato alla cassetta postale. In questo scenario, è necessario disattivare il blocco di conservazione sulla cassetta postale dopo aver modificato le impostazioni del criterio di conservazione. Per ulteriori informazioni, vedere [configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
