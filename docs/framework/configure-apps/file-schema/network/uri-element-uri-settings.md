---
title: "&lt;Uri&gt; 요소 (Uri 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44ef28ca2188973ccd353f4e8615c7c95f5674a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lturigt-element-uri-settings"></a>&lt;Uri&gt; 요소 (Uri 설정)
.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.  
  
## <a name="schema-hierarchy"></a>스키마 계층 구조  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri >](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a>구문  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|리소스 IRI (International Identifier) 구문 분석에 적용 됩니다 지정 <xref:System.Uri> IRI 구문 분석 규칙을 적용 해야 하는지 여부입니다.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[구성](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|모든 네임 스페이스에 대 한 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `uri` 요소의 멤버에 대 한 설정이 포함 되어는 <xref:System.Uri> 클래스에 의해 사용 되는 클래스는 <xref:System.Net> 네임 스페이스입니다. 이 설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서 사용 되는 구성을 <xref:System.Uri> IRI 구문 분석 및 IDN 이름을 지원 하기 위해 클래스입니다. 이 예제에서는 또한 모든 스키마 설정을 지우고 http 체계에 대 한 퍼센트 인코딩 경로 구분 기호를 이스케이프 하지 않아도 되도록 하는 것에 대 한 지원을 추가 합니다.  
  
### <a name="code"></a>코드  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
