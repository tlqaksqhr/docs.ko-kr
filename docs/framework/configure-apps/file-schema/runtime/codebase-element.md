---
title: "&lt;코드 베이스&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 272a4262295b5dd67414dd0ef6523f90b2125836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcodebasegt-element"></a>&lt;코드 베이스&gt; 요소
공용 언어 런타임에서 어셈블리를 찾을 수를 지정 합니다.  
  
 \<configuration>  
\<런타임 >  
\<assemblyBinding >  
\<dependentAssembly >  
\<s e >  
  
## <a name="syntax"></a>구문  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`href`|필수 특성입니다.<br /><br /> 런타임에서 지정 된 버전의 어셈블리를 찾을 수 있는 URL을 지정 합니다.|  
|`version`|필수 특성입니다.<br /><br /> 코드 베이스에 적용 됩니다. 어셈블리의 버전을 지정 합니다. 어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다.|  
  
## <a name="version-attribute"></a>버전 특성  
  
|값|설명|  
|-----------|-----------------|  
|버전 번호의 각 부분에 대 한 유효한 값은 0부터 65535 까지입니다.|해당 사항 없음.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`buildproviders`|사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다. 빌드 공급자 수에는 제한이 없습니다.|  
|`compilation`|ASP.NET에서 사용 하는 모든 컴파일 설정을 구성 합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`System.web`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 런타임에서 사용에 대 한는  **\<s e >** 컴퓨터 구성 파일 또는 게시자 정책 파일에 설정, 파일을 리디렉션해야 어셈블리 버전입니다. 응용 프로그램 구성 파일 없이 어셈블리 버전 리디렉션 codebase 설정을 가질 수 있습니다. 사용 하는 어셈블리 버전을 확인 한 후 런타임 버전을 결정 하는 파일의 코드 베이스 설정을 적용 합니다. 지정 된 없는 codebase가 런타임에서 어셈블리에 대 한 일반적으로 찾습니다.  
  
 어셈블리에 강력한 이름이 있으면 codebase 설정을 로컬 인트라넷 또는 인터넷에서 아무 곳 이나 수 있습니다. 전용 어셈블리를 어셈블리가 있는 경우 코드 베이스 설정은는 응용 프로그램의 디렉터리의 상대 경로 여야 합니다.  
  
 강력한 이름 없이 어셈블리의 경우 버전이 무시 되 고 로더 사용에서 처음 나오는 \<s e > 내 \<dependentAssembly > 합니다. 다른 어셈블리에 바인딩 리디렉션하는 응용 프로그램 구성 파일에 항목이 있으면 리디렉션 어셈블리 버전 바인딩 요청과 일치 하지 않는 경우에 우선을 적용 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 런타임에 어셈블리를 찾을 수를 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [어셈블리 위치 지정](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
