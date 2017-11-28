---
title: "&lt;검색이&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7dd829fbbfbaa6f26b59e26d5a8b1d2b36593f57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltprobinggt-element"></a>&lt;검색이&gt; 요소
공용 언어 런타임에서 어셈블리를 로드할 때 검색에 대 한 응용 프로그램 기본 하위 디렉터리를 지정 합니다.  
  
 \<configuration>  
\<런타임 >  
\<assemblyBinding >  
\<조사 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`privatePath`|필수 특성입니다.<br /><br /> 어셈블리에 포함 될 수 있는 응용 프로그램의 기본 디렉터리의 하위 디렉터리를 지정 합니다. 각 하위 디렉터리를 세미콜론으로 구분 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 런타임에 어셈블리를 검색 해야 응용 프로그램 기본 하위 디렉터리를 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [어셈블리 위치 지정](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
