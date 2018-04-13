---
title: '방법: Visual Basic에서 Object를 다른 형식으로 변환'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>방법: Visual Basic에서 Object를 다른 형식으로 변환
변환 된 `Object` 같은 변환 키워드를 사용 하 여 다른 데이터 형식으로 변수 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `Object` 변수를 프로그램 `Integer` 및 `String`합니다.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 알고 있는 경우의 내용을 `Object` 변수는 특정 데이터 형식의 하는 것이 변수를 해당 데이터 형식으로 변환 합니다. 계속 사용 하는 경우는 `Object` 변수에 발생 하거나 *boxing* 및 *unboxing* (값 형식)에 대 한 또는 *런타임에 바인딩* (참조 형식)에 대 한 합니다. 이러한 추가 실행 시간이 모든 작업과 하므로 성능이 저하 됩니다.  
  
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
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
