---
title: "&lt;servicePointManager&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 85ccad3e2c3b237e286f3737589a5e58994521bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt; 요소 (네트워크 설정)
네트워크 리소스에 대 한 연결을 구성합니다.  
  
 \<configuration>  
\<system.net >  
\<설정 >  
\<servicePointManager >  
  
## <a name="syntax"></a>구문  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`checkCertificateName`|시스템이 인증서의 이름과 인증서를 사용 하기 전에 서버 호스트 이름이 일치 하는지 확인 해야 하는지 여부를 지정 합니다. 기본값은 `true`입니다.|  
|`checkCertificateRevocationList`|시스템이 인증서를 사용 하기 전에 인증서 해지 여부를 확인 해야 하는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
|`dnsRefreshTimeout`|DNS 라운드 로빈 옵션 밀리초에서와 함께에서 시간 서비스 DNS (Domain Name) 해상도 캐시를 지정 합니다. 기본값은 120,000밀리초(2분)입니다.|  
|`enableDnsRoundRobin`|호스트의 DNS 확인이 모든 주소를 또는 첫 번째 반환 여러 IP (인터넷 프로토콜) 주소와 이름을 있는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
|`encryptionPolicy`|SSL/TLS 세션에 적용 된 암호화 정책을 지정는 <xref:System.Net.ServicePointManager> 인스턴스. 가능한 값은에 대 한 값에 해당 하는 <xref:System.Net.Security.EncryptionPolicy> 열거형입니다. 사용 <xref:System.Security.Authentication.CipherAlgorithmType.Null> 암호화 정책을로 설정 된 경우에 필요한 `NoEncryption`합니다. 기본값은 `RequireEncryption`입니다.|  
|`expect100Continue`|POST 메서드를 받을 예상 해야 하는지 여부를 지정 된 `100-continue` 서버 로부터 응답 합니다. 기본값은 `true`입니다.|  
|`useNagleAlgorithm`|서비스 지점 관리자에 의해 제어 하는 연결 Nagle 알고리즘을 사용 하는지 여부를 지정 합니다. 기본값은 `true`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
