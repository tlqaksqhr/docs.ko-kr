---
title: '방법: 문자열 내에서 검색(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647685"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>방법: 문자열 내에서 검색(Visual Basic)
이 예제에서는 호출는 <xref:System.String.IndexOf%2A> 에서 메서드는 <xref:System.String> 개체 맨 처음 발견 되는 부분 문자열의 인덱스를 보고 합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `Imports` 문을 지정 하는 <xref:System> 네임 스페이스입니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.String.IndexOf%2A> 메서드 맨 처음 발견 되는 부분 문자열의 첫 번째 문자의 위치를 보고 합니다. 인덱스는 0부터 즉 문자열의 첫 번째 문자에 인덱스 0.  
  
 경우 <xref:System.String.IndexOf%2A> 는 부분 문자열을 찾지 못하면-1을 반환 합니다.  
  
 <xref:System.String.IndexOf%2A> 메서드는 대/소문자 구분 하며 현재 문화권을 사용 합니다.  
  
 오류를 제어에 대 한 문자열 검색을 포함 하려는 `Try` 블록는 [시도 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String.IndexOf%2A>  
 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)
