---
title: "&lt;되어 supportPortability&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52ef9cce9ee28c6329f688bb9ac751f0f9016657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltsupportportabilitygt-element"></a>&lt;되어 supportPortability&gt; 요소
응용 프로그램 이식성을 위해 어셈블리를 동일하게 간주하는 기본 동작을 사용하지 않도록 설정함으로써, 응용 프로그램이 .NET Framework의 서로 다른 두 구현에서 같은 어셈블리를 참조할 수 있도록 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<assemblyBinding > 요소  
\<되어 supportPortability > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|PKT|필수 특성입니다.<br /><br /> 문자열로 서 영향을 받는 어셈블리의 공개 키 토큰을 지정합니다.|  
|사용|선택적 특성입니다.<br /><br /> 지정된 된.NET Framework 어셈블리의 구현 간의 이식성에 대 한 지원을 설정할지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|true|지정된 된.NET Framework 어셈블리의 구현 간의 이식성에 대 한 지원을 사용 하도록 설정 합니다. 이 값이 기본값입니다.|  
|False|지정된 된.NET Framework 어셈블리의 구현 간의 이식성에 대 한 지원을 사용 하지 않도록 설정 합니다. 그러면 응용 프로그램을 지정된 된 어셈블리의 여러 구현에 대 한 참조가 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)],.NET Framework의 두 가지 구현 중 하나를 사용 하는 응용 프로그램에 대 한 지원을 자동으로 제공 됩니다 예를 들어.NET Framework 구현은 또는 Silverlight 구현에 대 한.NET Framework입니다. 특정.NET Framework 어셈블리의 두 가지 구현 어셈블리 바인더를 통해 동일한 것으로 표시 됩니다. 몇 가지 시나리오에서이 응용 프로그램 이식성 기능 문제가 발생합니다. 이러한 시나리오의 경우에 `<supportPortability>` 기능을 비활성화 하는 요소를 사용할 수 있습니다.  
  
 이러한 시나리오 중 하나는 어셈블리는.NET Framework 구현과 특정 참조 어셈블리의 Silverlight 구현에 대 한.NET Framework를 참조 해야 하는입니다. 예를 들어 Windows Presentation Foundation (WPF)에서 작성 된 XAML 디자이너 참조 디자이너의 사용자 인터페이스 및 Silverlight 구현에 포함 된 WPF의 하위 집합에 대 한 두는 WPF 데스크톱 구현 해야 합니다. 기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다. 이 요소는 기본 동작을 사용 하지 않도록 설정 하 고 컴파일이 성공 하도록 합니다.  
  
> [!IMPORTANT]
>  정보를 전달 하는 공용 언어 런타임의 어셈블리 바인딩 논리를 컴파일러에 대 한 순서를 사용 해야 하는 `/appconfig` 컴파일러 옵션을이 요소를 포함 하는 app.config 파일의 위치를 지정 합니다.  
  
## <a name="example"></a>예  
 다음 예에서는 응용 프로그램을.NET Framework 구현은 두 구현 모두에 존재 하는.NET Framework 어셈블리의 Silverlight 구현에 대 한.NET Framework에 대 한 참조가 있습니다. `/appconfig` 이 app.config 파일의 위치를 지정 컴파일러 옵션을 사용 해야 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [/appconfig (C# 컴파일러 옵션)](http://msdn.microsoft.com/library/ee523958.aspx)  
 [.NET framework 어셈블리 통합 개요](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
