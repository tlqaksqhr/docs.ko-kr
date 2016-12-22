---
title: "/target:library (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:library"
  - "target compiler options [C#], /target:library"
  - "/target compiler options [C#], /target:library"
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:library (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/target:library** 옵션을 사용하면 컴파일러에서는 실행 파일\(EXE\) 대신 동적 연결 라이브러리\(DLL\)를 만듭니다.  
  
## 구문  
  
```  
/target:library  
```  
  
## 설명  
 DLL은 .dll 확장명으로 만들어집니다.  
  
 [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션에서 별도로 지정하지 않으면 첫 번째 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.  
  
 명령줄에서 지정할 경우, 다음 **\/out** 또는 **\/target:module** 옵션까지의 모든 파일이 .dll 파일을 만드는 데 사용됩니다.  
  
 .dll 파일을 빌드할 때 [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 메서드는 필요하지 않습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **출력 형식** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하여 `in.dll`을 만듭니다.  
  
```  
csc /target:library in.cs  
```  
  
## 참고 항목  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)