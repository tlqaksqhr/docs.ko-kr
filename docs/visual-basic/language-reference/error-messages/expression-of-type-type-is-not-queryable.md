---
title: "형식의 식은 &lt;형식&gt; 를 쿼리할 수 없습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords: BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f2b98bf48f0b3965929f9211c2944ff97754f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>형식의 식은 &lt;형식&gt; 를 쿼리할 수 없습니다
형식의 식은 \<유형 >를 쿼리할 수 없습니다. LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기 누락 되지 않았는지 확인 합니다.  
  
 쿼리 가능 형식에 정의 된는 <xref:System.Linq>, <xref:System.Data.Linq>, 및 <xref:System.Xml.Linq> 네임 스페이스입니다. LINQ 쿼리를 수행 하려면 이러한 네임 스페이스 중 하나 이상을 가져와야 합니다.  
  
 <xref:System.Linq> 네임 스페이스를 사용 하면 컬렉션 및 배열에 같은 쿼리 개체에 LINQ를 사용 하 여 합니다.  
  
 <xref:System.Data.Linq> 네임 스페이스를 사용 하면 LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.  
  
 <xref:System.Xml.Linq> 네임 스페이스를 사용 하면 XML 쿼리를 Visual Basic의 XML 기능을 사용 하 고 LINQ를 사용 하 여 합니다.  
  
 **오류 ID:** BC36593  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  추가 `Import` 문에 <xref:System.Linq>, <xref:System.Data.Linq>, 또는 <xref:System.Xml.Linq> 코드 파일에 네임 스페이스입니다. 사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다는 **참조** 프로젝트 디자이너의 페이지 (**My Project**).  
  
2.  쿼리의 소스는 쿼리 가능 형식으로 확인 된 형식을 확인 합니다. 구현 하는 형식 즉, <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
