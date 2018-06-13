---
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: e9b1da5a88c12e0d883c3afe63be98c3fa3e9173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591629"
---
# <a name="object-data-type"></a>Object Data Type
개체를 참조 하는 주소를 저장 합니다. 참조 형식 (문자열, 배열, 클래스 또는 인터페이스)를 할당할 수 있습니다는 `Object` 변수입니다. `Object` 변수 값 형식의 데이터에도 참조할 수 있습니다 (숫자, `Boolean`, `Char`, `Date`, 구조체 또는 열거형)입니다.  
  
## <a name="remarks"></a>설명  
 `Object` 데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다. 사용 하 여 `Object` 컴파일 타임에 알지 못하는 경우를 가리킬 수 있습니다 데이터 변수를 입력 합니다.  
  
 기본값 `Object` 은 `Nothing` (null 참조).  
  
## <a name="data-types"></a>데이터 형식  
 변수, 상수 또는 모든 데이터 형식의 식을 할당할 수는 `Object` 변수입니다. 데이터 형식을 결정 하는 `Object` 변수가 현재 참조 하는 데는 <xref:System.Type.GetTypeCode%2A> 의 메서드는 <xref:System.Type?displayProperty=nameWithType> 클래스입니다. 다음은 이에 대한 예입니다.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 `Object` 데이터 형식이 참조 형식이 있습니다. 그러나 Visual Basic에서 처리는 `Object` 값 형식의 데이터를 참조 하는 경우 값 형식으로 변수입니다.  
  
## <a name="storage"></a>저장소  
 참조 하는 데이터 형식에 관계 없이 `Object` 변수를 포함 데이터 값 자체를 아니라 값에 대 한 포인터입니다. 항상 컴퓨터 메모리에 4 바이트를 사용 하지만 여기 변수의 값을 나타내는 데이터 저장소에 포함 되지 않습니다. 포인터를 사용 하 여 데이터를 찾을 코드로 인해 `Object` 값 형식을 있는 변수는 액세스할 때 보다 명시적으로 형식화 된 변수 약간 더 느려집니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **Interop 고려 사항입니다.** Automation 또는 COM 개체를 위한.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 유의 포인터 형식은 다른 환경에서 Visual Basic과 호환 되는지 `Object` 유형입니다.  
  
-   **성능.** 으로 선언 된 변수는 `Object` 형식이 개체에 대 한 참조를 포함할 수 있을 만큼 유연 합니다. 그러나 메서드 또는 속성에 이러한 변수를 호출 하면 항상 발생 *런타임에 바인딩* (실행 시)입니다. 강제로 *초기 바인딩* (컴파일 시) 및 성능 향상, 특정 클래스 이름 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.  
  
     개체 변수를 선언 하는 경우 예를 들어 특정 클래스 형식에 사용 하려고 <xref:System.OperatingSystem>, 일반화 된 대신 `Object` 유형입니다. 와 같은 사용 가능한 가장 구체적인 클래스도 사용 해야 <xref:System.Windows.Forms.TextBox> 대신 <xref:System.Windows.Forms.Control>, 속성 및 메서드에 액세스할 수 있도록 합니다. 일반적으로 사용할 수 있습니다는 **클래스** 목록에 **개체 브라우저** 사용할 수 있는 클래스 이름을 찾을 수 있습니다.  
  
-   **확대 합니다.** 모든 데이터 형식 및 모든 참조 형식으로 확장 된 `Object` 데이터 형식입니다. 즉, 모든 형식을 변환할 수 있습니다 `Object` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
     그러나 다른 값 형식으로 변환 하는 경우 및 `Object`, 작업을 수행 하는 Visual Basic *boxing* 및 *unboxing*, 실행 속도가 느린 확인입니다.  
  
-   **형식 문자입니다.** `Object` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식입니다.** .NET Framework에 있는 해당 형식이 고 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `Object` 개체 인스턴스를 가리키는 변수입니다.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [방법: 두 개체가 관련이 있는지 확인](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [방법: 두 개체가 동일한지 확인](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
