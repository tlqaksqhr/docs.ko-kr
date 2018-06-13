---
title: '&lt;iriParsing&gt; 요소 (Uri 설정)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743305"
---
# <a name="ltiriparsinggt-element-uri-settings"></a>&lt;iriParsing&gt; 요소 (Uri 설정)
IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.  
  
## <a name="schema-hierarchy"></a>스키마 계층 구조  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri > 요소 (Uri 설정)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<iriParsing >](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a>구문  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|`enabled`|IRI 구문 분석 사용 되는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[Uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 기존 <xref:System.Uri> 클래스는.NET Framework 3.5에서 확장 되었습니다. 3.0 SP1 및 2.0 s p 1 식별자 IRI (International Resource) 및 이름 IDN (Internationalized Domain)에 대 한 지원을 제공 하기 위해. IRI 및 IDN 구체적으로 설정 하지 않으면 현재 사용자의.NET Framework 2.0 동작 어떠한 변경도 표시 되지 것입니다 지원 합니다. 이 덕분에 .NET Framework 이전 버전과의 응용 프로그램 호환성이 제공됩니다.  
  
 IRI에 대 한 지원을 설정 하는 다음 두 가지 변경이 필요 합니다.  
  
1.  .NET Framework 2.0 디렉터리 아래에 있는 machine.config 파일에 다음 줄을 추가 합니다.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다. 이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.  
  
 IRI 구문 분석을 사용 하도록 설정 (활성화 iriParsing = `true`) 최신 IRI에 따라 검사 문자 규칙 RFC 3987 및 정규화를 수행 합니다. 기본값은 `false` 고 됩니다 정규화 및 수행 (IPv6 리터럴)에 대 한 RFC 2396에 따라 검사 및 RFC 3986 문자입니다.  
  
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
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
