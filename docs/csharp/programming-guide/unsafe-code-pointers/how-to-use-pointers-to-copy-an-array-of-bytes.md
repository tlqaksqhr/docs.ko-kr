---
title: "방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "배열[C#], byte"
  - "바이트 배열[C#]"
  - "포인터[C#], 바이트 복사"
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 예제에서는 포인터를 사용하여 배열 간에 바이트를 복사합니다.  
  
 이 예제에서는 `Copy` 메서드 내에서 포인터를 사용할 수 있게 해주는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용합니다.  [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문은 소스 및 대상 배열에 대한 포인터를 선언하는 데 사용됩니다.  이렇게 하면 소스 및 대상 배열의 메모리 내 위치가 *고정*되어 가비지 수집에 의해 이동하지 않습니다.  배열의 메모리 블록은 `fixed` 블록이 완료될 때 고정이 해제됩니다.  이 예제의 `Copy` 메서드는 `unsafe` 키워드를 사용하기 때문에 **\/unsafe** 컴파일러 옵션을 사용하여 컴파일되어야 합니다.  Visual Studio에서 이 옵션을 설정하려면 프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  **빌드** 탭에서 **안전하지 않은 코드 허용**을 선택합니다.  
  
## 예제  
 [!CODE [csProgGuidePointers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#3)]  
  
 [!CODE [csProgGuidePointers#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#18)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [\/unsafe \(Enable Unsafe Mode\)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)