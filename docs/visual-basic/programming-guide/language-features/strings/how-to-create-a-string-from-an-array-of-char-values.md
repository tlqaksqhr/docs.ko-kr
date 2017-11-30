---
title: "방법: Char 값으로 이루어진 배열로 문자열 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>방법: Char 값으로 이루어진 배열로 문자열 만들기(Visual Basic)
이 예제에서는 개별 문자에서 문자열 "abcd"를 만듭니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 메서드는 특수 요구 사항이 없습니다.  
  
 구문을 `"a"c`, 여기서는 단일 `c` 와 인용 부호 안에 단일 문자, 문자 리터럴 만드는 데 사용 됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Null 문자 (같음 `Chr(0)`) 문자열에서 예기치 않은 결과가 발생할 문자열을 사용 하는 경우. Null 문자는 문자열에 포함 될 수 있지만 null 문자 다음 상황에 따라 표시 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String>  
 [Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
