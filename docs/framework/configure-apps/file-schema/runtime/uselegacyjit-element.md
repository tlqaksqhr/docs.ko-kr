---
title: '&lt;useLegacyJit&gt; 요소'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd0ae1a44b41ddcae2149bcf685871a37dd01b06
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746776"
---
# <a name="ltuselegacyjitgt-element"></a>&lt;useLegacyJit&gt; 요소

공용 언어 런타임이 Just-In-Time 컴파일에 레거시 64비트 JIT 컴파일러를 사용할지를 결정합니다.  
  
\<configuration>  
\<runtime>  
\<useLegacyJit >
  
## <a name="syntax"></a>구문  
  
```xml
<useLegacyJit enabled=0|1 />
```

요소 이름 `useLegacyJit` 대 소문자를 구분 합니다.
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
| 특성 | 설명                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | 필수 특성입니다.<br><br>런타임이 레거시 64 비트 JIT 컴파일러를 사용 하는지 여부를 지정 합니다. |  
  
### <a name="enabled-attribute"></a>enabled 특성  
  
| 값 | 설명                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | 공용 언어 런타임은.NET Framework 4.6 및 이상 버전에 포함 된 새로운 64 비트 JIT 컴파일러를 사용 합니다. |  
| 1     | 공용 언어 런타임에서 이전 64 비트 JIT 컴파일러를 사용 합니다.                                                     |  
  
### <a name="child-elements"></a>자식 요소

없음
  
### <a name="parent-elements"></a>부모 요소  
  
| 요소         | 설명                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | 공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다. |  
| `runtime`       | 런타임 초기화 옵션에 대한 정보를 포함합니다.                                                        |  
  
## <a name="remarks"></a>설명  

.NET Framework 4.6 부터는 공용 언어 런타임 새로운 64 비트 컴파일러는 jit (JUST-IN-TIME) 컴파일에 기본적으로 사용 합니다. 경우에 따라이 응용 프로그램 코드를 JIT 컴파일된 64 비트 JIT 컴파일러의 이전 버전에서 동작의 차이가에 발생할 수 있습니다. 설정 하 여는 `enabled` 특성에는 `<useLegacyJit>` 요소를 `1`, 새로운 64 비트 JIT 컴파일러를 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 하 여 앱을 컴파일할 수 있습니다.  
  
> [!NOTE]
> `<useLegacyJit>` 요소 64 비트 JIT 컴파일에 영향을 줍니다. 32 비트 JIT 컴파일러는 컴파일 영향을 받지 않습니다.  
  
구성 파일 설정을 사용 하는 대신 다른 두 가지 방법으로 레거시 64 비트 JIT 컴파일러를 사용할 수 있습니다.  
  
- 환경 변수 설정

  설정의 `COMPLUS_useLegacyJit` 환경 변수 중 하나를 `0` (새로운 64 비트 JIT 컴파일러를 사용 하 여) 또는 `1` (이전 64 비트 JIT 컴파일러를 사용 하 여):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  환경 변수에 *전역 범위*에 영향을 의미 하는 모든 응용 프로그램이 컴퓨터에서 실행 됩니다. 경우 설정, 재정의할 수 있습니다 응용 프로그램 구성 파일 설정에서 합니다. 환경 변수 이름 대/소문자 구분 됩니다.
  
- 레지스트리 키 추가

  추가 하 여 레거시 64 비트 JIT 컴파일러를 사용 하도록 설정할 수는 `REG_DWORD` 값 중 하나에 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 또는 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 레지스트리에서 키입니다. 값은 이름이 `useLegacyJit`합니다. 값이 0 이면 새 컴파일러 사용 됩니다. 값이 1 이면 레거시 64 비트 JIT 컴파일러를 사용 합니다. 레지스트리 값 이름이 대/소문자 구분 됩니다.
  
  에 값을 추가 하는 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 키 컴퓨터에서 실행 되는 모든 앱에 영향을 줍니다. 에 값을 추가 하는 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 키 현재 사용자가을 실행 하는 모든 앱에 영향을 줍니다. 컴퓨터를 여러 사용자 계정으로 구성 된 경우 현재 사용자가을 실행 하는 앱만 영향을 받는 값으로 다른 사용자에 대 한 레지스트리 키에 추가 하지 않으면 합니다. 추가 `<useLegacyJit>` 요소 구성 파일에 있는 경우 레지스트리 설정을 재정의 합니다.  
  
## <a name="example"></a>예제  

다음 구성 파일 새 64 비트 JIT 컴파일러는 컴파일을 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 하 여 합니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

[\<런타임 > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
[\<구성 > 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
[마이그레이션: 새로운 64비트 JIT 컴파일러](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
