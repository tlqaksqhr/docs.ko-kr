---
title: "방법: 쿼리 (LINQ) (Visual Basic)는 문자열의 문자에 대 한 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>방법: 문자열 (Visual Basic) (LINQ)의 문자에 대 한 쿼리
때문에 <xref:System.String>클래스는 제네릭 구현 <xref:System.Collections.Generic.IEnumerable%601>인터페이스를 문자 시퀀스로 모든 문자열을 쿼리할 수 있습니다.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String> 그러나 LINQ의 일반적인 용도 아닙니다. 복잡 한 패턴 일치 작업에 대 한 <xref:System.Text.RegularExpressions.Regex>클래스</xref:System.Text.RegularExpressions.Regex> 를 사용 하 여  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함 된 숫자의 수를 결정 하는 문자열을 쿼리 합니다. Note는 쿼리는 "" 다음 다시 처음으로 실행 됩니다. 쿼리 자체 실제 결과 저장 하지 않기 때문에 이것이 가능 합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
