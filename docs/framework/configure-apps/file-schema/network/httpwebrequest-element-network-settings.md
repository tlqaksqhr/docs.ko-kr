---
title: "&lt;httpWebRequest&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<httpWebRequest> 요소"
  - "httpWebRequest 요소"
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# &lt;httpWebRequest&gt; 요소(네트워크 설정)
웹 요청 매개 변수를 사용자 지정합니다.  
  
## 구문  
  
```  
  
      <httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`maximumResponseHeadersLength`|응답 헤더의 최대 길이\(KB\)를 지정합니다.  기본값은 64입니다.  \-1 값은 응답 헤더에 크기 제한이 적용되지 않음을 나타냅니다.|  
|`maximumErrorResponseLength`|오류 응답의 최대 길이\(KB\)를 지정합니다.  기본값은 64입니다.  \-1 값은 오류 응답에 크기 제한이 적용되지 않음을 나타냅니다.|  
|`maximumUnauthorizedUploadLength`|권한이 없는 오류 코드에 응답할 때 업로드의 최대 길이\(바이트\)를 지정합니다.  기본값은 \-1입니다.  \-1은 업로드할 때 크기 제한이 적용되지 않음을 나타냅니다.|  
|`useUnsafeHeaderParsing`|안전하지 않은 헤더의 구문 분석을 사용하는지 여부를 지정합니다.  기본값은 `false`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
 기본적으로 .NET Framework에서는 URI 구문 분석에 대해 RFC 2616을 엄격하게 적용합니다.  일부 서버 응답은 사용할 수 없는 필드에 제어 문자를 포함할 수 있으며, 이럴 경우 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> 메서드가 <xref:System.Net.WebException>을 throw합니다.  **useUnsafeHeaderParsing**을 **true**로 설정하면 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName>가 throw되지 않습니다. 그러나 이 경우 응용 프로그램이 여러 형태의 URI 구문 분석 공격에 취약해집니다.  가장 좋은 해결책은 응답에 제어 문자가 포함되지 않도록 서버를 변경하는 것입니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 일반적인 최대 헤더 길이보다 큰 값을 지정하는 방법을 보여 줍니다.  
  
```  
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
  
## 참고 항목  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)