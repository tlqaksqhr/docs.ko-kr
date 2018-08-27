---
title: '방법: Visual Basic에서 Object를 다른 형식으로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: f168b3021ee1dbe3c82edc22fc779767c30446b8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912015"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>방법: Visual Basic에서 Object를 다른 형식으로 변환
변환 하는 `Object` 같은 변환 키워드를 사용 하 여 다른 데이터 형식으로 변수 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제는 `Object` 변수는 `Integer` 및 `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 있음을 알고 있는 경우 내용의 `Object` 변수는 특정 데이터 형식의 편이 변수의 데이터 형식으로 변환 합니다. 계속 사용 하는 경우는 `Object` 변수에 발생 하거나 *boxing* 하 고 *unboxing* (값 형식)에 대 한 또는 *런타임에 바인딩* (참조 형식)에 대 한 합니다. 이러한 추가 실행 시간이 모든 작업과 하므로 성능이 저하 됩니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object>  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [문자열과 다른 형식 사이의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [배열 규칙](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
