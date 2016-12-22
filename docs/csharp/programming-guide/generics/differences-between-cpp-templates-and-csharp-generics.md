---
title: "C++ 템플릿과 C# 제네릭의 차이점(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "제네릭[C#], C++ 템플릿과 비교"
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C++ 템플릿과 C# 제네릭의 차이점(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# 제네릭과 C\+\+ 템플릿은 모두 매개 변수가 있는 형식을 지원하는 언어 기능입니다.  그러나 이 둘 사이에는 여러 가지 차이점이 있습니다.  구문이라는 측면에서 C\# 제네릭은 C\+\+ 템플릿처럼 복잡하지 않으며 매개 변수가 있는 형식을 보다 간편하게 다룰 수 있습니다.  또한 C\#에서는 C\+\+ 템플릿이 제공하는 모든 기능을 제공하지는 않습니다.  구현이라는 측면에서 가장 큰 차이점은, C\#의 제네릭 형식 대체는 런타임에 수행되므로 인스턴스화된 개체에서 제네릭 형식 정보가 유지된다는 점입니다.  자세한 내용은 [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)를 참조하십시오.  
  
 다음은 C\# 제네릭과 C\+\+ 템플릿 간의 주요 차이점입니다.  
  
-   C\# 제네릭은 C\+\+ 템플릿과 같은 정도의 융통성을 제공하지 않습니다.  예를 들어, C\# 제네릭 클래스에서 사용자 정의 연산자를 호출할 수는 있지만 산술 연산자를 호출할 수는 없습니다.  
  
-   C\#에서는 `template C<int i> {}` 같은 비형식 템플릿 매개 변수를 허용하지 않습니다.  
  
-   C\#에서는 명시적 특수화를 지원하지 않습니다. 즉, 특정 형식에 대한 템플릿을 사용자 지정하여 구현할 수 없습니다.  
  
-   C\#에서는 부분 특수화를 지원하지 않습니다. 즉, 형식 인수의 하위 집합을 사용자 지정하여 구현할 수 없습니다.  
  
-   C\#에서는 형식 매개 변수를 제네릭 형식에 대한 기본 클래스로 사용할 수 없습니다.  
  
-   C\#에서는 형식 매개 변수에 기본 형식을 사용할 수 없습니다.  
  
-   C\#에서는 생성된 형식을 제네릭으로 사용할 수는 있지만 제네릭 형식 매개 변수 자체가 제네릭이 될 수는 없습니다.  C\+\+에서는 템플릿 매개 변수를 허용합니다.  
  
-   C\+\+에서는 템플릿의 모든 형식 매개 변수에 대해서는 유효하지 않을 수 있는 코드가 허용되며 이러한 코드는 형식 매개 변수로 사용되는 특정 형식에 대해 검사를 받습니다.  C\#에서는 제약 조건을 충족하는 모든 형식과 함께 사용할 수 있도록 클래스의 코드를 작성해야 합니다.  예를 들어, C\+\+의 경우 형식 매개 변수의 개체에 대해 `+` 및 `-` 산술 연산자를 사용하는 함수를 작성할 수 있습니다. 이 경우 이러한 연산자를 지원하지 않는 형식으로 템플릿을 인스턴스화할 때 오류가 발생합니다.  C\#에서는 이러한 함수를 작성할 수 없고 제약 조건에서 추론 가능한 언어 구문만 사용할 수 있습니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [템플릿](/visual-cpp/cpp/templates-cpp)