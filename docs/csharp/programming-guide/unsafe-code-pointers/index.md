---
title: "안전하지 않은 코드 및 포인터(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "보안[C#], 형식 안전성"
  - "C# 언어, 안전하지 않은 코드"
  - "형식 안전성[C#]"
  - "unsafe 키워드[C#]"
  - "안전하지 않은 코드[C#]"
  - "C# 언어, 포인터"
  - "포인터[C#], 포인터 정보"
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 안전하지 않은 코드 및 포인터(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\#에서는 형식 안전성과 보안을 유지하기 위해 기본적으로 포인터 산술 연산을 지원하지 않습니다.  그러나 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용하면 포인터를 사용할 수 있는 안전하지 않은 컨텍스트를 정의할 수 있습니다.  포인터에 대한 자세한 내용은 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) 항목을 참조하십시오.  
  
> [!NOTE]
>  CLR\(공용 언어 런타임\)에서는 안전하지 않은 코드를 비안정형 코드라고 합니다.  C\#에서 안전하지 않은 코드는 항상 위험한 것만은 아닙니다. 이는 단지 CLR에서 그 안전성을 확인할 수 없는 코드를 의미합니다.  따라서 CLR에서는 안전하지 않은 코드가 완전히 신뢰할 수 있는 어셈블리에 포함된 경우에만 이 코드를 실행합니다.  안전하지 않은 코드를 사용하는 경우 이 코드로 인해 보안상의 위험이나 포인터 오류가 발생하지 않도록 하는 것은 사용자의 책임입니다.  
  
## 안전하지 않은 코드 개요  
 안전하지 않은 코드에는 다음과 같은 속성이 있습니다.  
  
-   메서드, 형식 및 코드 블록을 안전하지 않은 것으로 정의할 수 있습니다.  
  
-   안전하지 않은 코드를 사용하면 배열 범위를 검사하지 않으므로 경우에 따라서는 이를 통해 응용 프로그램의 성능을 향상시킬 수 있습니다.  
  
-   안전하지 않은 코드는 포인터가 필요한 네이티브 함수를 호출하는 경우에 필요합니다.  
  
-   안전하지 않은 코드를 사용하면 보안과 안전성이 위험해질 수 있습니다.  
  
-   C\#에서 안전하지 않은 코드를 컴파일하려면 [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)를 사용하여 응용 프로그램을 컴파일해야 합니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [방법: 포인터를 사용하여 바이트 배열 복사](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)