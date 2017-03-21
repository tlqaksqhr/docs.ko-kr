---
title: "LINQ to Objects (Visual Basic) | Microsoft 문서"
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d2bc048fea9affd4998430783d20b978317f3897
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects(Visual Basic)
LINQ 사용 하는 "LINQ 개체"를 의미를 사용 하 여 쿼리 <xref:System.Collections.IEnumerable>또는 <xref:System.Collections.Generic.IEnumerable%601>컬렉션의 중간 LINQ 공급자 또는와 같은 API를 사용 하지 않고 직접 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) 또는 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> LINQ를 사용 하 여 모든 열거 가능 컬렉션을 같은 쿼리를 <xref:System.Collections.Generic.List%601>, <xref:System.Array>, 또는 <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601> 컬렉션은 사용자 지정 중이거나.NET Framework API에서 반환 될 수 있습니다.  
  
 기본적으로 LINQ to Objects 컬렉션에는 새로운 방법을 나타냅니다. 이전에는 컬렉션에서 데이터를 검색하는 방법을 지정하는 복잡한 `For Each` 루프를 작성해야 했습니다. LINQ 사용 하 여 검색을 설명 하는 선언적 코드를 작성 합니다.  
  
 LINQ 쿼리 기존의 비해 세 가지 주요 이점을 제공 하는 또한 `For Each` 루프:  
  
1.  보다 간결하며 쉽게 읽을 수 있습니다(특히 여러 조건을 필터링하는 경우).  
  
2.  최소한의 응용 프로그램 코드로도 강력한 필터링, 순서 지정 및 그룹화 기능을 제공합니다.  
  
3.  거의 또는 전혀 수정하지 않고도 다른 데이터 소스에 이식할 수 있습니다.  
  
 일반적으로 복잡할수록 기존의 반복 기술 대신 LINQ를 사용 하 여 얻게 될 더 큰 이점을, 데이터에 대해 수행 하려는 작업입니다.  
  
 이 섹션의 목적은 몇 가지 예제를 통해 LINQ를 사용을 보여 주는 것입니다. 여기서 설명하는 방식 외에도 다양한 방식을 사용할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 문자열 및 문자열 컬렉션을 쿼리하고 변환에 LINQ를 사용할 수 있는 방법을 설명 합니다. 또한 이러한 원칙을 설명하는 항목의 링크도 제공합니다.  
  
 [LINQ 및 리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 LINQ에 리플렉션을 사용 하는 방법을 보여 주는 샘플에 연결 합니다.  
  
 [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 파일 시스템과 상호 작용 하도록 LINQ를 사용할 수 있는 방법을 설명 합니다. 또한 이러한 개념을 설명하는 항목의 링크도 제공합니다.  
  
 [방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 C#에서 ArrayList를 쿼리 하는 방법을 보여 줍니다.  
  
 [방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 확장 메서드를 추가 하 여 LINQ 쿼리에 사용할 수 있는 메서드 집합을 확장 하는 방법에 설명 된 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601>  
  
 [언어 통합 쿼리 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 LINQ를 설명 하 고 쿼리를 수행 하는 코드 예제를 제공 하는 항목에 대 한 링크를 제공 합니다.
