---
title: "&lt;webRequestModules&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f0da0e8afb2a9f89116b0d30992ce27b8520271d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a>&lt;webRequestModules&gt; 요소 (네트워크 설정)
네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.  
  
 \<configuration>  
\<system.net >  
\<webRequestModules >  
  
## <a name="syntax"></a>구문  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거합니다.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `webRequestModules` 요소는 <xref:System.Net.WebRequest> 클래스의 하위 클래스를 등록하여 네트워크 호스트로의 정보 요청을 처리합니다. 웹 요청 모듈을 구현 해야 합니다는 <xref:System.Net.IWebRequestCreate> 인터페이스입니다.  
  
 .NET Framework에는 http://, https://, 및 file://로 시작 하는 Uri에 대 한 웹 요청 모듈이 포함 됩니다. 구성 파일에 사용자 지정 모듈을 등록에 의해서만 기본 모듈을 재정의할 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 기본 HTTP 모듈을 등록 합니다. 지정된 된 모듈에 대 한 올바른 값으로 PublicKeyToken 및 버전에 대 한 값 바꿔야 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
