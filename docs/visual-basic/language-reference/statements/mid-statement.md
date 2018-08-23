---
title: Mid 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754164"
---
# <a name="mid-statement"></a>Mid 문
지정 된 수의 문자 대체를 `String` 다른 문자열에서 문자를 사용 하 여 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>요소  
 `Target`  
 필수. 이름을 합니다 `String` 변수를 수정 합니다.  
  
 `Start`  
 필수. `Integer` 식입니다. 문자 위치 `Target` 바꿀 텍스트가 시작 되는 위치입니다. `Start` 1부터 시작 하는 인덱스를 사용 합니다.  
  
 `Length`  
 선택 사항입니다. `Integer` 식입니다. 교체할 문자 수입니다. 생략 하면 모든 `String` 사용 됩니다.  
  
 `StringExpression`  
 필수. `String` 식의 일부를 대체 하는 `Target`합니다.  
  
## <a name="exceptions"></a>예외  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 또는 `Length` < 0입니다.|  
  
## <a name="remarks"></a>설명  
 대체 문자 수는 항상의 문자 수가 작거나 `Target`합니다.  
  
 Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수 및 `Mid` 문입니다. 이러한 요소는 모두 문자열에서 문자의 지정된 된 수에 작동 하지만 `Mid` 해당 문자를 반환 하는 함수는 `Mid` 문은 문자를 대체 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>을 참조하세요.  
  
> [!NOTE]
>  `MidB` 이전 버전의 Visual Basic의 문 문자가 아닌 바이트를의 부분 문자열을 대체 합니다. 더블 바이트 문자 집합 (DBCS) 응용 프로그램의 문자열을 변환에 주로 사용 됩니다. 모든 Visual Basic 문자열은 유니코드, 및 `MidB` 는 지원 되지 않습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 `Mid` 문을 다른 문자열에 지정 된 개수의 문자열 변수에 문자를 바꿉니다.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>요구 사항  
 **: Namespace** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:** `Strings`  
  
 **어셈블리:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Visual Basic의 문자열 소개](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
