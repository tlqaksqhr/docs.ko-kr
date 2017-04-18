---
title: "&lt;compiler&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compiler> 요소"
  - "컴파일러 구성 특성"
  - "컴파일러 구성 요소, <compiler> 요소"
  - "compiler 요소"
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;compiler&gt; 요소
언어 공급자의 컴파일러 구성 특성을 지정합니다.  
  
## 구문  
  
```  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`compilerOptions`|선택적 특성입니다.<br /><br /> 컴파일을 위한 추가적인 컴파일러 관련 인수를 지정합니다.  `compilerOptions` 특성 값은 일반적으로 컴파일러의 컴파일러 옵션 항목에 나열됩니다.  Visual Studio 2005 설명서의 색인에서 "컴파일러 옵션"을 검색하여 컴파일러에 대한 옵션을 찾아볼 수 있습니다.|  
|`extension`|필수 특성입니다.<br /><br /> 언어 공급자의 소스 파일에 사용되는 세미콜론으로 구분된 확장명 목록을 제공합니다.  예를 들어, ".cs"입니다.|  
|`language`|필수 특성입니다.<br /><br /> 언어 공급자가 지원하는 언어 이름의 세미콜론 구분 목록을 제공합니다.  예를 들어, "c\#;cs;csharp"입니다.|  
|`type`|필수 특성입니다.<br /><br /> 공급자 구현을 포함하는 어셈블리의 이름을 비롯하여 언어 공급자의 형식 이름을 지정합니다.  형식 이름은 [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)에 정의된 조건을 충족해야 합니다.|  
|`warningLevel`|선택적 특성입니다.<br /><br /> 기본 컴파일러 경고 수준을 지정하여 언어 공급자가 컴파일 경고를 오류로 처리하는 수준을 결정합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<providerOption\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|언어 공급자의 컴파일러 버전 특성을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|[\<system.codedom\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자의 컴파일러 구성 설정을 지정합니다.|  
|[\<compilers\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소의 컨테이너로, 0개 이상의 `<compiler>` 요소가 포함됩니다.|  
  
## 설명  
 각 `<compiler>` 요소는 특정 언어 공급자의 컴파일러 구성 특성을 지정합니다.  공급자는 특정 언어에 대해 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> 클래스를 확장합니다. `<compiler>` 요소는 언어 공급자의 컴파일러 및 코드 생성기 설정을 정의합니다.  
  
 .NET Framework는 컴퓨터 구성 파일\(Machine.config\)의 초기 컴파일러 설정을 정의합니다.  개발자 및 컴파일러 공급업체에서는 새 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현을 위한 구성 설정을 추가할 수 있습니다.  언어 공급자와 컴퓨터의 컴파일러 구성 설정을 프로그래밍 방식으로 나열하려면 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 응용 프로그램이나 웹 구성 파일의 컴파일러 요소가 컴퓨터 구성 파일의 설정을 보완하거나 재정의할 수 있습니다.  같은 언어 이름 또는 같은 확장명에 대해 둘 이상의 공급자 구현이 구성된 경우에는 마지막으로 일치하는 구성이 이전에 해당 언어 이름이나 확장명에 대해 구성된 공급자보다 우선합니다.  
  
## 구성 파일  
 이 요소는 컴퓨터 구성 파일과 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 일반적인 컴파일러 구성 요소를 보여 줍니다.  
  
```  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<compilers\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)   
 [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)   
 [compilation 요소의 compilers 요소에 대한 compiler 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)