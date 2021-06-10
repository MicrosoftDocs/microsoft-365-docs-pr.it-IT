---
title: Riferimento ai suggerimenti per i criteri di prevenzione della perdita dei dati
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: Informazioni su come aggiungere un suggerimento per i criteri a un criterio di prevenzione della perdita dei dati (DLP) informare un utente che sta lavorando con contenuto in conflitto con un criterio DLP.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086760"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Riferimento ai suggerimenti per i criteri di prevenzione della perdita dei dati

I suggerimenti per i criteri DLP in Outlook Web Access sono supportati per tutte le condizioni, le eccezioni e le azioni applicabili Exchange un carico di lavoro in un criterio DLP ad eccezione delle seguenti:

**Condizioni:**

- Sender Is
- Sender Domain Is
- Il destinatario è un membro di
- L'intestazione contiene parole o frasi
- L'intestazione corrisponde ai modelli
- La dimensione del documento è uguale o maggiore di
- Il tipo di messaggio è
- La priorità del messaggio è
- Il set di caratteri del contenuto contiene parole
- L'oggetto o il corpo contiene parole o frasi
- L'oggetto o il corpo corrisponde a modelli
- Il set di caratteri del contenuto contiene parole
- Il contenuto viene ricevuto da
- Il mittente ha ignorato il suggerimento per i criteri
- La dimensione del messaggio è uguale o maggiore di
- L'attributo Sender AD contiene parole o frasi
- L'attributo Ad mittente corrisponde ai modelli
- Il contenuto del documento contiene parole o frasi
- Il contenuto del documento corrisponde a modelli

**Azioni:**

- Inoltrare il messaggio per l'approvazione al responsabile del mittente
- Inoltrare il messaggio per l'approvazione a responsabili approvazione specifici
- Reindirizzare il messaggio a utenti specifici
- Aggiungere destinatari alla casella A
- Aggiungere destinatari alla casella Cc
- Aggiungere destinatari alla casella Ccn
- Aggiungere il manager del mittente come destinatario
- Aggiungere la dichiarazione di non responsabilità HTML
- Anteporre l'oggetto di posta elettronica
- Rimuovere la crittografia dei messaggi di O365 e la protezione dei diritti

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 e versioni successive supporta la visualizzazione di suggerimenti sui criteri solo per alcune condizioni ed eccezioni

Attualmente, Outlook 2013 e versioni successive supporta la visualizzazione di suggerimenti sui criteri per i criteri che non contengono alcuna condizione o eccezione a parte le condizioni indicate di seguito e le eccezioni corrispondenti:

- Il contenuto contiene (funziona solo per i tipi di informazioni riservate. Le etichette di riservatezza non sono supportate)
- Il contenuto è condiviso

Tieni presente che tutte le condizioni funzionano per i messaggi di posta elettronica creati Outlook'app client, in cui corrisponderanno al contenuto e applieranno azioni di protezione sul contenuto. Tuttavia, la visualizzazione di suggerimenti per i criteri per gli utenti non è supportata per tutte le condizioni utilizzate oltre a quelle indicate in precedenza.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 e versioni successive e le app Office desktop che mostrano suggerimenti sui criteri solo per alcuni tipi di informazioni riservate

L'elenco dei tipi di informazioni riservate predefiniti che verranno rilevati per visualizzare i suggerimenti per i criteri DLP in Outlook sul desktop (2013 e versioni successive) e nelle app Office (Word, Excel, PowerPoint) sul desktop sono i seguenti:

