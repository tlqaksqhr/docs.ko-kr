---
title: "&lt;bypassTrustedAppStrongNames&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0343aef083076249325b9577f90964d066867f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;bypassTrustedAppStrongNames&gt; 요소
완전 신뢰에 로드 되는 완전 신뢰 어셈블리에 강력한 이름 유효성 검사를 무시할 것인지 지정 <xref:System.AppDomain>합니다.  
  
 \<configuration>  
\<런타임 >  
\<bypassTrustedAppStrongNames >  
  
## <a name="syntax"></a>구문  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 완전 신뢰 어셈블리에 대 한 강력한 이름 유효성 검사를 건너뛰는 기능을 사용할지 여부를 지정 합니다. 이 기능을 사용 하는 경우 강력한 이름은 유효성이 검사 되지 않습니다 정확성에 대 한 어셈블리가 로드 되는 경우. 기본값은 `true`입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|완전 신뢰 어셈블리에 강력한 이름 서명의 완전 신뢰에는 어셈블리를 로드할 때 유효성이 검사 되지 않습니다 <xref:System.AppDomain>합니다. 이 값이 기본값입니다.|  
|`false`|완전 신뢰 어셈블리에 강력한 이름 서명의 유효성을 검사 완전 신뢰에는 어셈블리를 로드할 때 <xref:System.AppDomain>합니다. 강력한 이름 서명은 서명 정확성;에 대 한 검사 일치 하는 다른 강력한 이름에는 비교 되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 강력한 이름 건너뛰기 기능 완전 신뢰 어셈블리의 강력한 이름 서명 확인 하는 오버 헤드를 방지할 수 있습니다.  
  
 건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.  
  
-   없이 완전 신뢰는 <xref:System.Security.Policy.StrongName> 증명 정보 (예를 들어, `MyComputer` 영역 증명 정보).  
  
-   완전히 신뢰할 수 있는 <xref:System.AppDomain>에 로드됨  
  
-   해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드됨  
  
-   서명이 연기되지 않음  
  
> [!NOTE]
>  건너뛰기 기능은 해제 되었습니다 컴퓨터의 모든 응용 프로그램에 대 한 레지스트리 키를 사용 하 여,이 구성 파일 설정은 효과가 없습니다. 자세한 내용은 참조 [하는 방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에는 완전 신뢰 어셈블리에 강력한 이름 서명의 유효성을 검사 하는 동작을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
