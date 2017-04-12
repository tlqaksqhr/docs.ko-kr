---
title: "Visual Basic의 문자열 조작 메서드 유형 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 349cfdb3e31225f6aeba90ac29aa1c66e37c7e11
ms.lasthandoff: 03/13/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Visual Basic의 문자열 조작 메서드 유형
분석 및 문자열을 조작 하는 여러 가지가 있습니다. 일부인 일부 메서드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 내재 된 언어 및 다른 사용자는 `String` 클래스입니다.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic 언어와.NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]메서드는 언어의 기본 기능으로 사용 됩니다. 코드에서 자격 증명 없이 사용할 수 있습니다. 다음 예제에서는 일반적인 사용을 보여 줍니다.는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열 조작 명령:  
  
 [!code-vb[VbVbalrStrings #&44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 이 예제는 `Mid` 에서 직접 작업을 수행 하는 함수 `aString` 값을 할당 하 고 `bString`합니다.  
  
 Visual Basic 문자열 조작 메서드 목록이 참조 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.  
  
### <a name="shared-methods-and-instance-methods"></a>공유 메서드와 인스턴스 메서드  
 메서드로 문자열을 조작할 수도 `String` 클래스입니다. 메서드는 두 가지 `String`: *공유* 메서드 및 *인스턴스* 메서드.  
  
#### <a name="shared-methods"></a>공유 메서드  
 발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다. 이러한 메서드는 클래스의 이름으로 정규화 할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다. 예:  
  
 [!code-vb[VbVbalrStrings #&45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=fullName>메서드는 정적 메서드를 작동 하는 식에 대해 지정 하 고 결과 값을 할당 `bString`.</xref:System.String.Copy%2A?displayProperty=fullName>  
  
#### <a name="instance-methods"></a>인스턴스 메서드  
 인스턴스 메서드는 반면,의 특정 인스턴스에서 생기고 `String` 및 인스턴스 이름으로 한정 되어야 합니다. 예:  
  
 [!code-vb[VbVbalrStrings #&46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 이 예제는 <xref:System.String.Substring%2A?displayProperty=fullName>메서드가 인스턴스 메서드가 `String` (즉, `aString`).</xref:System.String.Substring%2A?displayProperty=fullName> 에 작업을 수행 `aString` 해당 값을 할당 하 고 `bString`합니다.  
  
 자세한 내용은 <xref:System.String>클래스</xref:System.String> 에 대 한 설명서를 참조 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
