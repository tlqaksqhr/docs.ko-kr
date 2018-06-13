---
title: '&lt;etwEnable&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 267a4a29282881d18201d0cb2062e91b4ff974a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745177"
---
# <a name="ltetwenablegt-element"></a>&lt;etwEnable&gt; 요소
공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<etwEnabled >  
  
## <a name="syntax"></a>구문  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> ETW를 사용 해야 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|true|ETW를 사용 하도록 설정 합니다. Windows Vista 및 Windows Server 2008 운영 체제부터 Windows 버전에 대 한 기본값입니다.|  
|False|ETW를 사용 하지 않도록 설정 합니다. 이전 버전의 Windows에 대 한 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 Windows Vista부터, ETW 기본적으로 사용 됩니다. 이 요소를 사용 하 여 응용 프로그램에 대 한 ETW를 사용 하지 않도록 설정 합니다. 이전 버전의 Windows에서 응용 프로그램에 대 한 ETW를 사용 하도록 설정 하려면이 요소를 사용 합니다.  
  
> [!NOTE]
>  ETW는 사용 하도록 설정 또는 레지스트리 설정을 사용 하 여 서버에 전체적으로 해제 수 있습니다. 참조 [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램에 대 한 ETW 추적을 사용 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)
