---
title: "/main (C# Compiler Options) | Microsoft Docs"
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
  - "/main"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-main compiler option [C#]"
  - "main compiler option [C#]"
  - "/main compiler option [C#]"
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /main (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 옵션은 **Main** 메서드가 여러 개의 클래스에 포함되어 있는 경우 프로그램의 진입점을 포함하는 클래스를 지정합니다.  
  
## 구문  
  
```  
/main:class  
```  
  
## 인수  
 `class`  
 **Main** 메서드가 있는 형식입니다.  
  
## 설명  
 컴파일에 [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 메서드가 있는 형식이 둘 이상 포함되어 있는 경우 프로그램의 진입점으로 사용할 **Main** 메서드를 포함하는 형식을 지정할 수 있습니다.  
  
 .exe 파일을 컴파일할 때 이 옵션을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **시작 개체** 속성을 수정합니다.  
  
     프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>를 참조하십시오.  
  
## 예제  
 `t2.cs`와 `t3.cs`를 컴파일하고 **Main** 메서드를 `Test2`에서 찾을 수 있도록 지정합니다.  
  
```  
csc t2.cs t3.cs /main:Test2  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)