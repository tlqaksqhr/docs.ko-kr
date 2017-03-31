---
title: "do(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 95655432bde750de54996daaa2e9457a420d7c80
ms.lasthandoff: 03/13/2017

---
# <a name="do-c-reference"></a>do(C# 참조)
`do` 문은 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행합니다. 루프의 본문이 단일 문으로 구성되지 않은 경우 중괄호(`{}`)로 묶어야 합니다. 이 경우 중괄호는 선택 사항입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `x` 변수가 5보다 작은 한 `do-while` 루프 문이 실행됩니다.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 [while](../../../csharp/language-reference/keywords/while.md) 문과 달리 `do-while` 루프는 조건식이 계산되기 전에 한 번 실행됩니다.  
  
 `do-while` 블록의 어느 지점에서나 [break](../../../csharp/language-reference/keywords/break.md) 문을 사용하여 루프를 중단할 수 있습니다. [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용하여 `while` 식 계산 문을 직접 실행할 수 있습니다. `while` 식이 true로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다. 식이 false로 계산될 경우 `do-while` 루프 다음의 첫 번째 문에서 계속 실행됩니다.  
  
 또한 `do-while` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 종료할 수 있습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [do-while 문(C++)](https://docs.microsoft.com/cpp/cpp/do-while-statement-cpp)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)
