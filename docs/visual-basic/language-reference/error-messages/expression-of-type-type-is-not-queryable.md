---
title: "형식의 식은 &lt;형식&gt; 는 쿼리할 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
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
ms.openlocfilehash: 1e7e1e2652cf730ef6d14b0579d8a3ee3de67fbb
ms.lasthandoff: 03/13/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>형식의 식은 &lt;형식&gt; 는 쿼리할 수 없습니다
형식의 식은 \<유형 >는 쿼리할 수 없습니다. LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기를 이동 되지 않았는지 확인 합니다.  
  
 쿼리 가능 형식은에 정의 되는 <xref:System.Linq>, <xref:System.Data.Linq>, 및 <xref:System.Xml.Linq>네임 스페이스.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> LINQ 쿼리를 수행 하려면 이러한 네임 스페이스 중 하나 이상을 가져와야 합니다.  
  
 <xref:System.Linq>네임 스페이스를 사용 하면 쿼리 개체 컬렉션 및 배열과 같은 LINQ를 사용 하 여.</xref:System.Linq>  
  
 <xref:System.Data.Linq>네임 스페이스를 사용 하면 LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.</xref:System.Data.Linq>  
  
 <xref:System.Xml.Linq>네임 스페이스를 사용 하면 XML 쿼리를 Visual Basic의 XML 기능을 사용 하 고 LINQ를 사용 하 여.</xref:System.Xml.Linq>  
  
 **오류 ID:** BC36593  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  추가 `Import` 에 대 한 정보는 <xref:System.Linq>, <xref:System.Data.Linq>, 또는 <xref:System.Xml.Linq>네임 스페이스를 코드 파일.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> 사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다는 **참조** 프로젝트 디자이너의 페이지 (**My Project**).  
  
2.  쿼리 원본 쿼리 가능한 형식으로 식별 하는 형식을 확인 합니다. 즉, <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 형식  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 <xref:System.Data.Linq></xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
