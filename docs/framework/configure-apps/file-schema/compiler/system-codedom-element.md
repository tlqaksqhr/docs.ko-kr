---
title: '&lt;system.codedom&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5939fa31a2f87348922d4586e3e7b7b52066fb09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744228"
---
# <a name="ltsystemcodedomgt-element"></a>&lt;system.codedom&gt; 요소
사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.  
  
 \<구성 > 요소  
\<system.codedom > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소용 컨테이너입니다. 0개 이상의 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함되어 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<구성>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="net-framework-version-20"></a>.NET framework 버전 2.0  
 [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) 요소와 같은.NET Framework와 함께 설치 되는 기본 공급자 외에도 컴퓨터에 설치 된 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어는 <xref:Microsoft.CSharp.CSharpCodeProvider> 및 <xref:Microsoft.VisualBasic.VBCodeProvider>합니다. [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소 0 개 이상의 포함 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소입니다. 각 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.  
  
 개발자 및 컴파일러 공급 수에 구성 설정을 추가 컴퓨터 구성 파일 (Machine.config)에 대 한 새 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현 합니다. 사용 된 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 프로그래밍 방식으로 기본 언어 공급자 및 컴퓨터에서 컴파일러 구성 설정에 의해 식별 된 언어 공급자를 모두 열거 합니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서는.NET Framework에서 제공 하는 공급자에서 식별 된 기본 언어는 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소입니다. .NET Framework 버전 2.0의에서 기본 언어 공급자 식별 되지 않습니다는 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소를 사용 하 여 열거할 수 있지만 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> 메서드.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET framework 버전 1.0 및 1.1  
 [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) 요소는 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다. [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소 0 개 이상의 포함 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소입니다. 각 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.  
  
 .NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다. 개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서이 요소를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 일반적인 컴파일러 구성을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [컴파일러 및 언어 공급자 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [\<compiler> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
