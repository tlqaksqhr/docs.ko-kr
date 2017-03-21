---
title: "LINQ Querying2에 대 한 데이터 원본을 사용 | Microsoft 문서"
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
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
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
ms.openlocfilehash: 34bdc4e056d982799eac35eb2398dd3f23f6f351
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>LINQ 쿼리에 대한 데이터 소스 활성화
확장 하는 방법은 여러 가지가 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 모든 데이터 소스를 쿼리할 수 있도록는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 패턴입니다. 데이터 소스의 예를 몇 가지 들자면 데이터 구조, 웹 서비스, 파일 시스템 또는 데이터베이스가 있습니다. 쿼리의 구문과 패턴은 변경되지 않으므로 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 패턴을 사용하면 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리가 활성화된 데이터 소스를 클라이언트가 쉽게 쿼리할 수 있습니다. 하는 방법 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 확장 될 수 있습니다 이러한 데이터 원본에는 다음과 같습니다.  
  
-   구현 된 <xref:System.Collections.Generic.IEnumerable%601>인터페이스를 사용 하도록 설정 하는 종류에 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 해당 형식의 개체를 쿼리 하.</xref:System.Collections.Generic.IEnumerable%601>  
  
-   와 같은 표준 쿼리 연산자 메서드를 만들어 <xref:System.Linq.Enumerable.Where%2A>및 <xref:System.Linq.Enumerable.Select%2A>사용자 지정을 사용 하도록 설정 하는 형식을 확장 하는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를.</xref:System.Linq.Enumerable.Select%2A> </xref:System.Linq.Enumerable.Where%2A>  
  
-   구현 하는 데이터 원본에 대 한 공급자 만들기는 <xref:System.Linq.IQueryable%601>인터페이스.</xref:System.Linq.IQueryable%601> 이 인터페이스를 구현하는 공급자는 원격 실행과 같이 사용자 지정 방식으로 실행할 수 있는 식 트리의 형태로 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 받습니다.  
  
-   기존을 활용 하는 데이터 원본에 대 한 공급자 만들기 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 기술 합니다. 이러한 공급자를 사용하면 쿼리뿐만 아니라 사용자 정의 형식에 대한 삽입, 업데이트 및 삭제 작업과 매핑을 수행할 수 있습니다.  
  
 이 항목에서는 이러한 옵션에 대해 설명합니다.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>데이터 소스의 LINQ 쿼리를 활성화하는 방법  
  
### <a name="in-memory-data"></a>메모리 내 데이터  
 두 가지 방법으로 사용 하도록 설정할 수 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 메모리 내 데이터의 쿼리 합니다. 데이터가 구현 하는 형식의 경우 <xref:System.Collections.Generic.IEnumerable%601>를 사용 하 여 데이터를 쿼리할 수 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 개체에.</xref:System.Collections.Generic.IEnumerable%601> 하는 경우는 바람직하지 구현 하 여 형식의 열거형을 활성화 하는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스를 정의할 수 있습니다 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 표준 쿼리 연산자 메서드 또는 작성 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 형식을 확장 하는 표준 쿼리 연산자 메서드.</xref:System.Collections.Generic.IEnumerable%601> 표준 쿼리 연산자의 사용자 지정 구현에서는 지연된 실행을 사용하여 결과를 반환해야 합니다.  
  
### <a name="remote-data"></a>원격 데이터  
 활성화 하는 가장 좋은 방법은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 을 구현 하는 원격 데이터 원본의 쿼리는 <xref:System.Linq.IQueryable%601>인터페이스.</xref:System.Linq.IQueryable%601> 하지만 이 방식은 데이터 소스에서 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 같은 공급자를 확장하는 방식과 다릅니다. 기존 확장 하기 위한 공급자 모델은 없습니다 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 기술을 같은 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], 다른 유형의 데이터 원본에서 사용할 수 있는 [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)]합니다.  
  
## <a name="iqueryable-linq-providers"></a>IQueryable LINQ 공급자  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]구현 하는 공급자 <xref:System.Linq.IQueryable%601>의 복잡성에 다양할 수 있습니다.</xref:System.Linq.IQueryable%601> 이 단원에서는 이러한 복잡성의 차이에 대해 설명합니다.  
  
 덜 복잡한 `IQueryable` 공급자는 웹 서비스의 단일 메서드와 인터페이스할 수도 있습니다. 이러한 형식의 공급자는 쿼리에 처리할 특정 정보가 있다고 가정하므로 매우 한정적이며, 대개 단일 결과 형식을 노출하는 폐쇄형 형식 시스템을 갖고 있습니다. 예를 들어을 사용 하 여 대부분의 쿼리 실행은 로컬에서 수행 된 <xref:System.Linq.Enumerable>표준 쿼리 연산자의 구현입니다.</xref:System.Linq.Enumerable> 복잡성이 낮은 공급자는 식 트리에서 쿼리를 나타내는 하나의 메서드 호출 식만 검사하고 쿼리의 나머지 논리는 다른 곳에서 처리되도록 할 수 있습니다.  
  
 복잡성이 보통인 `IQueryable` 공급자는 부분적으로 표현되는 쿼리 언어가 있는 데이터 소스를 대상으로 할 수 있습니다. 공급자가 웹 서비스를 대상으로 하는 경우 둘 이상의 웹 서비스 메서드에 대한 인터페이스를 제공하고 쿼리가 노출하는 질문에 따라 호출할 메서드를 선택할 수 있습니다. 복잡성이 보통인 공급자는 복잡성이 낮은 공급자보다 풍부한 형식 시스템을 가질 수 있지만 여전히 고정된 형식 시스템을 유지합니다. 예를 들어 이 공급자는 이동 가능한 일대다 관계가 있는 형식을 노출할 수 있지만 사용자 정의 형식에 대한 매핑 기술을 제공하지 않습니다.  
  
 `IQueryable` 공급자와 같은 복잡한 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 공급자가 전체 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 SQL과 같이 표현이 가능한 쿼리 언어로 변환할 수 있습니다. 복잡한 공급자가 덜 복잡한 공급자보다 더욱 다양하고 방대한 질문을 쿼리로 처리할 수 있기 때문에 더 일반적이라 할 수 있습니다. 또한 개방형 형식 시스템을 가지므로 사용자 정의 형식을 매핑하는 확장 인프라를 포함해야 합니다. 복잡성이 높은 공급자를 개발하려면 상당한 노력이 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.IQueryable%601></xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
