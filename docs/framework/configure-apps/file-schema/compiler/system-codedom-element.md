---
title: "&lt;system.codedom&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.codedom> 요소"
  - "컴파일러 구성 요소, <system.codedom> 요소"
  - "system.codedom 요소"
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;system.codedom&gt; 요소
사용 가능한 언어 공급자의 컴파일러 구성 설정을 지정합니다.  
  
## 구문  
  
```  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<컴파일러\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소의 컨테이너로, 0개 이상의 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함됩니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<적용\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 설명  
  
## .NET Framework 버전 2.0  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) 요소에는 <xref:Microsoft.CSharp.CSharpCodeProvider> 및 <xref:Microsoft.VisualBasic.VBCodeProvider>.와 같은 .NET Framework와 함께 설치되는 기본 공급자 이외에 컴퓨터에 설치되는 언어 공급자에 대한 컴파일러 구성 설정이 들어 있습니다.  [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소에는 0개 이상의 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 들어 있습니다.  각 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자의 컴파일러 구성 특성을 지정합니다.  
  
 개발자와 컴파일러 공급업체가 새 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현을 위한 구성 설정을 컴퓨터 구성 파일\(Machine.config\)에 추가할 수 있습니다.  <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 메서드를 사용하여 기본 언어 공급자와 컴퓨터의 컴파일러 구성 설정으로 식별되는 언어 공급자를 모두 프로그래밍 방식으로 열거할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서는 .NET Framework에서 제공하는 기본 언어 공급자가 [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소에서 식별됩니다.  .NET Framework 버전 2.0의 경우 기본 언어 공급자는 [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소에서 식별되지 않지만 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> 메서드를 사용하여 열거할 수 있습니다.  
  
## .NET Framework 버전 1.0 및 1.1  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) 요소에는 컴퓨터의 언어 공급자에 대한 컴파일러 구성 설정이 들어 있습니다.  [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소에는 0개 이상의 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 들어 있습니다.  각 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자의 컴파일러 구성 특성을 지정합니다.  
  
 .NET Framework는 컴퓨터 구성 파일\(Machine.config\)의 초기 컴파일러 설정을 정의합니다.  개발자 및 컴파일러 공급업체에서는 새 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현을 위한 구성 설정을 추가할 수 있습니다.  언어 공급자와 컴퓨터의 컴파일러 구성 설정을 프로그래밍 방식으로 나열하려면 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
## 구성 파일  
 이 요소는 컴퓨터 구성 파일과 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 일반적인 컴파일러 구성을 보여 줍니다.  
  
```  
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
  
## 참고 항목  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [컴파일러 및 언어 공급자 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)   
 [\<compiler\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)