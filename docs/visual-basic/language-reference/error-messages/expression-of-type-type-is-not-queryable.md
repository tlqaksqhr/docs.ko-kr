---
title: "Expression of type &lt;type&gt; is not queryable | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36593"
  - "vbc36593"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36593"
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Expression of type &lt;type&gt; is not queryable
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<type\> 형식의 식은 쿼리할 수 없습니다.LINQ 공급자에 대한 어셈블리 참조 및\/또는 네임스페이스 가져오기가 없는지 확인하십시오.  
  
 쿼리할 수 있는 형식은 <xref:System.Linq>, <xref:System.Data.Linq> 및 <xref:System.Xml.Linq> 네임스페이스에 정의되어 있습니다.  LINQ 쿼리를 수행하려면 이러한 네임스페이스 중 하나 이상을 가져와야 합니다.  
  
 <xref:System.Linq> 네임스페이스를 사용하면 LINQ를 사용하여 컬렉션, 배열 등의 개체를 쿼리할 수 있습니다.  
  
 <xref:System.Data.Linq> 네임스페이스를 사용하면 LINQ를 사용하여 ADO.NET 데이터 집합과 SQL Server 데이터베이스를 쿼리할 수 있습니다.  
  
 <xref:System.Xml.Linq> 네임스페이스를 사용하면 LINQ를 사용하여 XML을 쿼리하고 Visual Basic에서 XML 기능을 사용할 수 있습니다.  
  
 **오류 ID:** BC36593  
  
### 이 오류를 해결하려면  
  
1.  코드 파일에 <xref:System.Linq>, <xref:System.Data.Linq> 또는 <xref:System.Xml.Linq> 네임스페이스에 대한 `Import` 문을 추가합니다.  프로젝트 디자이너\(**My Project**\)의 **참조** 페이지에서 프로젝트에 필요한 네임스페이스를 가져올 수도 있습니다.  
  
2.  쿼리 소스로 지정한 형식이 쿼리 가능한 형식인지 확인합니다.  즉, <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>을 구현하는 형식인지 확인합니다.  
  
## 참고 항목  
 <xref:System.Linq>   
 <xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)