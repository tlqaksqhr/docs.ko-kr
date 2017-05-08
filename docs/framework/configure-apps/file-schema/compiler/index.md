---
title: "컴파일러 및 언어 공급자 설정 스키마 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "컴파일러 구성 요소"
  - "컴파일러 구성 요소, 스키마"
  - "컴파일러 구성 설정"
  - "컴파일러 구성 설정, 스키마"
  - "구성 스키마[.NET Framework], 컴파일러 설정"
  - "구성 설정[.NET Framework], 컴파일러"
  - "언어 공급자"
  - "언어 공급자, 설정 스키마"
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 컴파일러 및 언어 공급자 설정 스키마
컴파일러 및 언어 공급자 설정은 사용 가능한 언어 공급자의 컴파일러 구성 요소를 지정합니다.  각 컴파일러 구성 요소는 코드 공급자 형식 이름, 컴파일러 매개 변수, 지원되는 언어 이름 및 지원되는 파일 확장명을 지정합니다.  
  
 .NET Framework는 컴퓨터 구성 파일\(Machine.config\)의 초기 컴파일러 설정을 정의합니다.  개발자 및 컴파일러 공급업체에서는 새 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현을 위한 구성 설정을 추가할 수 있습니다.  언어 공급자와 컴퓨터의 컴파일러 구성 설정을 프로그래밍 방식으로 나열하려면 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 [\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<컴파일러\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<컴파일러\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|요소|설명|  
|--------|--------|  
|[\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|사용 가능한 언어 공급자의 컴파일러 구성 설정을 지정합니다.|  
|[\<컴파일러\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|컴파일러 구성 요소의 컨테이너로, 0개 이상의 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함됩니다.|  
|[\<컴파일러\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|언어 공급자의 컴파일러 구성 특성을 지정합니다.|  
  
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
 [\<compiler\> 요소](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)