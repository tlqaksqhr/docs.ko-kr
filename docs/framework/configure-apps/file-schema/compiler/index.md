---
title: "컴파일러 및 언어 공급자 설정 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ff278413e2fc91201eeca26fccf9dc5b4fb9d1a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="compiler-and-language-provider-settings-schema"></a>컴파일러 및 언어 공급자 설정 스키마
컴파일러 및 언어 공급자 설정은 사용 가능한 언어 공급자에 대한 컴파일러 구성 요소를 지정합니다. 각 컴파일러 구성 요소는 코드 공급자 형식 이름, 컴파일러 매개 변수, 지원되는 언어 이름 및 지원되는 파일 확장명을 지정합니다.  
  
 .NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다. 개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.  
  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.|  
|[\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소용 컨테이너입니다. 0개 이상의 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함되어 있습니다.|  
|[\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.|  
  
## <a name="example"></a>예  
 다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
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
 [\<compiler> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
