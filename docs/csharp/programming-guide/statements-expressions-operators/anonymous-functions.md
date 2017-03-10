---
title: "익명 함수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "익명 함수[C#]"
  - "무명 메서드[C#]"
  - "람다 식[C#], 익명 함수로"
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# 익명 함수(C# 프로그래밍 가이드)
익명 함수는 대리자 형식과 함께 사용될 수 있는 "인라인" 문이나 식입니다.  익명 함수는 명명된 대리자를 초기화하는 데 사용되거나 명명된 대리자 형식 대신 메서드 매개 변수로 전달될 수 있습니다.  
  
 익명 함수에는 두 가지 종류가 있으며 각 익명 함수는 다음 단원에서 따로 설명합니다.  
  
-   [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  람다 식은 식 트리뿐만 아니라 대리자에도 바인딩할 수 있습니다.  
  
## C\#에서의 대리자 발전 과정  
 C\# 1.0에서는 코드의 다른 부분에 정의된 메서드를 통해 명시적으로 초기화하는 방법으로 대리자의 인스턴스를 만들었습니다.  C\# 2.0에서는 대리자 호출 시 실행될 수 있는 무명의 인라인 문 블록을 작성하기 위한 방법으로 무명 메서드라는 개념이 도입되었습니다.  C\# 3.0에는 무명 메서드와 비슷한 개념이지만 표현력이 뛰어나면서 간결한 람다 식이 도입되었습니다.  이러한 두 기능을 통칭하여 *익명 함수*라고 합니다.  일반적으로 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 3.5 이상을 대상으로 하는 응용 프로그램에서는 람다 식을 사용하는 것이 좋습니다.  
  
 다음 예제에서는 C\# 1.0부터 C\# 3.0까지 대리자 생성의 발전 과정을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#65)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [문, 식, 연산자](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)