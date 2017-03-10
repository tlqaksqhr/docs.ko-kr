---
title: "/target:exe (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/exe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#], /target:exe"
  - "/target compiler options [C#], /target:exe"
  - "-target compiler options [C#], /target:exe"
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# /target:exe (C# Compiler Options)
**\/target:exe** 옵션을 사용하면 컴파일러에서는 실행 가능한 콘솔 응용 프로그램\(EXE\)을 만듭니다.  
  
## 구문  
  
```  
/target:exe  
```  
  
## 설명  
 **\/target:exe** 옵션은 기본적으로 설정되어 있습니다.  이 경우 확장명이 .exe인 실행 파일이 만들어집니다.  
  
 Windows 프로그램 실행 파일을 만들려면 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)를 사용합니다.  
  
 [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션 다음에 별도로 이름을 지정하지 않으면 [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 메서드를 포함하는 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.  
  
 명령줄에서 지정할 경우, 다음 **\/out** 또는 **\/target:module** 옵션까지의 모든 파일이 .exe 파일을 만드는 데 사용됩니다.  
  
 .exe로 컴파일되는 소스 코드 파일에서는 하나의 **Main** 메서드만 필요합니다.  [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 컴파일러 옵션을 사용하면 코드에 **Main** 메서드를 가진 클래스가 둘 이상 있는 경우 **Main** 메서드를 포함할 클래스를 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **출력 형식** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 예제  
 다음 명령줄은 각각 `in.cs`를 컴파일하여 `in.exe`를 만듭니다.  
  
```  
csc /target:exe in.cs  
csc in.cs  
```  
  
## 참고 항목  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)