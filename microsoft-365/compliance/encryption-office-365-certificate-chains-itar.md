---
title: Catene di crittografia di Office 365 - DOD e GCC High
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/24/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Visualizzare un elenco completo dei certificati e delle autorità di certificazione (CAs) di DOD e GCC High root in Office 365.
ms.openlocfilehash: 19f164669392372c99c562f55cfb05487d9f7ed2
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308279"
---
# <a name="office-365-encryption-chains---dod-and-gcc-high"></a>Catene di crittografia di Office 365 - DOD e GCC High

Office 365 utilizza una serie di provider di certificati diversi. Di seguito viene descritto l'elenco completo dei certificati radice noti di Office 365 che potrebbero verificarsi quando si accede **a** Office 365. Per informazioni sui certificati che potrebbe essere necessario installare nella propria infrastruttura, vedere [Plan for Third-Party SSL Certificates for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates).

Le informazioni relative al certificato seguenti si applicano a **tutti i clienti DOD e High GCC**.

>[!NOTE]
>Per informazioni sui certificati applicabili ai **clienti di tutto il mondo**, vedere [catene di crittografia di Office 365](encryption-office-365-certificate-chains.md).

| **Tipo di certificato** | **Download di P7b** | **Endpoint CRL** | **Endpoint OCSP** |
| --- | --- | --- | --- | --- |
| Certificati intermedio e radice pubblicamente attendibili | [Bundle di certificati di ITAR di Office 365 (P7B)](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/O365_Chain_Certs_ITAR20200304.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

Espandere la radice e le sezioni intermedie per visualizzare ulteriori dettagli sui provider di certificati.

## <a name="office-365-certificate-details"></a>**Dettagli del certificato di Office 365**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Oggetto** | CN = radice di CyberTrust Baltimore<br>OU = CyberTrust<br>O = Baltimora<br>C = IE |
| --- | --- |
| **Numero di serie** | 02:00:00: B9 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Maggio 12 18:46:00 2000 UTC |
| **Validità non dopo** | Maggio 12 23:59:00 2025 UTC |
| **Identificatore chiave del soggetto** | E5:9D: 50:30:82:47:58: CC: AC: fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Identificazione personale (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **Identificazione personale (SHA-256)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **Pin (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**Servizi cloud di DigiCert CA-1**

| **Oggetto** | CN = Servizi cloud di DigiCert CA-1<br>O = DigiCert Inc<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = DigiCert CA radice globale<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = Stati Uniti |
| **Numero di serie** | 01:9E: C1: C6: BD: 3F: 59:7B: B2:0C: 33:38: E5:51: D8:77 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Aug 04 12:00:00 2015 UTC |
| **Validità non dopo** | Aug 04 12:00:00 2030 UTC |
| **Identificatore chiave del soggetto** | DD: 51: D0: a2:31:73: A9:73: AE: 8F: B4:01:7E: 5D: 8C: 57: CB: 9F: F0: F7 |
| **Identificatore chiave dell'autorità** | keyId: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Identificazione personale (SHA-1)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **Identificazione personale (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **Pin (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **URL CRL** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **URL OCSP** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**CA radice globale di DigiCert**

| **Oggetto** | CN = DigiCert CA radice globale<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = Stati Uniti |
| --- | --- |
| **Numero di serie** | 08:3B: E0:56:90:42:46: B1: A1:75:6A: C9:59:91: C7:4A |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Nov 10 00:00:00 2006 UTC |
| **Validità non dopo** | Nov 10 00:00:00 2031 UTC |
| **Identificatore chiave del soggetto** | 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Identificatore chiave dell'autorità** | keyId: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Identificazione personale (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **Identificazione personale (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **Pin (SHA-256)** | r/mIkG3eEpVdm + u/Ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-high-assurance-ev-root-ca"></a>**CA radice di DigiCert High Assurance EV**

| **Oggetto** | CN = DigiCert High Assurance EV root CA<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = Stati Uniti |
| --- | --- |
| **Numero di serie** | 02: AC: 5C: 26:6A: 0B: 40:9B: 8F: 0B: 79: F2: AE: 46:25:77 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Nov 10 00:00:00 2006 UTC |
| **Validità non dopo** | Nov 10 00:00:00 2031 UTC |
| **Identificatore chiave del soggetto** | B1:3e: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Identificatore chiave dell'autorità** | keyId: B1:3e: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Identificazione personale (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **Identificazione personale (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **Pin (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**CA DigiCert SHA2 Extended Validation Server**

| **Oggetto** | CN = DigiCert SHA2 Extended Validation Server CA<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = Stati Uniti |
| --- | --- |
| **Numero di serie** | 0C: 79: A9:44: B0:8C: 11:20:92:61:5F: E2:6B: 1D: 83 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | 22 00:00:00 2013 ottobre UTC |
| **Validità non dopo** | 22 00:00:00 2028 ottobre UTC |
| **Identificatore chiave del soggetto** | 3D: D3:50: A5: D6: A0: AD: EE: F3:4A: 60:0A: 65: D3:21: D4: F8: F8: D6:0F |
| **Identificatore chiave dell'autorità** | keyID: B1:3e: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Identificazione personale (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **Identificazione personale (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="entrust-root-certification-authority"></a>**Autorità di certificazione radice di Entrust**

| **Oggetto** | CN = autorità di certificazione radice di Entrust<br>OU = "(c) 2006 Entrust, Inc."<br>OU = www. Entrust. NET/CPS è incorporato per riferimento<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Numero di serie** | 45:6B: 50:54 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Nov 27 12:23:42 2006 UTC |
| **Validità non dopo** | Nov 27 12:53:42 2026 UTC |
| **Identificatore chiave del soggetto** | 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 6D |
| **Identificatore chiave dell'autorità** | keyID: 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 6D |
| **Identificazione personale (SHA-1)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **Identificazione personale (SHA-256)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Autorità di certificazione radice di Entrust-G2**

| **Oggetto** | CN = autorità di certificazione radice di Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-solo per uso autorizzato&quot;<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Numero di serie** | 4A: 53:8C: 28 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Lug 07 17:25:54 2009 UTC |
| **Validità non dopo** | Dec 07 17:55:54 2030 UTC |
| **Identificatore chiave del soggetto** | 6a: 72:26:7A: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 8D: 9F: 90:12:66: AB |
| **Identificazione personale (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **Identificazione personale (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **Pin (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **Oggetto** | CN = autorità di certificazione Entrust. NET (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. NET/CPS \_ 2048 incorp. per Rif (Limit s Liab)<br>O = Entrust. NET |
| --- | --- |
| **Numero di serie** | 38:63: DE: F8 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Dec 24 17:50:51 1999 UTC |
| **Validità non dopo** | Lug 24 14:15:12 2029 UTC |
| **Identificatore chiave del soggetto** | 55: E4:81: D1:11:80: essere: D8:89: B9:08: a3:31: F9: a1:24:09:16: B9:70 |
| **Identificazione personale (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **Identificazione personale (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **Pin (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Autorità di certificazione Entrust-L1C**

| **Oggetto** | CN = autorità di certificazione Entrust-L1C<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. NET/RPA è incorporato per riferimento<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = autorità di certificazione Entrust. NET (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. NET/CPS \_ 2048 incorp. per Rif (Limits Liab).<br>O = Entrust. NET |
| **Numero di serie** | 4C: 0E: 8C: 39 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Nov 11 15:40:40 2011 UTC |
| **Validità non dopo** | Nov 11 02:51:17 2021 UTC |
| **Identificatore chiave del soggetto** | 1e: F1: AB: 89:06: F8:49:0f: 01:33:77: EE: 14:7A: EE: 19:7c: 93:28:4D |
| **Identificatore chiave dell'autorità** | keyId: 55: E4:81: D1:11:80: be: D8:89: B9:08: a3:31: F9: a1:24:09:16: B9:70 |
| **Identificazione personale (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Identificazione personale (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **Pin (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **URL CRL** | http://crl.entrust.net/2048ca.crl |
| **URL OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Autorità di certificazione Entrust-L1E**

| **Oggetto** | CN = autorità di certificazione Entrust-L1E<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. NET/RPA è incorporato per riferimento<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = autorità di certificazione Entrust. NET (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. NET/CPS \_ 2048 incorp. per Rif (Limits Liab).<br>O = Entrust. NET |
| **Numero di serie** | 4C: 0E: C9:18 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha1RSA |
| **Validità non prima** | Nov 11 15:40:40 2011 UTC |
| **Validità non dopo** | Nov 11 02:51:17 2021 UTC |
| **Identificatore chiave del soggetto** | 5B: 41:8A: B2: C4:43: C1: BD: BF: C8:54:41:55:9D: E0:96: AD: FF: B9: A1 |
| **Identificatore chiave dell'autorità** | keyId: 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 6D |
| **Identificazione personale (SHA-1)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **Identificazione personale (SHA-256)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **URL CRL** | http://crl.entrust.net/rootca1.crl |
| **URL OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Autorità di certificazione Entrust-L1K**

| **Oggetto** | CN = autorità di certificazione Entrust-L1K<br>OU = &quot; (c) 2012 Entrust, Inc.-solo per uso autorizzato&quot;<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = autorità di certificazione radice di Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-solo per uso autorizzato&quot;<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| **Numero di serie** | 0E: E9:4C: C3:00:00:00:00:51: D3:77:85 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | 05 19:13:56 2015 ottobre UTC |
| **Validità non dopo** | Dec 05 19:43:56 2030 UTC |
| **Identificatore chiave del soggetto** | 82: a2:70:74: DD: BC: 53:3F: CF: 7B: D4: F7: CD: 7F: A7:60: C6:0A: 4C: BF |
| **Identificatore chiave dell'autorità** | keyId: 6a: 72:26:7A: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 8D: 9F: 90:12:66: AB |
| **Identificazione personale (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **Identificazione personale (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **Pin (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **URL CRL** | http://crl.entrust.net/g2ca.crl |
| **URL OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Autorità di certificazione Entrust-L1M**

| **Oggetto** | CN = Entrust Certification Authority-L1M, OU = &quot; (c) 2014 Entrust, Inc.-solo per uso autorizzato&quot;<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = autorità di certificazione radice di Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-solo per uso autorizzato&quot;<br>OU = vedere www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = Stati Uniti |
| **Numero di serie** | 61: A1: E7: D2:00:00:00. H: 51: D3:66: A6 |
| **Lunghezza della chiave pubblica** | RSA 2048 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Dec 15 07:25:03 2014 UTC |
| **Validità non dopo** | 15 08:55:03 2030 ottobre UTC |
| **Identificatore chiave del soggetto** | C3: F7: D0: B5:2A: 30: AD: AF: 0D: 91:21:70:39:54: DD: BC: 89:70: C7:3A |
| **Identificatore chiave dell'autorità** | keyId: 6a: 72:26:7A: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 8D: 9F: 90:12:66: AB |
| **Identificazione personale (SHA-1)** | CC136695639065FAB47074D28C55314C66077E90 |
| **Identificazione personale (SHA-256)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **URL CRL** | http://crl.entrust.net/g2ca.crl |
| **URL OCSP** | http://ocsp.entrust.net |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **Oggetto** | CN = Microsoft IT TLS CA 1<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = radice di CyberTrust Baltimore<br>OU = CyberTrust<br>O = Baltimora<br>C = IE |
| **Numero di serie** | 08: B8:7A: 50:1B: BE: 9C: DA: 2D: 16:4D: 3E: 39:51: BF: 55 |
| **Lunghezza della chiave pubblica** | RSA 4096 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Maggio 20 12:51:28 2016 UTC |
| **Validità non dopo** | Maggio 20 12:51:28 2024 UTC |
| **Identificatore chiave del soggetto** | 58:88:9F: D6: DC: 9C: 48:22: B7:14:3e: FF: 84:88: E8: E6:85: FF: fa: 7D |
| **Identificatore chiave dell'autorità** | keyId: E5:9D: 59:30:82:47:58: CC: AC: fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Identificazione personale (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **Identificazione personale (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **Pin (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **URL CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **Oggetto** | CN = Microsoft IT TLS CA 2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = radice di CyberTrust Baltimore<br>OU = CyberTrust<br>O = Baltimora<br>C = IE |
| **Numero di serie** | 0F: 2C: 10: C9:5B: 06: C0:93:7F: B8: D4:49: F8:3E: 85:69 |
| **Lunghezza della chiave pubblica** | RSA 4096 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Maggio 20 12:51:57 2016 UTC |
| **Validità non dopo** | Maggio 20 12:51:57 2024 UTC |
| **Identificatore chiave del soggetto** | 91:9e: 3B: 44:6C: 3D: 57:9C: 42:77:2a: 34: D7:4F: D1: CC: 4a: 97:2C: da |
| **Identificatore chiave dell'autorità** | keyId: E5:9D: 59:30:82:47:58: CC: AC: fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Identificazione personale (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **Identificazione personale (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **Pin (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **URL CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **Oggetto** | CN = Microsoft IT TLS CA 4<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = radice di CyberTrust Baltimore<br>OU = CyberTrust<br>O = Baltimora<br>C = IE |
| **Numero di serie** | 0B: 6A: B3: B0:3E: B1: A9: F6: C4:60:92:6A: A8: CD: FE: B3 |
| **Lunghezza della chiave pubblica** | RSA 4096 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Maggio 20 12:52:38 2016 UTC |
| **Validità non dopo** | Maggio 20 12:52:38 2024 UTC |
| **Identificatore chiave del soggetto** | 7a: 7B: 8C: C1: CF: E7: a0: CA: 1C: D4:6B: fa: FB: E1:33: C3:0f: 1a: a2:9D |
| **Identificatore chiave dell'autorità** | keyId: E5:9D: 59:30:82:47:58: CC: AC: fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Identificazione personale (SHA-1)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **Identificazione personale (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **Pin (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **URL CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **Oggetto** | CN = Microsoft IT TLS CA 5<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = Stati Uniti |
| --- | --- |
| **Autorità di certificazione** | CN = radice di CyberTrust Baltimore<br>OU = CyberTrust<br>O = Baltimora<br>C = IE |
| **Numero di serie** | 08:88: CD: 52:5F: 19:24:44:4D: 14: A5:82:91: DE: B9:52 |
| **Lunghezza della chiave pubblica** | RSA 4096 bit (e 65537) |
| **Algoritmo di firma** | sha256RSA |
| **Validità non prima** | Maggio 20 12:53:03 2016 UTC |
| **Validità non dopo** | Maggio 20 12:53:03 2024 UTC |
| **Identificatore chiave del soggetto** | 08: Fe: 25:9F: 74: EA: 87:04: C2: BC: BB: 8E: A8:38:5F: 33: C6: D1:6C: 65 |
| **Identificatore chiave dell'autorità** | keyId: E5:9D: 59:30:82:47:58: CC: AC: fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Identificazione personale (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **Identificazione personale (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **Pin (SHA-256)** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **URL CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL OCSP** | http://ocsp.digicert.com |
