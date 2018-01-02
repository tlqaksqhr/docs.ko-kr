---
title: "&lt;shadowCopyVerifyByTimestamp&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bae98c91c8a9b68ec7c21b142bc9f004c7bc1394
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;shadowCopyVerifyByTimestamp&gt; 요소
섀도 복사에서 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 기본 시작 동작을 사용하는지 아니면 이전 .NET Framework 버전의 시작 동작으로 되돌아가는지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<shadowCopyVerifyByTimestamp > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 섀도 복사를 사용 하는 응용 프로그램 도메인 어셈블리에 어셈블리를 섀도 복사 하기 전에 업데이트 되었는지 여부를 확인 하려면 시작 시 어셈블리 타임 스탬프 비교 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|true|시작 시 어셈블리 섀도 복사 디렉터리에 마지막으로 복사 된 후이 업데이트 되어를 복사 합니다. 에 대 한 기본값은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.|  
|false|시작 시 모든 파일을 복사할 이전의 이전 버전의.NET Framework의 시작 동작으로 되돌립니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 어셈블리는 해당 타임 스탬프 섀도 복사 디렉터리에 마지막으로 복사 된 이후 변경 된 것을 나타내는 경우에 섀도 복사 합니다. 에 설명 된 대로 섀도 복사를 사용 하는 많은 응용 프로그램에 대 한 시작 시간이 향상 됩니다 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)합니다. 어셈블리 업데이트의 높은 비율과 빈도를 갖는 응용 프로그램은 이 동작 변경이 도움이 되지 않을 수 있습니다. 이 경우 이 요소를 사용하여 이전 버전의 .NET Framework의 동작을 복원할 수 있습니다.  
  
## <a name="example"></a>예  
 섀도 복사의 기본 시작 동작을 사용 하지 않도록 설정 하는 방법을 보여 주는 다음 예제는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 이전 버전의.NET Framework의 시작 동작으로 되돌립니다.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