- Numero di registrazione ABA
- Argentina - Numero di identità nazionale (DNI)
- Australia - Numero di conto bancario
- Australia - Numero di tessera sanitaria
- Australia - Numero di passaporto
- Australia - Identificativo fiscale
- Azure DocumentDB Auth Key  
- Stringa di connessione del database IAAS di Azure e stringa di connessione SQL azure  
- Azure IoT Stringa di connessione  
- Password dell'impostazione di pubblicazione di Azure  
- Stringa di connessione della cache di Azure Redis  
- Firma di accesso condiviso di Azure  
- Stringa di connessione bus di servizio Azure  
- Archiviazione di Azure Chiave account  
- Archiviazione di Azure Chiave account (generica)  
- Belgio - Numero nazionale
- Numero CPF Brasile
- Brasile - Codice fiscale persone giuridiche (CNPJ)
- 	Carta d'identità (Brasile) (RG)
- Canada - Numero di conto bancario
- Canada - Numero della patente di guida
- Canada - Codice del servizio sanitario
- Canada - Numero di passaporto
- Canada - Numero di identificazione sanitaria personale (PHIN)
- Canada - Numero di assicurazione sociale
- 	Cile - Numero di carta di identità
- 	Numero carta di identità per residenti in Cina (RPC)
- Numero di carta di credito
- Numero di carta di identità della Croazia  
- Numero di identificazione personale (OIB) - Croazia  
- Numero di identità personale ceco  
- Codice PIN - Danimarca
- Numero della Drug Enforcement Agency (DEA)
- Unione Europea - Numero di carta di debito
- Numero di patente di guida UE  
- Numero di identificazione nazionale DELL  
- Numero di passaporto UE  
- CODICE SSN (EU Social Security Number) o ID equivalente  
- Codice fiscale UE (TIN)  
- Finland National ID
- Finlandia - Numero di passaporto
- Francia - Numero della patente di guida
- Francia - Carta d'identità nazionale (CNI)
- Francia - Numero di passaporto
- Francia - Numero di previdenza sociale (INSEE)
- Germania - Numero della patente di guida
- Germania - Numero di passaporto
- Germania - Numero carta di identità
- Carta d'identità (Grecia)  
- Hong Kong - Numero di carta di identità (HKID)
- India - Numero di conto permanente (PAN)
- India - Numero di identificazione univoco (Aadhaar)
- Indonesia - Numero di carta di identità (KTP)
- Numero di conto bancario internazionale (IBAN)
- Classificazione internazionale delle malattie (ICD-10-CM)  
- Classificazione internazionale delle malattie (ICD-9-CM)  
- Indirizzo IP
- Irlanda - Numero personale di servizio pubblico (PPS) 
- Israele - Numero di conto bancario
- Carta di identità (Israele)
- Italia - Numero della patente di guida
- Giappone - Numero di conto bancario
- Giappone - Numero della patente di guida
- Giappone - Numero di passaporto
- Giappone - Numero di registrazione dei residenti
- Giappone - Numero di assicurazione sociale (SIN)
- Numero carta di residenza giapponese
- Malaysia Identity Card Number
- Paesi Bassi - Numero di servizio cittadino (BSN)  
- Nuova Zelanda - Numero del Ministero della Sanità
- Norvegia - Numero di identificazione  
- Filippine - Numero ID multifunzione unificato
- Carta di identità - Polonia
- ID nazionale Polonia (PESEL)
- Passaporto Polonia
- Portogallo - Numero di carta del cittadino
- Arabia Saudita - Identificativo nazionale
- Singapore - Numero di carta di identità di registrazione nazionale (NRIC)
- Sudafrica - Numero di identificazione
  
- Corea del Sud - Numero di registrazione dei residenti
- Spagna - Numero di previdenza sociale (SSN)
- SQL Server Stringa di connessione  
- Svezia - Identificativo nazionale
- Svezia - Numero di passaporto
- Codice SWIFT
- Taiwan National ID
- 	Taiwan - Numero di passaporto
- Taiwan Resident Certificate (ARC/TARC)
- Codice di identificazione della popolazione thai
- Numero di identificazione nazionale turco
- Regno Unito - Numero della patente di guida
- Regno Unito - Numero di iscrizione alle liste elettorali
- Regno Unito - Codice del servizio sanitario nazionale
- Regno Unito - Numero di assicurazione nazionale (NINO)
- Stati Uniti/Regno Unito - Numero di passaporto
- Stati Uniti - Numero di conto bancario
- Stati Uniti - Numero della patente di guida
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

Si noti che i tipi di informazioni riservate personalizzati sono supportati anche per i suggerimenti sui criteri DLP oltre ai tipi di informazioni riservate predefiniti precedenti.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Prevenzione della perdita di dati nei dispositivi endpoint supporta suggerimenti sui criteri solo per alcuni tipi di informazioni riservate

L'elenco dei tipi di informazioni riservate predefiniti che verranno rilevati nei documenti che risiedono nei dispositivi endpoint è il seguente:

