---
title: "/target:winexe (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:winexe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/target compiler options [C#], /target:winexe"
  - "-target compiler options [C#], /target:winexe"
  - "target compiler options [C#], /target:winexe"
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:winexe (C# Compiler Options)
**\/target:winexe** 옵션을 사용하면 컴파일러에서는 실행 가능한 Windows 프로그램\(EXE\)을 만듭니다.  
  
## 구문  
  
```  
/target:winexe  
```  
  
## 설명  
 이 경우 확장명이 .exe인 실행 파일이 만들어집니다.  Windows 프로그램은 .NET Framework 라이브러리나 Win32 API를 사용하여 사용자 인터페이스를 제공합니다.  
  
 콘솔 응용 프로그램을 만들려면 [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)를 사용합니다.  
  
 [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션 다음에 별도로 이름을 지정하지 않으면 [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 메서드를 포함하는 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.  
  
 명령줄에서 지정할 경우 다음 **\/out** 또는 [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션까지의 모든 파일이 Windows 프로그램을 만드는 데 사용됩니다.  
  
 .exe로 컴파일되는 소스 코드 파일에서는 하나의 **Main** 메서드만 필요합니다.  [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 옵션을 사용하면 코드에 **Main** 메서드를 가진 클래스가 둘 이상 있는 경우 **Main** 메서드를 포함할 클래스를 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **출력 형식** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하여 Windows 프로그램을 만듭니다.  
  
```  
csc /target:winexe in.cs  
```  
  
## 참고 항목  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)