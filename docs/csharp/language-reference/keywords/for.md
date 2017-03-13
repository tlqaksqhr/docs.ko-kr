---
title: "for(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "for"
  - "for_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "for 키워드[C#]"
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# for(C# 참조)
사용 하는 `for` 루프를 실행할 수 있습니다 하나의 문 또는 문 블록을 반복적으로 평가 되는 지정 된 식 때까지 `false`.  이 종류의 루프는 배열을 반복 하 고 반복 하는 루프를 몇 번을 미리 알고 있는 다른 응용 프로그램에 유용 합니다.  
  
## 예제  
 다음 예제에서 값을 `i` 콘솔에 작성 하 고 루프를 반복할 때마다 1 씩 증가 합니다.  
  
 [!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 `for` 문 앞의 예제에서 다음 작업을 수행 합니다.  
  
1.  첫째, 초기 변수 값 `i` 설정 됩니다.  이 단계는 한 번만 루프 반복 여러 번 방법에 관계 없이 발생합니다.  이 초기화 중 이런 현상이 반복 프로세스 밖에 생각할 수 있습니다.  
  
2.  조건을 확인할 \(`i <= 5`\), 값을 `i` 5에 비교 됩니다.  
  
    -   경우 `i` 보다 작거나 5, 조건이 `true`, 및 다음과 같은 동작이 발생 합니다.  
  
        1.  `Console.WriteLine` 문 루프의 본문에서 값을 표시 합니다 `i`.  
  
        2.  값을 `i` 1 씩 증가 합니다.  
  
        3.  루프 조건이 다시 평가 하는 2 단계 시작으로 반환 합니다.  
  
    -   경우 `i` 5 보다 크면 조건은 `false`, 루프를 종료 하 고 있습니다.  
  
 이때, 경우 초기 값을 `i` 5 보다 크면 루프의 본문을 한 번도 실행 되지 않습니다.  
  
 모든 `for` 문은 이니셜라이저, 조건 및 반복기 섹션을 정의 합니다.  일반적으로 이러한 섹션 반복 횟수를 결정 합니다.  
  
```c#  
for (initializer; condition; iterator)  
    body  
```  
  
 섹션은 다음과 같은 목적으로 사용 됩니다.  
  
-   이니셜라이저 절 초기 조건을 설정합니다.  루프를 입력 하기 전에이 섹션에서 문을 한 번만 실행 합니다.  섹션에서 다음 두 옵션 중 하나만 포함할 수 있습니다.  
  
    -   선언 하 고 초기화 하는 첫 번째 예제와 같이 로컬 루프 변수 \(`int i = 1`\).  루프를 로컬 변수 이며 루프 외부에서 액세스할 수 없습니다.  
  
    -   다음 목록에서 쉼표로 구분 된 0 개 이상의 문이 expressons  
  
        -   [할당](../../../csharp/language-reference/operators/assignment-operator.md) 문  
  
        -   메서드 호출  
  
        -   전위 또는 후 위  [증가](../../../csharp/language-reference/operators/increment-operator.md) 식으로 `++i` 또는`i++`  
  
        -   전위 또는 후 위  [감소](../../../csharp/language-reference/operators/decrement-operator.md) 식으로 `--i` 또는`i--`  
  
        -   개체를 사용 하 여  [새](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   [기다립니다](../../../csharp/language-reference/keywords/await.md) 식  
  
-   조건 구역 계산 루프 종료 해야 하거나 다시 실행 해야 하는지 여부를 결정 하는 부울 식을 포함 되어 있습니다.  
  
-   루프의 본문의 각 반복 후에 일어나는 반복기 섹션을 정의 합니다.  반복기 섹션 쉼표로 구분 된 다음 문 식을 0 개 이상 포함 되어 있습니다.  
  
    -   [할당](../../../csharp/language-reference/operators/assignment-operator.md) 문  
  
    -   메서드 호출  
  
    -   전위 또는 후 위  [증가](../../../csharp/language-reference/operators/increment-operator.md) 식으로 `++i` 또는`i++`  
  
    -   전위 또는 후 위  [감소](../../../csharp/language-reference/operators/decrement-operator.md) 식으로 `--i` 또는`i--`  
  
    -   개체를 사용 하 여  [새](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   [기다립니다](../../../csharp/language-reference/keywords/await.md) 식  
  
-   루프의 본문 문을, 빈 문, 또는 0 개 이상의 문이 중괄호로 묶어 작성 하는 문 블록으로 구성 됩니다.  
  
     중 손상 될 수 있습니다는 `for` 루프를 사용 하 여은  [브레이크](../../../csharp/language-reference/keywords/break.md) 키워드 또는 수 있는 단계를 다음 반복으로 사용 하 여은  [계속](../../../csharp/language-reference/keywords/continue.md) 키워드.  사용 하 여 모든 루프를 끝낼 수는  [goto](../../../csharp/language-reference/keywords/goto.md),  [반환](../../../csharp/language-reference/keywords/return.md), 또는  [throw](../../../csharp/language-reference/keywords/throw.md) 문.  
  
 첫 번째 예제에서는이 항목의 종류의 가장 일반적인 표시 `for` 루프 섹션의 다음 항목을 선택할 수 있도록 합니다.  
  
-   선언 하 고 로컬 루프 변수를 초기화 하는 이니셜라이저 `i`, 루프의 반복 횟수를 유지 관리 합니다.  
  
-   조건은 알려진 최종 값 5 루프 변수 값을 검사합니다.  
  
-   후 위 증분 문을 반복기 섹션을 사용 하 여 `i++`, 각 루프의 반복 수를 셉니다.  
  
 다음 덜 일반적인 선택 사항 몇 가지 예제: 이니셜라이저 섹션에서 외부 루프 변수에 값을 할당, 호출의 `Console.WriteLine` 메서드의 이니셜라이저 및 반복기 섹션 및 반복기 섹션에서 두 변수의 값을 변경 합니다.  
  
 [!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 모두 정의 하는 식의 `for` 문에서 선택적 요소입니다.  예를 들어 다음 문은 무한 루프를 만듭니다.  
  
 [!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [for 문 \(C\+\+\)](/visual-cpp/cpp/for-statement-cpp)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)