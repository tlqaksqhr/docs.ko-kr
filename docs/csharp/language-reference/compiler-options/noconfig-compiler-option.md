---
title: "/noconfig (C# Compiler Options) | Microsoft Docs"
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
  - "/noconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/noconfig compiler option [C#]"
  - "csc.rsp"
  - "-noconfig compiler option [C#]"
  - "noconfig compiler option [C#]"
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /noconfig (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/noconfig** 옵션을 사용하면 컴파일러에서는 csc.rsp 파일을 사용하여 컴파일하지 않게 됩니다. csc.rsp 파일은 csc.exe 파일과 같은 디렉터리에 있고 이 디렉터리에서 로드됩니다.  
  
## 구문  
  
```  
/noconfig  
```  
  
## 설명  
 csc.rsp 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다.  Visual Studio .NET 개발 환경에 포함되는 실제 참조는 프로젝트 형식마다 다릅니다.  
  
 csc.rsp 파일을 수정하고 명령줄에서 csc.exe를 사용하여 모든 컴파일에 포함할 추가 컴파일러 옵션을 지정할 수 있습니다\(**\/noconfig** 옵션은 제외\).  
  
 컴파일러에서는 **csc** 명령에 전달된 옵션을 마지막으로 처리합니다.  따라서 명령줄에서 지정한 옵션이 csc.rsp 파일에 있는 해당 옵션의 설정에 우선합니다.  
  
 컴파일러에서 csc.rsp 파일의 설정을 찾아 사용하지 않도록 하려면 **\/noconfig**를 지정합니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)