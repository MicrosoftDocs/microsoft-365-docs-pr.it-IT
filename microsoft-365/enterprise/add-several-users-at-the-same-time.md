---
title: Aggiungere più utenti contemporaneamente a Microsoft 365-Guida per gli amministratori
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'Informazioni su come aggiungere più utenti a Microsoft 365 for business da un elenco in un foglio di calcolo o in un altro file in formato CSV. Guardare un video su YouTube che spiega come aggiungere account a Microsoft 365. Alla fine di questo processo, ogni utente con un account avrà una cassetta postale di Microsoft 365. '
ms.openlocfilehash: 7629879990facbce57a6fbca1aa543471ad1b05b
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877213"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Aggiungere più utenti contemporaneamente a Microsoft 365-Guida per gli amministratori

Ogni persona del team ha bisogno di un account utente prima di poter accedere ai servizi Microsoft 365, ad esempio la posta elettronica e l'ufficio. Se il team è composto da numerose persone, è possibile aggiungere tutti gli account contemporaneamente da un foglio di calcolo di Excel o da un altro file salvato in formato CSV. [Non si è sicuri del formato CSV](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?
  
> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Aggiungere più utenti nell'interfaccia di amministrazione di Microsoft 365

1. Accedere a Microsoft 365 con l'account aziendale o dell'istituto di istruzione.

2. Nell'interfaccia di **amministrazione scegliere utenti** \> **attivi**.

3. Selezionare **Aggiungi più utenti**.

4. Nel riquadro **Importa più utenti** è possibile scegliere di scaricare un file CSV di esempio con o senza dati di esempio inseriti.

    Il foglio di calcolo deve includere le **stesse intestazioni di colonna** del campione 1 (nome utente, nome e così via). Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio il blocco note, e prendere in considerazione di lasciare tutti i dati solo nella riga 1 e immettere i dati solo nelle righe 2 e seguenti.

    Il foglio di calcolo deve includere anche i valori per il nome utente (ad esempio albertino@contoso.com) e per il nome visualizzato (ad esempio Albertino Mazzanti) di ogni utente.

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Immettere un percorso di file nella casella oppure scegliere **Sfoglia** per passare al percorso del file CSV e quindi scegliere **Verifica**.
  
    Se ci sono problemi con il file, i relativi messaggi vengono visualizzati nel riquadro. È anche possibile scaricare un file di log.

6. Nella finestra di dialogo **Imposta opzioni utente** è possibile impostare lo stato di accesso e scegliere la licenza del prodotto che verrà assegnata a tutti gli utenti.

7. Nella finestra di dialogo **Visualizza i risultati** è possibile scegliere di inviare i risultati a se stessi o ad altri utenti (le password saranno in testo normale) ed è possibile vedere quanti utenti sono stati creati e se è necessario acquistare altre licenze da assegnare ad alcuni nuovi utenti.

## <a name="next-steps"></a>Passaggi successivi

- Ora che queste persone hanno account, devono [scaricare e installare o reinstallare Microsoft 365 o Office 2016 su un PC o un Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658). Ogni persona del team può installare Microsoft 365 su un massimo di 5 PC o Mac.

- Ogni persona può anche [configurare le app di Office e la posta elettronica su un dispositivo mobile su un](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) massimo di 5 tablet e 5 telefoni, ad esempio iPhone, iPad, telefoni e Tablet Android. In questo modo, potrà modificare i file di Office ovunque vada.

    Per un elenco end-to-end dei passaggi di configurazione, vedere [configurare Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) .

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Ulteriori informazioni su come aggiungere utenti a Microsoft 365

### <a name="not-sure-what-csv-format-is"></a>Che cos'è il formato CSV?

Un file CSV è un file con valori delimitati da virgole. È possibile creare o modificare un file di questo tipo con qualsiasi editor di testo o foglio di calcolo, ad esempio Excel.
  
