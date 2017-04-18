---
title: "&lt;httpListener&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;httpListener&gt; 요소(네트워크 설정)
<xref:System.Net.HttpListener> 클래스에서 사용하는 매개 변수를 사용자 지정합니다.  
  
## 구문  
  
```  
  
      <httpListener  
  unescapeRequestUrl ="true|false"  
/>  
```  
  
## 형식  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|unescapeRequestUrl|<xref:System.Net.HttpListener> 인스턴스가 변환된 URI 대신 이스케이프되지 않은 원시 URI를 사용할지 여부를 나타내는 부울 값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
 **unescapeRequestUrl** 특성은 <xref:System.Net.HttpListener>가 백분율 기호로 인코딩된 값이 변환되고 다른 정규화 단계가 수행되는 변환된 URI 대신 이스케이프되지 않은 원시 URI를 사용하는지 여부를 나타냅니다.  
  
 <xref:System.Net.HttpListener> 인스턴스가 `http.sys` 서비스를 통해 요청을 받을 때 인스턴스는 `http.sys`에서 제공된 URI 문자열의 인스턴스를 만들어 <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=fullName> 속성으로 노출합니다.  
  
 `http.sys` 서비스는 다음과 같은 두 요청 URI 문자열을 노출합니다.  
  
-   원시 URI  
  
-   변환된 URI  
  
 원시 URI는 HTTP 요청의 요청 줄에 제공되는 <xref:System.Uri?displayProperty=fullName>입니다.  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 위에서 설명한 요청에 대해 `http.sys`에서 제공되는 원시 URI는 "\/path\/"입니다.  이는 네트워크를 통해 보낸 것처럼 다음 HTTP 동사 다음의 문자열을 나타냅니다.  
  
 `http.sys` 서비스는 HTTP 요청줄에 제공된 URI와 요청을 전달해야 하는 소스 서버를 확인하는 호스트 헤더를 사용하여 요청에 제공된 정보를 통해 변환된 URI를 만듭니다.  이는 요청의 정보를 등록된 URI 접두사의 집합과 비교하여 수행됩니다.  HTTP 서버 SDK 설명서에서는 HTTP\_COOKED\_URL 구조체로 변환된 URI를 설명합니다.  
  
 등록된 URI 접두사 요청과 비교할 수 있도록 하려면 일부 정규화 요청을 수행해야 합니다.  위의 샘플의 경우 변환된 URI는 다음과 같습니다.  
  
 `http://www.contoso.com/path/`  
  
 `http.sys` 서비스는 <xref:System.Uri.Host%2A?displayProperty=fullName> 속성 값과 요청 줄의 문자열을 결합하여 변환된 URI를 만듭니다.  또한, `http.sys` 및 <xref:System.Uri?displayProperty=fullName> 클래스는 다음을 수행합니다.  
  
-   인코딩된 모든 백분율 값에서 이스케이프 해제  
  
-   백분율 기호로 인코딩된 ASCII 문자가 아닌 문자가 UTF\-16 문자 표현으로 변환됩니다.  UTF\-8 및 ANSI\/DBCS 문자뿐만 아니라 유니코드 문자\(%uXXXX 형식을 사용하는 유니코드 인코딩\)도 지원됩니다.  
  
-   경로 압축과 같은 다른 정규화 단계를 실행합니다.  
  
 백분율로 인코딩된 값에 사용되는 인코딩에 대한 정보가 요청에 없으므로 백분율로 인코딩된 값만 구문 분석하여 올바른 인코딩을 확인할 수 없습니다.  
  
 따라서 `http.sys`는 프로세스를 수정하는 두 개의 레지스트리 키를 제공합니다.  
  
|레지스트리 키|기본값|설명|  
|-------------|---------|--------|  
|EnableNonUTF8|1|0이면 `http.sys`가 UTF\-8 인코딩 URL만 받아들입니다.<br /><br /> 0이 아니면, `http.sys`는 요청에서 ANSI 인코딩되거나 DBCS 인코딩된 URL도 받아들입니다.|  
|FavorUTF8|1|0이 아닌 경우 `http.sys`은 항상 먼저 URL을 UTF\-8로 디코딩을 시도합니다. 해당 변환이 실패하고 EnableNonUTF8이 0이 아닌 경우 Http.sys는 ANSI 또는 DBCS로 디코딩을 시도합니다.<br /><br /> 0\(및 EnableNonUTF8이 0이 아님\)인 경우 `http.sys`는 ANSI 또는 DBCS로 디코딩을 시도합니다. 성공하지 않은 경우 UTF\-8 변환을 시도합니다.|  
  
 <xref:System.Net.HttpListener>가 요청을 받으면 `http.sys`에서 변환된 URI를 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대한 입력으로 사용합니다.  
  
 URI에서 문자 및 숫자 이외의 문자를 지원하는 데 필요합니다.  예를 들면 고객 번호 "1\/3812"에 대한 고객 정보를 검색하는 데 사용되는 다음과 같은 URI입니다.  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 URI에 % 인코딩된 슬래시가 있습니다\(%2F\).  이 경우 슬래시 문자는 경로 구분 기호가 아닌 데이터를 나타내므로 필요합니다.  
  
 URI 생성자에 문자열을 전달하면 다음과 같은 URI가 생성됩니다.  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 경로를 해당 세그먼트로 분할하면 다음 요소가 만들어집니다.  
  
 `Customer('1`  
  
 `3812')`  
  
 이것은 요청을 보낸 사람의 의도는 아닙니다.  
  
 **unescapeRequestUrl** 특성이 **false**로 설정된 경우 <xref:System.Net.HttpListener>가 요청을 받으면 이를 `http.sys`에서 변환된 URI 대신 <xref:System.Net.HttpListenerRequest.Url%2A> 속성에 대한 입력으로 사용합니다.  
  
 **unescapeRequestUrl** 특성의 기본값은 **true**입니다.  
  
 <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> 속성은 해당 구성 파일에서 **unescapeRequestUrl** 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `http.sys`에서 <xref:System.Net.HttpListenerRequest.Url%2A> 속성 입력으로 변환된 URI 대신 원시 URI를 사용하도록 요청을 받을 때 <xref:System.Net.HttpListener> 클래스를 구성하는 방법을 보여줍니다.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## 요소 정보  
  
|||  
|-|-|  
|네임스페이스|System.Net|  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있음||  
  
## 참고 항목  
 <xref:System.Net.Configuration.HttpListenerElement>   
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpListenerRequest.Url%2A>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)