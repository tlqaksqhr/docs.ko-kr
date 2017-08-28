---
title: "Boxing 및 Unboxing(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.boxing
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c783ac60735ba25db2736bd9469063c0897be22f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-and-unboxing-c-programming-guide"></a>Boxing 및 Unboxing(C# 프로그래밍 가이드)
Boxing은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)을 `object` 형식 또는 이 값 형식에서 구현된 임의의 인터페이스 형식으로 변환하는 프로세스입니다. CLR은 값 형식을 boxing할 때 값을 System.Object 내부에 래핑하고 관리되는 힙에 저장합니다. unboxing하면 개체에서 값 형식이 추출됩니다. Boxing은 암시적이며 unboxing은 명시적입니다. Boxing 및 unboxing의 개념은 개체로 처리할 수 있는 모든 값 형식에서 형식 시스템의 C#에 통합된 뷰의 기반이 됩니다.  
  
 다음 예제에서는 정수 변수 `i`를 *boxing*하고 개체 `o`에 할당합니다.  
  
 [!code-cs[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]  
  
 그런 다음 `o` 개체를 unboxing하고 정수 변수 `i`에 할당할 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]  
  
 다음 예제에서는 C#에서 boxing이 사용되는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]  
  
## <a name="performance"></a>성능  
 단순 할당에서는 boxing과 unboxing을 수행하는 데 많은 계산 과정이 필요합니다. 값 형식을 boxing할 때는 새로운 개체를 할당하고 생성해야 합니다. 정도는 약간 덜하지만 unboxing에 필요한 캐스트에도 상당한 계산 과정이 필요합니다. 자세한 내용은 [성능](https://msdn.microsoft.com/library/ms173196(VS.110).aspx)을 참조하세요.  
  
## <a name="boxing"></a>boxing  
 boxing은 가비지 수집되는 힙에 값 형식을 저장하는 데 사용됩니다. Boxing은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)을 `object` 형식 또는 이 값 형식에서 구현된 임의의 인터페이스 형식으로 암시적으로 변환하는 프로세스입니다. 값 형식을 boxing하면 힙에 개체 인스턴스가 할당되고 값이 새 개체에 복사됩니다.  
  
 다음과 같이 값 형식 변수를 선언합니다.  
  
 [!code-cs[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]  
  
 다음 문에서는 변수 `i`에 암시적으로 boxing 연산을 적용합니다.  
  
 [!code-cs[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]  
  
 이 문의 결과로 힙에 있는 `o` 형식의 값을 참조하는 `int` 개체 참조가 스택에 생성됩니다. 이 값은 변수`i`에 할당된 값 형식 값의 복사본입니다. 다음 그림에서는 두 변수 `i` 및 `o`의 차이점을 보여 줍니다.  
  
 ![BoxingConversion 그래픽](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")  
boxing 변환  
  
 다음 예제에서와 같이 명시적으로 boxing을 수행할 수도 있지만 명시적 boxing이 반드시 필요한 것은 아닙니다.  
  
 [!code-cs[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]  
  
## <a name="description"></a>설명  
 이 예제에서는 boxing을 통해 정수 변수 `i`를 개체 `o`로 변환합니다. 그런 다음 변수 `i`에 저장된 값을 `123`에서 `456`으로 변경합니다. 이 예제에서는 원래 값 형식과 boxing된 개체에 개별 메모리 위치를 사용하여 서로 다른 값을 저장하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]  
  
## <a name="unboxing"></a>unboxing  
 Unboxing은 `object` 형식에서 [값 형식](../../../csharp/language-reference/keywords/value-types.md)으로, 또는 인터페이스 형식에서 해당 인터페이스를 구현하는 값 형식으로 명시적으로 변환하는 프로세스입니다. unboxing 연산 과정은 다음과 같습니다.  
  
-   개체 인스턴스가 지정한 값 형식을 boxing한 값인지 확인합니다.  
  
-   인스턴스의 값을 값 형식 변수에 복사합니다.  
  
 다음 문은 boxing 및 unboxing 연산을 모두 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]  
  
 다음 그림에서는 이전 문의 결과를 보여 줍니다.  
  
 ![UnBoxing 변환 그래픽](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")  
unboxing 변환  
  
 런타임에 값 형식의 unboxing이 성공하려면 unboxing되는 항목은 이전에 해당 값 형식의 인스턴스를 boxing하여 생성된 개체에 대한 참조여야 합니다. `null`을 unboxing하려고 하면 <xref:System.NullReferenceException>이 발생합니다. 호환되지 않는 값 형식에 대한 참조를 unboxing하려고 하면 <xref:System.InvalidCastException>이 발생합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 잘못된 unboxing의 경우와 그 결과로 발생하는 `InvalidCastException`을 보여 줍니다. 이 예제에서는 `try` 및 `catch`를 사용하여 오류가 발생할 때 오류 메시지를 표시합니다.  
  
 [!code-cs[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]  
  
 이 프로그램의 출력은 다음과 같습니다.  
  
 `Specified cast is not valid. Error: Incorrect unboxing.`  
  
 다음 문을  
  
```  
int j = (short) o;  
```  
  
 다음과 같이 변경합니다.  
  
```  
int j = (int) o;  
```  
  
 변환이 수행되고 결과가 출력됩니다.  
  
 `Unboxing OK.`  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [값 형식](../../../csharp/language-reference/keywords/value-types.md)  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)

