---
title: "방법: Visual Basic에서 문자열 안의 문자에 액세스"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>방법: Visual Basic에서 문자열 안의 문자에 액세스
사용 하는 방법을 보여 주는이 예제는 <xref:System.String.Chars%2A> 문자는 문자열에 지정된 된 위치에 액세스 하려면 속성입니다.  
  
## <a name="example"></a>예제  
 경우에 따라 문자 및 문자열에서 문자열 내에서 해당 문자의 위치에 대 한 데이터가 있어야 유용 합니다. 문자의 배열 문자열 생각할 수 있습니다 (`Char` 인스턴스);를 통해 해당 문자의 인덱스를 참조 하 여 특정 문자를 검색할 수 있습니다는 <xref:System.String.Chars%2A> 속성입니다.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 `index` 의 매개 변수는 <xref:System.String.Chars%2A> 속성은 0부터 시작 합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.String.Chars%2A> 속성이 지정된 된 위치에 문자를 반환 합니다. 그러나 일부 유니코드 문자 1 자로 나타낼 수 있습니다. 유니코드 문자를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 배열의 문자를 문자열로 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)합니다.  
  
 <xref:System.String.Chars%2A> 속성은 <xref:System.IndexOutOfRangeException> 예외 경우는 `index` 매개 변수는 문자열의 길이 보다 크거나 그가 0 보다 작은 경우  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String.Chars%2A>  
 [방법: 문자열을 문자 배열로 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)
