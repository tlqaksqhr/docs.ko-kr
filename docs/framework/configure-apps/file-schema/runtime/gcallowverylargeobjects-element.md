---
title: "&lt;gcAllowVeryLargeObjects&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5db777f147e2eca7644d5b5f1a4bc18c8401ca8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcallowverylargeobjectsgt-element"></a>&lt;gcAllowVeryLargeObjects&gt; 요소
64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<gcAllowVeryLargeObjects > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 64 비트 플랫폼에서의 총 크기가 2GB 보다 큰 않는 배열을 사용 되는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|총 크기가 2GB 보다 큰 배열 사용 되지 않습니다. 이 값이 기본값입니다.|  
|`true`|64 비트 플랫폼에서의 총 크기가 2GB 보다 큰 배열 활성화 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 사용 하 여 응용 프로그램 구성 파일에 크기가 2GB 보다 큰 배열에 있지만 개체 크기 또는 배열 크기에 대 한 다른 제한 변경 되지 않습니다.  
  
-   배열에 있는 요소의 최대 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>합니다.  
  
-   임의의 단일 차원에 있는 최대 인덱스 2,147,483,591 바이트 배열 및 단일 바이트 구조의 배열에 대 한 (0x7FFFFFC7) 및 다른 형식에 대 한 2,146,435,071 (0X7FEFFFFF)는입니다.  
  
-   문자열 및 기타 배열이 아닌 개체에 대 한 최대 크기는 변경 되지 않습니다.  
  
> [!CAUTION]
>  이 기능을 사용 하기 전에 응용 프로그램 모든 배열이 크기가 2GB 보다 작은 가정 하는 안전 하지 않은 코드를 포함 하지 않습니다 확인 합니다. 예를 들어 배열 2GB를 초과 하지 것입니다 가정에 작성 된 경우 버퍼도 배열을 사용 하는 안전 하지 않은 코드 버퍼 오버런에 취약 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 응용 프로그램에 대 한이 기능을 사용 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
