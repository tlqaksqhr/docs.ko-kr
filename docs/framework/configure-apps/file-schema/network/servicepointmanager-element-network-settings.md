---
title: "&lt;servicePointManager&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<servicePointManager> 요소"
  - "servicePointManager 요소"
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;servicePointManager&gt; 요소(네트워크 설정)
네트워크 리소스에 대한 연결을 구성합니다.  
  
## 구문  
  
```  
  
      <servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`checkCertificateName`|인증서 사용 전에 인증서의 이름이 서버 호스트 이름과 일치하는지를 시스템이 확인해야 하는지 여부를 지정합니다.  기본값은 `true`입니다.|  
|`checkCertificateRevocationList`|인증서 사용 전에 인증서가 해지되었는지를 시스템이 확인해야 하는지 여부를 지정합니다.  기본값은 `false`입니다.|  
|`dnsRefreshTimeout`|DNS 라운드 로빈 옵션과 함께 DNS\(Domain Name Service\) 확인이 캐시되는 시간\(밀리초\)을 지정합니다.  기본값은 120,000밀리초\(2분\)입니다.|  
|`enableDnsRoundRobin`|여러 IP\(인터넷 프로토콜\) 주소를 가진 호스트 이름에 대한 DNS 확인에서 모든 주소가 반환되는지 또는 첫 번째 주소만 반환되는지를 지정합니다.  기본값은 `false`입니다.|  
|`encryptionPolicy`|<xref:System.Net.ServicePointManager> 인스턴스에서 SSL\/TLS 세션에 적용된 암호화 정책을 지정합니다.  사용할 수 있는 값은 <xref:System.Net.Security.EncryptionPolicy> 열거형의 값과 동일합니다.  암호화 정책이 `NoEncryption`으로 설정된 경우 <xref:System.Security.Authentication.CipherAlgorithmType>의 사용이 필요합니다.  기본값은 `RequireEncryption`입니다.|  
|`expect100Continue`|POST 메서드가 서버에서 `100-continue` 응답을 받아야 하는지 여부를 지정합니다.  기본값은 `true`입니다.|  
|`useNagleAlgorithm`|서비스 지점 관리자가 제어하는 연결에서 Nagle 알고리즘을 사용하는지 여부를 지정합니다.  기본값은 `true`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Net.ServicePointManager>   
 <xref:System.Net.Security.EncryptionPolicy>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)