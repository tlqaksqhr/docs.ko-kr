---
title: "&lt;loadFromRemoteSources&gt; 요소 | Microsoft Docs"
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
helpviewer_keywords: 
  - "loadFromRemoteSources 요소"
  - "<loadFromRemoteSources> 요소"
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: 31
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 31
---
# &lt;loadFromRemoteSources&gt; 요소
원격 소스의 어셈블리에 완전 신뢰를 부여할지 여부를 지정합니다.  
  
> [!NOTE]
>  Visual Studio 프로젝트 오류 목록의 오류 메시지 또는 빌드 오류로 인해 이 항목으로 연결된 경우 [방법: Visual Studio에서 웹의 어셈블리 사용](http://msdn.microsoft.com/ko-kr/d8635b63-89a0-41aa-90f4-f351b2111070)을 참조하십시오.  
  
## 구문  
  
```  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 원격 소스에서 로드한 어셈블리에 완전 신뢰를 부여할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|원격 소스의 응용 프로그램에 완전 신뢰를 부여하지 마십시오.  이 값이 기본값입니다.|  
|`true`|원격 소스의 응용 프로그램에 완전 신뢰를 부여합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 버전 3.5 및 이전 버전에서는 원격 위치의 어셈블리를 로드하면 어셈블리가 로드되는 영역에 의해 결정되는 권한 부여 설정에 따라 부분 신뢰로 실행됩니다.  예를 들어, 웹 사이트에서 어셈블리를 로드한 경우, 인터넷 영역으로 로드되고 Internet 권한 집합을 부여 받습니다.  즉, 어셈블리가 인터넷 샌드박스에서 실행됩니다.  [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]와 그 이상 버전에서 해당 어셈블리를 실행할 경우 예외가 throw됩니다. 어셈블리에 대한 샌드박스를 명시적으로 만들거나\([방법: 샌드박스에서 부분 신뢰 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)를 참조하세요\) 어셈블리를 완전 신뢰로 실행해야 합니다.  
  
 `<loadFromRemoteSources>` 요소를 사용하면 이전 버전의 .NET Framework에서 부분 신뢰로 실행되는 어셈블리가 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 및 그 이상 버전에서 완전 신뢰로 실행되도록 지정할 수 있습니다.  기본적으로, 원격 어셈블리는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 및 그 이상에서 실행 하지 않습니다.  원격 어셈블리를 실행 하려면, 완전히 신뢰된 실행 하거나 실행할 샌드박스된 <xref:System.AppDomain>를 만들어야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에서, 로컬 네트워크 공유에 있는 어셈블리는 기본적으로 완전 신뢰 상태로 실행 합니다; `<loadFromRemoteSources>` 요소를 활성시킬 필요가 없습니다.  
  
> [!NOTE]
>  응용 프로그램을 웹에서 복사한 경우, 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 응용 프로그램이라는 플래그가 Windows에 의해 지정됩니다.  파일 속성을 변경하여 해당 지정을 변경하거나 `<loadFromRemoteSources>` 요소를 사용하여 어셈블리에 완전 신뢰를 부여할 수 있습니다.  대안으로서, 운영 체제가 웹에서 로드 되었음을 표시 하는 로컬 어셈블리를 로드 하는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용할 수 있습니다.  
  
 이 요소의 `enabled` 특성은 CAS\(코드 액세스 보안\)을 사용하지 않도록 설정한 경우에만 적용됩니다.  기본적으로 CAS 정책은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 및 이후 버전에서 사용되지 않습니다.  `enabled`를 `true`로 설정하면 원격 응용 프로그램에 완전 신뢰가 부여됩니다.  
  
 `<loadFromRemoteSources>` `enabled`가 `true`로 설정되어 있지 않으면 다음과 같은 경우 예외가 throw됩니다.  
  
-   현재 도메인의 샌드박싱 동작이 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]에서의 동작과 다른 경우.  이 경우 CAS 정책을 사용하지 않도록 설정하고 현재 도메인에 샌드박스를 적용하지 않아야 합니다.  
  
-   `MyComputer`가 아닌 영역에서 어셈블리가 로드되고 있는 경우  
  
> [!NOTE]
>  호스팅 컴퓨터의 연결된 폴더에서 파일을 로드하려고 할 때 Windows 가상 PC 응용 프로그램에서 <xref:System.IO.FileLoadException>을 가져올 수 있습니다.  이 오류는 [원격 데스크톱 서비스](http://go.microsoft.com/fwlink/?LinkId=182775) \(터미널 서비스\)에 링크 된 폴더에서 파일을 로드하려고 할 때에 발생합니다.  예외를 방지하려면 `enabled`를 `true`로 설정합니다.  
  
 `<loadFromRemoteSources>` 요소를 `true`로 설정하면 이 예외가 throw되지 않습니다.  따라서 공용 언어 런타임을 사용하지 않고도 보안을 위해 로드된 어셈블리를 샌드박싱하고 이러한 어셈블리가 완전 신뢰로 실행되도록 지정할 수 있습니다.  
  
> [!IMPORTANT]
>  어셈블리를 완전 신뢰로 실행해서는 안 되는 경우 이 구성 요소를 설정하는 대신  어셈블리를 로드할 샌드박스가 적용된 <xref:System.AppDomain>을 만드십시오.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에서 주로 사용 되지만 컨텍스트에 따라 다른 구성 파일에 사용할 수 있습니다.  자세한 내용은 다음 문서를 참조 하십시오. .NET 보안 블로그의 [CAS 정책의 자세한 암시적 사용: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839).  
  
## 예제  
 다음 예제에서는 원격 소스의 응용 프로그램에 완전 신뢰를 부여하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [CAS 정책의 암시적 사용: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)   
 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)   
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)