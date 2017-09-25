---
title: "new 제약 조건(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="new-constraint-c-reference"></a>new 제약 조건(C# 참조)
`new` 제약 조건은 제네릭 클래스 선언의 모든 형식 인수에 매개 변수가 없는 public 생성자가 있어야 하도록 지정합니다. 새 제약 조건을 사용하려면 추상 형식일 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제와 같이 제네릭 클래스가 형식의 새 인스턴스를 만드는 경우 형식 매개 변수에 `new` 제약 조건을 적용합니다.  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>예제  
 다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 마지막에 지정해야 합니다.  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)

