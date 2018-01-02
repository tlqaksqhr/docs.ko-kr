---
title: "&lt;requiredRuntime&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 12be2350cb123407b2f71d1f5f07e836ccddb9c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt; 요소
응용 프로그램에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다. 이 요소는 사용 되지 않으며 더 이상 사용 되지 않음을. [ `supportedRuntime` ](supportedruntime-element.md) 요소를 대신 사용 해야 합니다.
  
 \<configuration>  
\<시작 >  
\<requiredRuntime >  
  
## <a name="syntax"></a>구문  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`version`|선택적 특성입니다.<br /><br /> 이 응용 프로그램이 지 원하는.NET Framework의 버전을 지정 하는 문자열 값입니다. 문자열 값에는.NET Framework 설치 루트 아래 표시 된 디렉터리 이름과 일치 해야 합니다. 문자열 값의 내용은 구문 분석 되지 않습니다.|  
|`safemode`|선택적 특성입니다.<br /><br /> 런타임 시작 코드는 런타임 버전을 확인 하려면 레지스트리를 검색 하는지 여부를 지정 합니다.|  
  
## <a name="safemode-attribute"></a>안전 모드 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|레지스트리 런타임 시작 코드를 검색 합니다. 기본값입니다.|  
|`true`|레지스트리에 런타임 시작 코드를 검사 하지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`startup`|포함 된 `<requiredRuntime>` 요소입니다.|  
  
## <a name="remarks"></a>설명  
 런타임 버전 1.0만 지원 하도록 작성 된 응용 프로그램을 사용 해야 합니다는 `<requiredRuntime>` 요소입니다. 버전 1.1 이상 런타임에서 사용 하 여 빌드된 응용 프로그램을 사용 해야 합니다는 `<supportedRuntime>` 요소입니다.  
  
> [!NOTE]
>  사용 하는 경우는 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 구성 파일을 지정 하려면 함수를 사용 해야 합니다는 `<requiredRuntime>` 모든 버전의 런타임에 대 한 요소입니다. `<supportedRuntime>` 사용할 때 요소는 무시 됩니다 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)합니다.  
  
 `version` 특성 문자열에 지정된 된 버전의.NET Framework에 대 한 설치 폴더 이름과 일치 해야 합니다. 이 문자열 해석 되지 않습니다. 일치 하는 폴더를 찾지 못하면 런타임 시작 코드는 런타임이 로드 되지 않습니다. 시작 코드는 오류 메시지를 표시 하 고 종료 됩니다.  
  
> [!NOTE]
>  Microsoft Internet Explorer에서 호스팅되는 응용 프로그램에 대 한 시작 코드는 무시는 `<requiredRuntime>` 요소입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 구성 파일에서 런타임 버전을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> 사용할 런타임 버전 지정](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
