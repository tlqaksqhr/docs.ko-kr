---
title: "방법: AS 및 IS 연산자를 사용한 안전한 캐스팅(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 733b67408997feb0e518db327e3eedd42f286a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>방법: AS 및 IS 연산자를 사용한 안전한 캐스팅(C# 프로그래밍 가이드)
개체는 다형성이기 때문에 기본 클래스 형식의 변수에 파생 형식이 포함될 수 있습니다. 파생 형식의 메서드에 액세스하려면 값을 파생 형식으로 다시 캐스팅해야 합니다. 그러나 이러한 경우에 단순 캐스트를 시도하면 <xref:System.InvalidCastException>이 throw될 위험이 있습니다. C#에서 [is](../../../csharp/language-reference/keywords/is.md) 및 [as](../../../csharp/language-reference/keywords/as.md) 연산자를 제공하는 것은 이런 이유 때문입니다. 이러한 연산자를 사용하여 예외가 throw되지 않고 캐스트에 성공할지 여부를 테스트할 수 있습니다. 일반적으로 `as` 연산자는 성공적으로 캐스팅할 수 있는 경우 실제로 캐스트 값을 반환하기 때문에 더 효율적입니다. `is` 연산자는 부울 값만 반환합니다. 따라서 개체의 형식을 확인하려고 하지만 실제로 캐스팅할 필요는 없는 경우에 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `is` 및 `as` 연산자를 사용하여 예외가 throw될 위험 없이 한 참조 형식에서 다른 참조 형식으로 캐스팅하는 방법을 보여 줍니다. 또한 예제에서는 `as` 연산자를 nullable 값 형식과 함께 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [유형](../../../csharp/programming-guide/types/index.md)  
 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)
