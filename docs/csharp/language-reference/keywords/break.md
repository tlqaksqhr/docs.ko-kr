---
title: "break(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- break
- break_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
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
ms.openlocfilehash: 1ad255ce1b57da81b791897044d1038f0ef4981a
ms.lasthandoff: 03/13/2017

---
# <a name="break-c-reference"></a>break(C# 참조)
`break` 문은 배치된 지점에서 가장 가까운 바깥쪽 루프 또는 [switch](../../../csharp/language-reference/keywords/switch.md) 문을 종료합니다. 제어는 종료된 문 뒤의 문으로 전달됩니다(있는 경우).  
  
## <a name="example"></a>예제  
 이 예제의 조건문에는 1부터 100까지 개수를 계산하는 카운터가 포함되지만 `break` 문은 4회 계산 후에 루프를 종료합니다.  
  
 [!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]  
  
## <a name="example"></a>예제  
 이 예제에서 `break` 문은 내부 중첩 루프를 중단하고 제어를 외부 루프에 반환하는 데 사용됩니다.  
  
 [!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]  
  
## <a name="example"></a>예제  
 이 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `break`의 사용을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]  
  
 `4`를 입력하면 다음과 같이 출력됩니다.  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [점프 문](../../../csharp/language-reference/keywords/jump-statements.md)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)
