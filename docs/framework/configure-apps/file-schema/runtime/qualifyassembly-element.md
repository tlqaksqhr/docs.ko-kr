---
title: "&lt;qualifyAssembly&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dd24ae9e5659deff7ddbe4183c70d5b442542cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltqualifyassemblygt-element"></a>&lt;qualifyAssembly&gt; 요소
부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<qualifyAssembly>  
  
## <a name="syntax"></a>구문  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`partialName`|필수 특성입니다.<br /><br /> 코드에 표시 된 대로 어셈블리의 부분 이름을 지정 합니다.|  
|`fullName`|필수 특성입니다.<br /><br /> 전역 어셈블리 캐시에 표시 되는 어셈블리의 전체 이름을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 호출 된 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 부분 어셈블리 이름을 사용 하 여 메서드를 공용 언어 런타임 응용 프로그램 기본 디렉터리에만 어셈블리에 대 한 조회를 사용 하면 됩니다. 사용 하 여  **\<qualifyAssembly >** 전체 어셈블리 정보 (이름, 버전, 공개 키 토큰 및 문화권)를 제공 하 여 검색 하려면 공용 언어 런타임이 응용 프로그램 구성 파일의 요소 전역 어셈블리 캐시에서 어셈블리입니다.  
  
 **fullName** 특성의 어셈블리 id는 4 개의 필드를 포함 해야 합니다: 이름, 버전, 공개 키 토큰 및 culture입니다. **partialName** 특성 어셈블리를 부분적으로 참조 해야 합니다. 어셈블리의 텍스트 이름 (가장 일반적인 경우), 이상 지정 해야 하지만 버전, 공개 키 토큰 또는 문화권 (또는 일부 4의 임의 조합)을 포함할 수도 있습니다. **partialName** 프로그램 호출에 지정 된 이름과 일치 해야 합니다. 예를 들어 지정할 수 없습니다 `"math"` 로 **partialName** 구성 파일 및 호출 특성 `Assembly.Load("math, Version=3.3.3.3")` 코드에서입니다.  
  
## <a name="example"></a>예  
 다음 예에서는 논리적으로 호출을 변환 `Assembly.Load("math")` 에 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [NIB: 부분 어셈블리 참조](http://msdn.microsoft.com/library/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