- Numero di registrazione ABA 
- Argentina - Numero di identità nazionale (DNI) 
- Australia - Numero di conto bancario 
- Australia - Numero di tessera sanitaria 
- Australia - Numero di passaporto 
- Australia - Identificativo fiscale 
- Numero di azienda australiano 
- Numero società australiano 
- Austria Driver's License Number 
- Carta d'identità Austria 
- Austria - Numero di passaporto 
- Austria - Numero di previdenza sociale 
- Austria Tax Identification Number 
- Numero di imposta sul valore aggiunto (IVA) austria 
- Azure DocumentDB Auth Key 
- Stringa di connessione del database IAAS di Azure e stringa di connessione SQL azure 
- Azure IoT Stringa di connessione 
- Password dell'impostazione di pubblicazione di Azure 
- Stringa di connessione della cache di Azure Redis 
- Firma di accesso condiviso di Azure 
- Stringa di connessione bus di servizio Azure 
- Archiviazione di Azure Chiave account 
- Archiviazione di Azure Chiave account (generica) 
- Belgio - Numero di patente di guida 
- Belgio - Numero nazionale 
- Belgio - Numero di passaporto 
- Belgio - Numero di imposta sul valore aggiunto 
- Numero CPF Brasile 
- Brasile - Codice fiscale persone giuridiche (CNPJ) 
- 	Carta d'identità (Brasile) (RG) 
- Bulgaria Driver's License Number 
- Bulgaria - Numero di passaporto 
- Numero civile uniforme Bulgaria 
- Canada - Numero di conto bancario 
- Canada - Numero della patente di guida 
- Canada - Codice del servizio sanitario 
- Canada - Numero di passaporto 
- Canada - Numero di identificazione sanitaria personale (PHIN) 
- Canada - Numero di assicurazione sociale 
- 	Cile - Numero di carta di identità 
- 	Numero carta di identità per residenti in Cina (RPC) 
- Numero di carta di credito 
- Croatia Driver's License Number 
- Numero di carta di identità della Croazia 
- Croatia National ID Card Number 
- Croatia Passport Number 
- Numero di identificazione personale (OIB) - Croazia 
- Firma di accesso condiviso Archiviazione di Azure account CSCAN-AZURE0060 
- Chiave simmetrica generale CSCAN-GENERAL0140 
- Cyprus Driver's License Number 
- Carta d'identità di Cipro 
- Cipro - Numero di passaporto 
- Codice fiscale di Cipro 
- Czech Driver's License Number 
- Numero di identità personale ceco 
- Numero di passaporto della Repubblica Ceca 
- Denmark Driver's License Number 
- Danimarca - Numero di passaporto 
- Codice PIN - Danimarca 
- Numero della Drug Enforcement Agency (DEA) 
- Estonia Driver's License Number 
- Estonia - Numero di passaporto 
- Estonia Personal Identification Code 
- Unione Europea - Numero di carta di debito 
- Numero di patente di guida UE 
- Numero di identificazione nazionale DELL 
- Numero di passaporto UE 
- CODICE SSN (EU Social Security Number) o ID equivalente 
- Codice fiscale UE (TIN) 
- Finlandia - Numero di patente di guida 
- Finlandia - Numero di assicurazione sanitaria europea 
- Finland National ID 
- Finlandia - Numero di passaporto 
- Francia - Numero della patente di guida 
- Francia - Numero di assicurazione sanitaria 
- Francia - Carta d'identità nazionale (CNI) 
- Francia - Numero di passaporto 
- Francia - Numero di previdenza sociale (INSEE) 
- Numero di identificazione fiscale francia (numéro SPI. 
- Francia - Numero di imposta sul valore aggiunto 
- Germania - Numero della patente di guida 
- Germania - Numero di passaporto 
- Germania - Numero carta di identità 
- Germany Tax Identification Number 
- Germania - Numero di imposta sul valore aggiunto 
- Numero di patente di guida per la Grecia 
- Carta d'identità (Grecia) 
- Grecia - Numero di passaporto 
- Grecia - Numero di previdenza sociale (AMKA) 
- Numero di identificazione fiscale greco 
- Hong Kong - Numero di carta di identità (HKID) 
- Codice di previdenza sociale ungherese (TAJ) 
- Numero di imposta sul valore aggiunto ungherese 
- Ungheria - Numero di patente di guida 
- Numero di passaporto ungherese 
- Ungheria - Numero di identificazione personale 
- Hungary Tax identification Number 
- India - Numero di conto permanente (PAN) 
- India - Numero di identificazione univoco (Aadhaar) 
- Indonesia - Numero di carta di identità (KTP) 
- Numero di conto bancario internazionale (IBAN) 
- Classificazione internazionale delle malattie (ICD-10-CM) 
- Classificazione internazionale delle malattie (ICD-9-CM) 
- Indirizzo IP 
- Ireland Driver's License Number 
- Irlanda - Numero di passaporto 
- Irlanda - Numero personale di servizio pubblico (PPS) 
- Israele - Numero di conto bancario 
- Carta di identità (Israele) 
- Italia - Numero della patente di guida 
- Codice fiscale italiano 
- Italia - Numero di passaporto 
- Numero imposta sul valore aggiunto dell'Italia 
- Giappone - Numero di conto bancario 
- Giappone - Numero della patente di guida 
- Giappone - Numero di passaporto 
- Giappone - Numero di registrazione dei residenti 
- Giappone - Numero di assicurazione sociale (SIN) 
- Giapponese Il mio numero aziendale 
- Giapponese Il mio numero personale 
- Numero carta di residenza giapponese 
- Numero di patente di guida lettone 
- Numero di passaporto lettone 
- Codice personale lettone 
- Numero di patente di guida lituania 
- Lituania - Numero di passaporto 
- Codice personale Lituania 
- Numero di patente di guida di Luxemburg 
- Numero di identificazione nazionale di Luxemburg (persone fisiche) 
- Numero di identificazione nazionale di Luxemburg (persone non fisiche) 
- Numero di passaporto di Luxemburg 
- Malaysia Identity Card Number 
- Malta Driver's License Number 
- Numero carta d'identità Malta 
- Malta Passport Number 
- Malta Tax ID Number 
- Paesi Bassi - Numero di servizio cittadino (BSN) 
- Netherlands Driver's License Number 
- Numero di passaporto olandese 
- Codice fiscale Paesi Bassi 
- Numero imposta sul valore aggiunto dei Paesi Bassi 
- Numero di conto corrente bancario della Nuova Zelanda 
- Numero di patente di guida in Nuova Zelanda 
- New Zealand Inland Revenue number 
- Nuova Zelanda - Numero del Ministero della Sanità 
- Numero di previdenza sociale in Nuova Zelanda 
- Norvegia - Numero di identificazione 
- Filippine - Numero ID multifunzione unificato 
- Poland Driver's License Number 
- Carta di identità - Polonia 
- ID nazionale Polonia (PESEL) 
- Passaporto Polonia 
- Codice fiscale Polonia 
- Numero REGON polacco 
- Portogallo - Numero di carta del cittadino 
- Portugal Driver's License Number 
- Portugal Passport Number 
- Portugal Tax Identification Number 
- Romania Driver's License Number 
- Numero di passaporto romania 
- Romania Personal Numerical Code (CNP) 
- Numero di passaporto russo (nazionale) 
- Numero di passaporto russo (internazionale) 
- Arabia Saudita - Identificativo nazionale 
- Singapore - Numero di carta di identità di registrazione nazionale (NRIC) 
- Slovacchia - Numero di patente di guida 
- Slovacchia - Numero di passaporto 
- Slovacchia - Numero personale 
- Slovenia Driver's License Number 
- Numero di passaporto slovenia 
- Slovenia Tax Identification Number 
- Slovenia Unique Master Citizen Number 
- Sudafrica - Numero di identificazione
 
- Corea del Sud - Numero di registrazione dei residenti 
- Spagna DNI 
- Spagna - Numero di patente di guida 
- Spagna - Numero di passaporto 
- Spagna - Numero di previdenza sociale (SSN) 
- Spagna - Numero di identificazione fiscale 
- SQL Server Stringa di connessione 
- Svezia - Numero di patente di guida 
- Svezia - Identificativo nazionale 
- Svezia - Numero di passaporto 
- Svezia - Codice fiscale 
- Codice SWIFT 
- Swiss Social Security Number AHV 
- Taiwan National ID 
- 	Taiwan - Numero di passaporto 
- Taiwan Resident Certificate (ARC/TARC) 
- Codice di identificazione della popolazione thai 
- Numero di identificazione nazionale turco 
- Regno Unito - Numero della patente di guida 
- Regno Unito - Numero di iscrizione alle liste elettorali 
- Regno Unito - Codice del servizio sanitario nazionale 
- Regno Unito - Numero di assicurazione nazionale (NINO) 
- Regno Unito Numero di riferimento fiscale univoco 
- Stati Uniti/Regno Unito - Numero di passaporto 
- Stati Uniti - Numero di conto bancario 
- Stati Uniti - Numero della patente di guida 
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN) 
- Stati Uniti - Numero di previdenza sociale (SSN) 
- Numero di passaporto dell'Ucraina (nazionale) 
- Numero di passaporto dell'Ucraina (internazionale) 
 
