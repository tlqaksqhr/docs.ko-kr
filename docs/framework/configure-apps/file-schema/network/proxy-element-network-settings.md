---
title: '&lt;프록시&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b5ae716994f9b8222a633699367c94480179c97b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744449"
---
# <a name="ltproxygt-element-network-settings"></a>&lt;프록시&gt; 요소 (네트워크 설정)
프록시 서버를 정의합니다.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy >  
\<프록시 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`autoDetect`|프록시를 자동으로 검색할지 여부를 지정 합니다. 기본값은 `unspecified`입니다.|  
|`bypassonlocal`|로컬 리소스에 대 한 프록시를 바이패스 하는지 여부를 지정 합니다. 로컬 리소스에는 로컬 서버 포함 (http://localhost, http://loopback, 또는 http://127.0.0.1) 및 마침표가 없는 URI (http://webserver)합니다. 기본값은 `unspecified`입니다.|  
|`proxyaddress`|프록시 사용 하는 URI를 지정 합니다.|  
|`scriptLocation`|구성 스크립트의 위치를 지정합니다.|  
|`usesystemdefault`|Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다. 경우 설정 `true`, 후속 특성에는 Internet Explorer 프록시 설정은 재정의 됩니다. 기본값은 `unspecified`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="text-value"></a>텍스트 값  
  
## <a name="remarks"></a>설명  
 `proxy` 요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다. 이 요소는 구성 파일에서 누락,.NET Framework Internet Explorer에서 프록시 설정을 사용 합니다.  
  
 에 대 한 값은 `proxyaddress` 특성에는 올바른 형식의 표시기 URI (Uniform Resource) 이어야 합니다.  
  
 `scriptLocation` 특성이 프록시 구성 스크립트의 자동 검색을 참조 합니다. <xref:System.Net.WebProxy> 클래스는 구성 스크립트 (일반적으로 명명 된 Wpad.dat) 경우 찾으려고 시도 **자동 구성 스크립트를 사용 하 여** Internet Explorer에서 옵션을 선택 합니다.  
  
 사용 하 여 `usesystemdefault` 버전 2.0으로 마이그레이션하는.NET Framework 버전 1.1 응용 프로그램에 대 한 특성입니다.  
  
 예외가 발생 하는 경우는 `proxyaddress` 특성 잘못 된 기본 프록시를 지정 합니다. 예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 여, 프록시 주소를 지정 및 로컬 액세스에 대 한 프록시를 무시 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