Come punto di partenza, è possibile scaricare questo [foglio di calcolo](https://www.microsoft.com/download/details.aspx?id=45485). Tenere presente che Microsoft 365 richiede intestazioni di colonna nella prima riga, quindi non sostituirle con qualcos'altro. 
  
Salvare il file con un nuovo nome e specificare il formato CSV.
  
![Immagine di come salvare un file in formato CSV in Excel](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
Quando si salva il file, è probabile che venga visualizzato un messaggio indicante che alcune caratteristiche della cartella di lavoro andranno perse in formato CSV. Non si tratta di un errore. Fare clic su **Sì** per continuare.
  
![Immagine del messaggio che potrebbe essere visualizzato in Excel in cui si chiede conferma per salvare il file in formato CSV](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Suggerimenti per la formattazione del foglio di calcolo

- **È necessario mantenere le stesse intestazioni di colonna del foglio di calcolo di esempio?** Sì. Il foglio di calcolo di esempio contiene intestazioni di colonna nella prima riga. Queste intestazioni sono obbligatorie. Per ogni utente che si desidera aggiungere a Microsoft 365, creare una riga sotto l'intestazione. Se si aggiungono, si modificano o si eliminano le intestazioni di colonna, Microsoft 365 potrebbe non essere in grado di creare gli utenti dalle informazioni contenute nel file.

- **Che cosa succede se non si hanno tutte le informazioni necessarie per ogni utente?** I campi obbligatori sono Nome utente e Nome visualizzato, pertanto non è possibile aggiungere un nuovo utente in assenza di tali informazioni. Se non si dispone di altre informazioni, ad esempio il fax, è possibile usare uno spazio seguito da una virgola per indicare che il campo deve rimanere vuoto.

- **Come può essere piccolo o grande il foglio di calcolo?** Il foglio di calcolo deve disporre di almeno due righe. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet.

- **Quali lingue è possibile utilizzare?** Quando si crea il foglio di calcolo, è possibile immettere le etichette delle colonne di dati degli utenti in qualsiasi lingua o carattere, ma non è necessario modificare l'ordine delle etichette, come illustrato nell'esempio. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.

- **Che cosa succede se si aggiungono utenti di paesi o aree geografiche diverse?** Creare un foglio di calcolo distinto per ogni area. È necessario eseguire i passaggi della procedura guidata Aggiunta utenti in blocco per ogni foglio di calcolo, specificando una singola area geografica per tutti gli utenti inclusi nel file in uso.

- **È previsto un limite per il numero di caratteri che è possibile usare?** La tabella seguente indica le etichette delle colonne dei dati utente e il numero massimo di caratteri che è possibile usare per ognuna nel foglio di calcolo di esempio.

|**Etichetta colonna dati utente**|**Numero massimo di caratteri**|
|:-----|:-----|
|Nome utente (obbligatorio)  <br/> |79 incluso il simbolo di chiocciola (@), nel formato name@domain. \<extension\> . L'alias dell'utente non può superare i 50 caratteri e il nome di dominio non può superare i 48 caratteri.  <br/> |
|Nome  <br/> |64  <br/> |
|Cognome  <br/> |64  <br/> |
|Nome visualizzato (obbligatorio)  <br/> |256  <br/> |
|Posizione  <br/> |64  <br/> |
|Reparto  <br/> |64  <br/> |
|Numero ufficio  <br/> |128  <br/> |
|Telefono ufficio  <br/> |64  <br/> |
|Telefono cellulare  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|Indirizzo  <br/> |1023  <br/> |
|Città  <br/> |128  <br/> |
|Provincia  <br/> |128  <br/> |
|CAP  <br/> |40  <br/> |
|Paese o area geografica  <br/> |128  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Si verificano ancora problemi quando si aggiungono utenti a Microsoft 365?

- **Verificare che il foglio di calcolo sia stato formattato correttamente.** Controllare le intestazioni di colonna per verificare che corrispondano a quelle del file di esempio. Assicurarsi di aver rispettato le regole relative al numero massimo di caratteri e di aver usato una virgola per separare i campi.

- **Se non si vedono subito i nuovi utenti in Microsoft 365, attendere qualche minuto.** È possibile che le modifiche apportate in tutti i servizi in Microsoft 365 possano richiedere un po' di tempo. 

## <a name="related-articles"></a>Articoli correlati

[Aggiungere gli utenti singolarmente o in blocco a Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)
