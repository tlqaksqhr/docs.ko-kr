---
title: for(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb7e83733fe026658f502b430975a0f8a27e9df3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="for-c-reference"></a>for(C# 참조)
`for` 루프를 사용하면 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행할 수 있습니다. 이러한 종류의 루프는 배열을 반복하는 데 유용하며 루프를 반복할 횟수를 미리 알고 있는 다른 응용 프로그램에 유용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 `i` 값은 콘솔에 기록되며 루프를 반복할 때마다 1씩 증가합니다.  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 이전 예제에서 `for` 문은 다음 작업을 수행합니다.  
  
1.  먼저 `i` 변수의 초기 값을 설정합니다. 이 단계는 루프가 반복되는 횟수에 관계없이 한 번만 수행됩니다. 이 초기화가 루프 프로세스 외부에서 발생한다고 생각할 수 있습니다.  
  
2.  조건(`i <= 5`)을 평가하기 위해 `i` 값을 5와 비교합니다.  
  
    -   `i`가 5보다 작거나 같으면 조건이 `true`로 평가되고 다음 작업이 수행됩니다.  
  
        1.  루프 본문의 `Console.WriteLine` 문이 `i` 값을 표시합니다.  
  
        2.  `i`의 값이 1씩 증가합니다.  
  
        3.  루프가 2단계의 시작 부분으로 돌아가 조건을 다시 평가합니다.  
  
    -   `i`가 5보다 크면 조건이 `false`로 평가되고 루프를 종료합니다.  
  
 `i`의 초기 값이 5보다 크면 루프의 본문이 한 번도 실행되지 않습니다.  
  
 모든 `for` 문은 이니셜라이저, 조건 및 반복기 섹션을 정의합니다. 이러한 섹션은 일반적으로 루프가 반복되는 횟수를 결정합니다.  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 섹션은 다음과 같은 용도로 사용됩니다.  
  
-   이니셜라이저 섹션은 초기 조건을 설정합니다. 이 섹션의 문은 루프가 시작되기 전에 한 번만 실행됩니다. 섹션에는 다음 두 가지 옵션 중 하나만 포함될 수 있습니다.  
  
    -   첫 번째 예제와 같이 로컬 루프 변수의 선언 및 초기화(`int i = 1`). 변수는 루프에 로컬이며 루프 외부에서 액세스할 수 없습니다.  
  
    -   쉼표로 구분된 다음 목록의 문 식 0개 이상  
  
        -   [assignment](../../../csharp/language-reference/operators/assignment-operator.md) 문  
  
        -   메서드 호출  
  
        -   접두사 또는 후위 [increment](../../../csharp/language-reference/operators/increment-operator.md) 식(예: `++i` 또는`i++`)  
  
        -   접두사 또는 후위 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 식(예: `--i` 또는`i--`)  
  
        -   [new](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 개체 만들기  
  
        -   [await](../../../csharp/language-reference/keywords/await.md) 식  
  
-   조건 섹션에는 루프를 종료할지 다시 실행할지를 결정하기 위해 평가되는 부일 식이 포함되어 있습니다.  
  
-   반복기 섹션은 루프의 본문을 반복할 때마다 수행되는 업을 정의합니다. 반복기 섹션에는 다음과 같은 문 식이 쉼표로 구분되어 0개 이상 포함됩니다.  
  
    -   [assignment](../../../csharp/language-reference/operators/assignment-operator.md) 문  
  
    -   메서드 호출  
  
    -   접두사 또는 후위 [increment](../../../csharp/language-reference/operators/increment-operator.md) 식(예: `++i` 또는`i++`)  
  
    -   접두사 또는 후위 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 식(예: `--i` 또는`i--`)  
  
    -   [new](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 개체 만들기  
  
    -   [await](../../../csharp/language-reference/keywords/await.md) 식  
  
-   루프의 본문은 문, 빈 문 또는 0개 이상의 문을 중괄호로 묶어 만드는 문 블록으로 구성됩니다.  
  
     [break](../../../csharp/language-reference/keywords/break.md) 키워드를 사용하여 `for` 루프를 중단하거나, [continue](../../../csharp/language-reference/keywords/continue.md) 키워드를 사용하여 다음 반복을 단계 실행할 수 있습니다. 또한 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 사용하여 루프를 종료할 수 있습니다.  
  
 이 항목의 첫 번째 예제에서는 섹션에 대해 다음 중에서 선택할 수 있는 가장 일반적인 종류의 `for` 루프를 보여 줍니다.  
  
-   이니셜라이저는 루프의 반복 횟수를 유지 관리하는 로컬 루프 변수 `i`를 선언하고 초기화합니다.  
  
-   조건은 알려진 최종 값 5에 대해 루프 변수의 값을 확인합니다.  
  
-   반복기 섹션에서는 후위 increment 문 `i++`를 사용하여 루프의 각 반복을 기록합니다.  
  
 다음 예제에서는 이니셜라이저 섹션에서 외부 루프 변수에 값 할당, 이니셜라이저와 반복기 섹션에서 `Console.WriteLine` 메서드 호출, 반복기 섹션에서 두 변수의 값 변경과 같이 여러 가지 덜 일반적인 선택 항목을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 `for` 문을 정의하는 모든 식은 선택 사항입니다. 예를 들어 다음 문은 무한 루프를 만듭니다.  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [for 문(C++)](/cpp/cpp/for-statement-cpp)  
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)
