---
title: "&lt;compilers&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compilers> 요소"
  - "컴파일러 구성 요소, <compilers> 요소"
  - "compilers 요소"
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;compilers&gt; 요소
컴파일러 구성 요소의 컨테이너로, 0개 이상의 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함됩니다.  
  
## 구문  
  
```  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<compiler\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|언어 공급자의 컴파일러 구성 특성을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|[\<system.codedom\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자의 컴파일러 구성 설정을 지정합니다.|  
  
## 설명  
 [\<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소는 컴퓨터의 언어 공급자에 대한 컴파일러 구성 설정을 포함합니다.  각 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자의 컴파일러 구성 특성을 지정합니다.  
  
 .NET Framework는 컴퓨터 구성 파일\(Machine.config\)에서 초기 컴파일러 및 언어 공급자 설정을 정의합니다.  개발자 및 컴파일러 공급업체에서는 새 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> 구현을 위한 구성 설정을 추가할 수 있습니다.  언어 공급자와 컴퓨터의 컴파일러 구성 설정을 프로그래밍 방식으로 나열하려면 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
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
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
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