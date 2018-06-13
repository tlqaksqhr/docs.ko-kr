---
title: '&lt;idn&gt; 요소 (Uri 설정)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742574"
---
# <a name="ltidngt-element-uri-settings"></a>&lt;idn&gt; 요소 (Uri 설정)
다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용 됩니다 지정 합니다.  
  
## <a name="schema-hierarchy"></a>스키마 계층 구조  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri > 요소 (Uri 설정)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn >](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>구문  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|`enabled`|도메인 이름에 적용 되는 다국어 도메인 이름 (IDN) 구문 분석 하는 경우 기본값은 none을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[Uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 기존 <xref:System.Uri> 클래스는.NET Framework 3.5에서 확장 되었습니다. 3.0 SP1 및 2.0 s p 1 식별자 IRI (International Resource) 및 이름 IDN (Internationalized Domain)를 지 원하는 합니다. IRI 및 IDN 구체적으로 설정 하지 않으면 현재 사용자의.NET Framework 2.0 동작 어떠한 변경도 표시 되지 것입니다 지원 합니다. 이 덕분에 .NET Framework 이전 버전과의 응용 프로그램 호환성이 제공됩니다.  
  
 IRI에 대 한 지원을 설정 하는 다음 두 가지 변경이 필요 합니다.  
  
1.  .NET Framework 2.0 디렉터리 아래에 있는 machine.config 파일에 다음 줄을 추가 합니다.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  도메인 이름에 적용 된 다국어 도메인 이름 (IDN) 구문 분석 및 여부 IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다. 이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.  
  
 사용 되는 DNS 서버에 따라 IDN에 대 한 3 가지 가능한 값인 가지가 있습니다.  
  
-   사용 하도록 설정 하는 idn = All  
  
     이 값은 punycode (IDN 이름)에 모든 유니코드 도메인 이름을 변환 합니다.  
  
-   사용 하도록 설정 하는 idn AllExceptIntranet =  
  
     이 값은 punycode (IDN 이름)을 사용 하도록 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다. 이 경우를 처리 하기 위해 로컬 인트라넷에 국제 이름을 인트라넷에 사용 되는 DNS 서버 유니코드 이름 확인을 지원 해야 합니다.  
  
-   사용 하도록 설정 하는 idn = 없음  
  
     이 값은 Punycode를 사용 하도록 모든 유니코드 도메인 이름을 변환 되지 않습니다. .NET Framework 2.0 동작은와 일치 하는 기본값입니다.  
  
 IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다. Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다. 대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.  
  
### <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서 사용 되는 구성을 <xref:System.Uri> IRI 구문 분석 및 IDN 이름을 지원 하기 위해 클래스입니다.  
  
### <a name="code"></a>코드  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
