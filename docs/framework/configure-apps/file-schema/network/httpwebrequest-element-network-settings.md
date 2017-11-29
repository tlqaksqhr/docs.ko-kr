---
title: "&lt;httpWebRequest&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0a4490870cb12ff221f75b043f01baad9b5c7c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;httpWebRequest&gt; 요소 (네트워크 설정)
웹 요청 매개 변수를 사용자 지정합니다.  
  
 \<configuration>  
\<system.net >  
\<설정 >  
\<httpWebRequest >  
  
## <a name="syntax"></a>구문  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|킬로바이트 단위로, 응답 헤더의 최대 길이 지정합니다. 기본값은 64입니다. 값이-1 크기 제한이 없음을 응답 헤더에 적용 됩니다 나타냅니다.|  
|`maximumErrorResponseLength`|킬로바이트 단위로 오류 응답의 최대 길이 지정합니다. 기본값은 64입니다. 값이-1 크기 제한이 없음을 오류 응답에 적용 됩니다 나타냅니다.|  
|`maximumUnauthorizedUploadLength`|권한이 없는 오류 코드, 바이트에 대 한 응답으로 업로드의 최대 길이 지정합니다. 기본값은 -1입니다. 값이-1 크기 제한이 없음을 업로드에 적용 됩니다 나타냅니다.|  
|`useUnsafeHeaderParsing`|안전 하지 않은 헤더를 구문 분석을 사용 하는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로.NET Framework URI 구문 분석에 대 한 RFC 2616 엄격 하 게 적용합니다. 일부 서버 응답 하 게 허용 되지 않는 필드에 제어 문자가 포함 될 수 있습니다는 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> throw 하는 메서드는 <xref:System.Net.WebException>합니다. 경우 **useUnsafeHeaderParsing** 로 설정 된 **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> 되지만 경우에 throw 하지 않는 것, 응용 프로그램은 여러 형태의 URI 구문 분석 공격에 노출 됩니다. 가장 적합 한 솔루션에 대 한 응답 제어 문자가 포함 되지 서버를 변경 하는 것입니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 큰 값을 지정 하는 방법을 보여 줍니다. 일반적인 최대 헤더 길이 보다 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
