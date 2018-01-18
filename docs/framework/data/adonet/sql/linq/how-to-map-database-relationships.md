---
title: "방법: 데이터베이스 관계 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b1637fd322468f743c29605b31c3c6849bd78aa6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-map-database-relationships"></a>방법: 데이터베이스 관계 매핑
항상 동일하게 유지되는 모든 데이터 관계를 엔터티 클래스에서 속성 참조로 인코딩할 수 있습니다. 예를 들어 Northwind 샘플 데이터베이스에서는 일반적으로 고객이 주문을 하기 때문에 고객과 고객 주문 간의 관계가 항상 모델에 존재합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 이러한 관계를 나타내는 데 도움이 되도록 <xref:System.Data.Linq.Mapping.AssociationAttribute> 특성을 정의합니다. 이 특성은 데이터베이스에서의 외래 키 관계가 무엇인지 나타내기 위해 <xref:System.Data.Linq.EntitySet%601> 및 <xref:System.Data.Linq.EntityRef%601> 형식과 함께 사용됩니다. 자세한 내용은의 연결 특성 섹션을 참조 하십시오. [특성 기반 매핑](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)합니다.  
  
> [!NOTE]
>  AssociationAttribute 및 ColumnAttribute Storage 속성 값은 대/소문자를 구분합니다. 예를 들어 AssociationAttribute.Storage 속성의 특성에 사용하는 값은 코드의 다른 곳에서 사용하는 해당 속성 이름과 대/소문자가 동일해야 합니다. 이 규칙은 [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)]과 같이 일반적으로 대/소문자를 구분하지 않는 프로그래밍 언어를 포함하여 모든 .NET 프로그래밍 언어에 적용됩니다. Storage 속성에 대한 자세한 내용은 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>를 참조하세요.  
  
 이 항목의 뒷부분에 나오는 예제처럼 대부분의 관계는 일대다입니다. 다음과 같이 일대일 및 다대다 관계를 나타낼 수도 있습니다.  
  
-   일대일: 양쪽 모두에 <xref:System.Data.Linq.EntitySet%601>을 포함하여 이 종류의 관계를 나타냅니다.  
  
     예를 들어 한 `Customer` - `SecurityCode` 고객의 보안 코드는에서 찾을 수 있도록 만든 관계는 `Customer` 테이블을 권한 있는 사용자만 액세스할 수 있습니다.  
  
-   다 대 다 관계에서 링크 테이블의 기본 키에서 다 대 다: (이 라고도 함는 *접합* 테이블) 일반적으로 다른 두 테이블의 외래 키 조합으로 구성 됩니다.  
  
     예를 들어 한 `Employee` - `Project` 링크 테이블을 사용 하 여 형성 된 다 대 다 관계 `EmployeeProject`합니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 `Employee`, `Project` 및 `EmployeeProject`라는 세 개의 클래스를 사용하여 이러한 관계를 모델링해야 합니다. 이 경우 `Employee` 및 `Project` 간의 관계를 변경하려면 기본 키 `EmployeeProject`의 업데이트가 필요한 것처럼 보일 수 있습니다. 그러나 이 상황을 모델링하는 최선의 방법은 기존 `EmployeeProject`를 삭제하고 새 `EmployeeProject`를 만드는 것입니다.  
  
    > [!NOTE]
    >  관계형 데이터베이스에서 관계는 일반적으로 다른 테이블의 기본 키를 참조하는 외래 키 값으로 모델링됩니다. 간을 탐색할를 명시적으로 연결 두 테이블 관계형를 사용 하 여 *조인* 작업 합니다.  
    >   
    >  개체에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]반면 다른 속성 참조 또는 참조를 사용 하 여 탐색할 수 있는 컬렉션을 사용 하 여 서로 참조, *점* 표기법입니다.  
  
## <a name="example"></a>예  
 다음 일대다 예제에서 `Customer` 클래스는 고객과 고객의 주문 사이의 관계를 선언하는 속성을 가집니다.  `Orders` 속성은 <xref:System.Data.Linq.EntitySet%601> 형식입니다. 이 형식은 이 관계가 일대다(한 명의 고객과 여러 개의 주문)라는 것을 나타냅니다. <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> 속성은 이 속성과 비교할 관련 클래스의 속성 이름을 지정함으로써 이 연결이 이루어지는 방법을 설명하는 데 사용됩니다. 이 예제는 `CustomerID` 데이터베이스와 마찬가지로 속성이 비교 됩니다 *조인* 해당 열 값 비교 하는 것입니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 클래스 간의 연결을 만들 수 있습니다.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>예  
 또한 이 상황을 반대로 적용할 수도 있습니다. `Customer` 클래스를 사용하여 고객과 주문 간의 연결을 설명하는 대신에 `Order` 클래스를 사용할 수 있습니다. 다음 코드 예제와 같이 `Order` 클래스는 <xref:System.Data.Linq.EntityRef%601> 형식을 사용하여 고객에 대한 관계를 설명합니다.  
  
> [!NOTE]
>  <xref:System.Data.Linq.EntityRef%601> 클래스에서 지 원하는 *지연 된 로드*합니다. 자세한 내용은 *참조* [지연 된 실행과 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)합니다.  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
