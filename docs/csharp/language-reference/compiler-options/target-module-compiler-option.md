---
title: "/target:module (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:module"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:module"
  - "target compiler options [C#], /target:module"
  - "/target compiler options [C#], /target:module"
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:module (C# Compiler Options)
이 옵션을 사용하면 컴파일러에서 어셈블리 매니페스트를 생성하지 않습니다.  
  
## 구문  
  
```  
/target:module  
```  
  
## 설명  
 기본적으로, 이 옵션과 함께 컴파일 할 때 생성되는 출력 파일의 확장명은 .netmodule 입니다.  
  
 .NET Framework 공용 언어 런타임에서는 어셈블리 매니페스트가 없는 파일을 로드할 수 없습니다.  그러나 [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하면 어셈블리 매니페스트가 없는 파일을 어셈블리 매니페스트에 통합할 수 있습니다.  
  
 단일 컴파일에서 두 개 이상의 모듈을 만들면 한 모듈의 [internal](../../../csharp/language-reference/keywords/internal.md) 형식을 컴파일의 다른 모듈에서 사용할 수 있습니다.  한 모듈의 코드가 다른 모듈의 `internal` 형식을 참조하는 경우 **\/addmodule**을 사용하여 두 모듈을 어셈블리 매니페스트로 통합해야 합니다.  
  
 Visual Studio 개발 환경에서는 모듈 만들기 기능을 지원하지 않습니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하여 `in.netmodule`을 만듭니다.  
  
```  
csc /target:module in.cs  
```  
  
## 참고 항목  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)