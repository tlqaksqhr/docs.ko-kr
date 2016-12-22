---
title: "extern alias(C# 참조) | Microsoft Docs"
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
  - "alias_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "별칭[C#], extern 키워드"
  - "별칭, extern 키워드"
  - "extern 별칭 키워드[C#]"
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# extern alias(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

정규화된 형식 이름이 동일하고 버전만 다른 두 개의 어셈블리를 참조해야 할 수도 있습니다.  예를 들어 동일한 응용 프로그램에서 어셈블리의 버전을 여러 개 사용해야 할 수도 있습니다.  외부 어셈블리 별칭을 사용하면 각 어셈블리의 네임스페이스가 별칭으로 명명되어 루트 수준 네임스페이스 안에 래핑되므로 동일한 파일에서 여러 어셈블리 버전을 사용할 수 있습니다.  
  
> [!NOTE]
>  [extern](../../../csharp/language-reference/keywords/extern.md) 키워드는 메서드 한정자로도 사용되어 비관리 코드로 작성된 메서드를 선언합니다.  
  
 정규화된 형식 이름이 동일한 두 개의 어셈블리를 참조하려면 다음과 같이 명령 프롬프트에서 별칭을 지정해야 합니다.  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 이렇게 하면 외부 별칭 `GridV1` 및 `GridV2`가 만들어집니다.  이러한 별칭을 한 프로그램에서 사용하려면 `extern` 키워드를 사용하여 별칭을 참조합니다.  예를 들면 다음과 같습니다.  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 각 외부 별칭 선언에서는 전역 네임스페이스와 같은 수준\(하위 수준은 제외\)에 있는 추가 루트 수준 네임스페이스를 선언합니다.  따라서 정규화된 이름을 사용하지 않고도 적절한 네임스페이스 별칭을 루트로 하여 모호성 문제 없이 각 어셈블리의 형식을 참조할 수 있습니다.  
  
 앞의 예제에서 `GridV1::Grid`는 `grid.dll`의 표 컨트롤이며 `GridV2::Grid`는 `grid20.dll`의 표 컨트롤입니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [:: 연산자](../Topic/::%20Operator%20\(C%23%20Reference\).md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)