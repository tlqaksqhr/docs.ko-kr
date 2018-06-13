---
title: '&lt;enforceFIPSPolicy&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746217"
---
# <a name="ltenforcefipspolicygt-element"></a>&lt;enforceFIPSPolicy&gt; 요소
암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<enforceFIPSPolicy > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 암호화 알고리즘이 FIPS와 호환 되도록 컴퓨터 구성 요구 사항의 적용을 사용할 것인지를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|컴퓨터가 fips 호환 암호화 알고리즘을 요구 하도록 구성 하는 경우 해당 요구 사항이 적용 됩니다. 클래스에 FIPS를 생성자와 호환 되지 않는 알고리즘을 구현 하는 경우 또는 `Create` 해당 클래스에 대 한 메서드는 해당 컴퓨터에서 실행 될 때 예외를 throw 합니다. 이 값이 기본값입니다.|  
|`false`|응용 프로그램에서 사용 되는 암호화 알고리즘 컴퓨터 구성에 관계 없이 FIPS와 호환 되도록 필요 하지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 2.0 부터는 암호화 알고리즘을 구현 하는 클래스의 생성 하는 컴퓨터의 구성에 의해 제어 됩니다. 컴퓨터 FIPS를 준수 해야 하는 알고리즘을 요구 하도록 구성 된 FIPS와 호환 되지 않는 알고리즘을 구현 하는 클래스를 해당 클래스의 인스턴스를 만들려고 시도 예외가 throw 됩니다. 생성자를 throw는 <xref:System.InvalidOperationException> 예외를 및 `Create` 메서드에서 throw 한 <xref:System.Reflection.TargetInvocationException> 예외는 내부 조인 된 <xref:System.InvalidOperationException> 예외입니다.  
  
 경우 응용 프로그램이 해당 구성을 사용 해야 하는 컴퓨터에서 실행 응용 프로그램을 사용 하 여 FIPS와 호환 되지 않는 알고리즘을 사용할 수 있습니다이 요소 프로그램 구성 파일에서에서 공용 언어 런타임 (CLR)을 방지 하기 위해 FIPS 준수를 강제 적용 합니다. 에 도입 된이 요소는 [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]합니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 CLR FIPS 준수를 강제 적용 하지 못하도록 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [암호화 모델](../../../../../docs/standard/security/cryptography-model.md)
