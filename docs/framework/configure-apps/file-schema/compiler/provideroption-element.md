---
title: "&lt;providerOption&gt; 요소 | Microsoft Docs"
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
  - "provideroption"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<provideroption> 요소"
  - "provideroption 요소"
  - "providerOptions"
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: 22
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# &lt;providerOption&gt; 요소
언어 공급자의 컴파일러 버전 특성을 지정합니다.  
  
## 구문  
  
```  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 특성입니다.<br /><br /> 예를 들어 "CompilerVersion"과 같은 옵션 이름을 지정합니다.|  
|`value`|필수 특성입니다.<br /><br /> 예를 들어 "v3.5"와 같은 옵션 값을 지정합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|[\<system.codedom\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자의 컴파일러 구성 설정을 지정합니다.|  
|[\<compilers\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소의 컨테이너로, 0개 이상의 `<compiler>` 요소가 포함됩니다.|  
|[\<compiler\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|언어 공급자의 컴파일러 구성 특성을 지정합니다.|  
  
## 설명  
 .NET Framework 버전 3.5에서 CodeDOM\(코드 문서 개체 모델\) 코드 공급자는 `<providerOption>` 요소를 사용하여 공급자별 옵션을 지원할 수 있습니다.  
  
 .NET Framework 3.5는 업데이트된 .NET Framework 2.0 어셈블리를 포함하며 새 형식이 포함된 새 버전인 3.5 어셈블리를 제공합니다.  Microsoft C\# 및 Visual Basic 코드 공급자는 .NET Framework 2.0 어셈블리에 포함되어 있지만 버전 3.5 컴파일러를 지원할 수 있도록 업데이트되었습니다.  기본적으로 업데이트된 코드 공급자는 버전 2.0 컴파일러용 코드를 생성합니다.  `<providerOption>` 요소를 사용하여 대상 컴파일러 버전을 3.5로 변경할 수 있습니다.  이렇게 하려면 `name` 특성에 대해 "CompilerVersion"을, `value` 특성에 대해 "v3.5"를 지정합니다.  버전 번호 앞에 소문자 "v"를 추가해야 합니다.  
  
 `<providerOption>` 요소를 .NET Framework 2.0 Machine.config 또는 루트 Web.config 파일에 추가하여 버전 사양을 전역으로 만들 수 있습니다.  Machine.config 파일에서 기본 컴파일러 버전을 3.5로 업데이트하는 경우 응용 프로그램 구성 파일에 있는 `<providerOption>` 요소를 사용하여 응용 프로그램별로 해당 버전을 2.0으로 다시 변경할 수 있습니다.  
  
 CodeDOM 코드 공급자 구현자는 <xref:System.Collections.Generic.IDictionary%602> 형식의 `providerOptions` 매개 변수를 사용하는 생성자를 제공하여 사용자 지정 옵션을 처리할 수 있습니다.  
  
## 예제  
 다음 예제에서는 C\# 코드 공급자 버전 3.0이 사용되도록 지정하는 방법을 보여 줍니다.  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
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