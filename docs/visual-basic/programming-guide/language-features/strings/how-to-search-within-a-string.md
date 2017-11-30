---
title: "방법: 문자열 내에서 검색(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c828d0b32fdf90e121e9d5da0bb60ab11c212f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
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
