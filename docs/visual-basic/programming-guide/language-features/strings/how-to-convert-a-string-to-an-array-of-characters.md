---
title: '방법: Visual Basic에서 문자열을 문자 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: c109143601e304b1ec15a60c71d65fe6bd15aae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648621"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>방법: Visual Basic에서 문자열을 문자 배열로 변환
경우에 따라 문자열을 구문 분석 하는 경우 처럼 문자열 내에서 해당 문자의 위치 및 문자열에서 문자에 대 한 데이터가 있어야 유용 합니다. 문자열의 호출 하 여 문자열에는 문자 배열을 가져올 수는 방법을 보여 주는이 예제 <xref:System.String.ToCharArray%2A> 메서드.  
  
## <a name="example"></a>예제  
 에 문자열을 분할 하는 방법을 보여 주는이 예제는 `Char` 배열 및 문자열로 문자열을 분할 하는 방법을 `String` 배열 유니코드 텍스트 문자입니다. 이 차이 대 한 이유는 두 개 이상의 유니코드 텍스트 문자를 구성할 수는 `Char` 문자 (예: 서로게이트 쌍 또는 조합 문자 시퀀스). 자세한 내용은 참조 <xref:System.Globalization.TextElementEnumerator> "에서 유니코드 표준을" 및 http://www.unicode.org합니다.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>예제  
 유니코드 텍스트 문자를 문자열로 분할 하는 것이 어려워집니다 하지만이 작업은 문자열의 시각적 표시에 대 한 정보가 필요한 경우에 필요 합니다. 사용 하 여이 예제는 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 메서드 문자열을 구성 하는 유니코드 텍스트 문자에 대 한 정보를 얻을 수 있습니다.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [방법: 문자열 안의 문자에 액세스](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)
