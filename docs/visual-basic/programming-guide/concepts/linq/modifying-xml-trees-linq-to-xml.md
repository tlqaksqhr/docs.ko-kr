---
title: "XML 트리 수정 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cf605973e68230e9e3e09f0abf6de49635cd5845
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>XML 트리 수정 (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 XML 트리의 메모리 내 저장소입니다. 패키지를 로드 하거나 소스에서 XML 트리를 구문 분석 한 후 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 위치에 해당 트리를 수정 하 고 serialize 한 다음, 아마도 파일에 저장 하거나 원격 서버에 보낼 수 있습니다.  
  
 <xref:System.Xml.Linq.XContainer.Add%2A>.</xref:System.Xml.Linq.XContainer.Add%2A> 등의 특정 메서드를 사용 하는 메모리 내에서 트리를 수정 하는 경우  
  
 그러나 함수 생성을 사용하여 다른 모양의 새 트리를 생성하는 다른 방법도 있습니다. XML 트리에 수행해야 하는 변경 유형과 트리 크기에 따라 이 방법은 더 강력하고 개발하기 쉬울 수 있습니다. 이 단원의 첫 번째 항목에서는 이러한 두 방법을 비교합니다.  
  
## <a name="in-this-section"></a>단원 내용  
  
|항목|설명|  
|-----------|-----------------|  
|[메모리 내 XML 트리 수정과 함수 생성 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|메모리 내 XML 트리 수정과 함수 생성을 비교합니다.|  
|[XML 트리 (Visual Basic)를 요소, 특성 및 노드 추가](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|요소, 특성 또는 노드를 XML 트리에 추가하는 방법에 대해 설명합니다.|  
|[XML 트리에서 요소, 특성 및 노드 수정](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|기존 요소, 특성 또는 노드를 수정하는 방법에 대해 설명합니다.|  
|[(Visual Basic)는 XML 트리에서 요소, 특성 및 노드 제거](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|XML 트리에서 요소, 특성 또는 노드를 제거하는 방법에 대해 설명합니다.|  
|[이름/값 쌍 (Visual Basic)를 유지 관리](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|이름/값 쌍으로 가장 잘 유지되는 응용 프로그램 정보(예: 구성 정보 또는 전역 설정)를 유지 관리하는 방법에 대해 설명합니다.|  
|[방법: 전체 XML 트리 (Visual Basic)에 대 한는 Namespace를 변경 합니다.](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|XML 트리를 한 네임스페이스에서 다른 네임스페이스로 이동하는 방법을 보여 줍니다.|  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 가이드 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
