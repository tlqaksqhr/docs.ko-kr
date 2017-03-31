---
title: "입니다. 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
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
ms.openlocfilehash: 45c775fe92e61de7be2356218f33964071e96c07
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>입니다. 연산자(C# 참조)
점 연산자(`.`)는 멤버 액세스에 사용됩니다. 점 연산자는 형식 또는 네임스페이스의 멤버를 지정합니다. 예를 들어 점 연산자는 .NET Framework 클래스 라이브러리 내의 특정 메서드에 액세스하는 데 사용됩니다.  
  
 [!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.  
  
 [!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 `s` 변수에는 두 개의 멤버 `a`와 `b`가 있으며, 액세스하려면 점 연산자를 사용합니다.  
  
 [!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 예를 들어 점은 속하는 네임스페이스 또는 인터페이스를 지정하는 이름인 정규화된 이름을 형성하는 데에도 사용됩니다.  
  
 [!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 using 지시문을 사용하면 일부 이름 한정이 선택 사항이 됩니다.  
  
 [!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 하지만 식별자가 모호한 경우 정규화해야 합니다.  
  
 [!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
