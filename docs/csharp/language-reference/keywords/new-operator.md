---
title: "new 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0831bbbaf68c8c9e1e0e2d77ccf18e7c8b42e4a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="new-operator-c-reference"></a>new 연산자(C# 참조)
개체를 만들고 생성자를 호출하는 데 사용됩니다. 예:  
  
```  
Class1 obj  = new Class1();  
```  
  
 무명 형식의 인스턴스를 만드는 데에도 사용됩니다.  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 또한 `new` 연산자는 값 형식에 대한 기본 생성자를 호출하는 데 사용됩니다. 예:  
  
```  
int i = new int();  
```  
  
 앞의 문에서 `i`는 `int` 형식의 기본값인 `0`으로 초기화됩니다. 이 문은 다음과 동일한 효과가 있습니다.  
  
```  
int i = 0;  
```  
  
 기본값의 전체 목록은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.  
  
 모든 값 형식에 암시적으로 공용 기본 생성자가 있기 때문에 [struct](../../../csharp/language-reference/keywords/struct.md)에 대한 기본 생성자를 선언하면 오류가 발생합니다. 구조체 형식에서 매개 변수가 있는 생성자를 선언하여 해당 초기 값을 설정할 수 있지만, 이 작업은 기본값이 아닌 값이 필요한 경우에만 요구됩니다.  
  
 구조체와 같은 값 형식 개체는 스택에 생성되는 반면, 클래스와 같은 참조 형식 개체는 힙에 생성됩니다. 두 개체 형식 모두 자동으로 제거되지만 값 형식을 기반으로 하는 개체는 범위를 벗어날 때 제거되는 반면, 참조 형식을 기반으로 하는 개체는 마지막 참조가 제거된 후 지정되지 않은 시간에 제거됩니다. 많은 양의 메모리, 파일 핸들, 네트워크 연결 등의 고정된 리소스를 사용하는 참조 형식의 경우 때로는 명확한 종료를 사용하여 개체가 최대한 빨리 제거되도록 하는 것이 좋습니다. 자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.  
  
 `new` 연산자를 오버로드할 수 없습니다.  
  
 `new` 연산자가 메모리 할당에 실패할 경우 <xref:System.OutOfMemoryException> 예외를 throw합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `new` 연산자를 사용하여 `struct` 개체 및 클래스 개체가 생성 및 초기화된 다음 값이 할당됩니다. 기본값과 할당된 값이 표시됩니다.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 예제에서는 문자열의 기본값이 `null`이므로 표시되지 않습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
