---
title: "/optimize (C# Compiler Options) | Microsoft Docs"
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
  - "/optimize"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/optimize compiler option [C#]"
  - "-o compiler option [C#]"
  - "optimize compiler option [C#]"
  - "/o compiler option [C#]"
  - "-optimize compiler option [C#]"
  - "compiler optimization [C#]"
  - "o compiler option [C#]"
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /optimize (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/optimize** 옵션을 사용하면 컴파일러에서 보다 작고 빠르고 효율적인 출력 파일을 만들기 위해 수행하는 최적화 기능을 활성화하거나 비활성화할 수 있습니다.  
  
## 구문  
  
```  
/optimize[+ | -]  
```  
  
## 설명  
 또한 **\/optimize**는 공용 언어 런타임에서 런타임에 코드를 최적화하도록 지정합니다.  
  
 기본적으로는 최적화가 사용되지 않습니다.  최적화를 사용하려면 **\/optimize\+**를 지정합니다.  
  
 어셈블리에서 사용할 모듈을 빌드할 때에는 어셈블리의 **\/optimize** 설정과 같은 설정을 사용합니다.  
  
 **\/o**는 **\/optimize**의 약식 표현입니다.  
  
 **\/optimize** 옵션과 [\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) 옵션을 함께 사용할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **코드 최적화** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>를 참조하십시오.  
  
## 예제  
 `t2.cs` 를 컴파일하고 컴파일러 최적화를 사용합니다.  
  
```  
csc t2.cs /optimize  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)