Si noti che verranno rilevati anche tipi di informazioni riservate personalizzati oltre ai tipi di informazioni riservate predefiniti precedenti

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Support Matrix for DLP policy tips across Microsoft apps

|**App e piattaforma**|**Supporto del suggerimento per i criteri DLP**|**Tipi di informazioni riservate supportati**|**Predicati e azioni supportati**|**Comments**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Tutti|Sottoinsieme|Vedere Informazioni di riferimento sui suggerimenti [per i criteri di prevenzione della perdita di dati](#data-loss-prevention-policy-tips-reference)|
|**Outlook Win32 (Outlook 2013 e oltre)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Sottoinsieme|Sottoinsieme|Vedere [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) e versioni successive supporta la visualizzazione di suggerimenti sui criteri solo per alcune condizioni ed eccezioni e per le app [di Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) e successive e Office sul desktop che mostrano suggerimenti sui criteri solo per alcuni tipi di informazioni riservate per informazioni dettagliate sul supporto per i tipi di informazioni riservate e le condizioni DLP e le azioni supportate per la visualizzazione di suggerimenti sui criteri DLP su Outlook Win32.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno|I suggerimenti per i criteri DLP non sono supportati Outlook mobile|
|**Client Web Sharepoint Online/One Drive for Business**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Tutti|Tutti i predicati e le azioni di SPO/ODB in DLP||
|**Sharepoint Win32/ One Drive for Business Win32 client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno|I suggerimenti per i criteri DLP non sono supportati nelle app client desktop OneDrive Sharepoint o SharePoint|
|**Word, Excel, PowerPoint Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Tutti|Tutti i predicati e le azioni di SPO/ODB in DLP|Il suggerimento per i criteri DLP è supportato se il documento è ospitato nell'app Web ODB o SPO e il criterio DLP è già contrassegnato.|
|**Word, Excel, PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno|I suggerimenti per i criteri DLP non sono supportati nelle app per dispositivi mobili per Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Tutti|Tutti Teams predicati nel criterio DLP|I suggerimenti per i criteri vengono visualizzati quando un messaggio è contrassegnato come "Questo messaggio è stato contrassegnato. Cosa posso fare?" Facendo clic sul collegamento, l'utente può esaminare i tipi di informazioni sensibili rilevati e ignorare o segnalare un problema, se consentito dall'amministratore. Si noti che non vengono visualizzati suggerimenti per i criteri per i file. Quando il destinatario tenta di accedere al documento, potrebbe ottenere l'accesso negato se non consentito.|
|**Dispositivi endpoint Win32**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Sottoinsieme|Tutti i predicati e le azioni di Endpoint DLP nel criterio DLP|Vedi [Prevenzione della perdita di dati nell'endpoint supporta i suggerimenti per i criteri solo per alcuni tipi di informazioni riservate](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Dispositivi Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno|I criteri di prevenzione della perdita dei dati non sono attualmente applicati nei dispositivi Mac|
|**App cloud di terze parti**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno|I suggerimenti per i criteri di prevenzione della perdita dei dati non sono supportati nelle app cloud di terze parti|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nessuno|Nessuno||
|**Word, Excel, PowerPoint Win32 Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Sottoinsieme|Sottoinsieme|Vedi app [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) e versioni successive e Office sul supporto desktop che mostrano suggerimenti sui criteri solo per alcuni tipi di informazioni riservate per l'elenco dei tipi di informazioni riservate supportati</br></br>I suggerimenti per i criteri per le app client WXP funzioneranno per i documenti archiviati nei siti di Sharepoint Online o One Drive for Business per tutti i criteri DLP che hanno esattamente le condizioni o un sottoinsieme di condizioni o azioni nel criterio DLP:</br> <ul><li>Il contenuto contiene tipi di informazioni riservate</li><li>Ambito di accesso (il contenuto è condiviso internamente/esternamente)</li><li>Notifica utente (suggerimenti per i criteri/notifiche utente)</li><li>Blocca tutti</li><li>Report degli incidenti</li></ul></br> Se sono presenti altre condizioni o azioni, il suggerimento per il criterio DLP per tale criterio non verrà visualizzato nelle app desktop di Word, Excel o PowerPoint.</br>Per [ulteriori informazioni, vedere Policy tips in Excel, PowerPoint e Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)|
||||||
