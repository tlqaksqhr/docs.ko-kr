---
title: '연습: 관계 간 쿼리(C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: a438b0ae83a223abfc35643915e6eedd5be068a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364420"
---
# <a name="walkthrough-querying-across-relationships-c"></a>연습: 관계 간 쿼리(C#)
이 연습에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *연결* 데이터베이스에서 외래 키 관계를 나타내는입니다.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 완료 해야 [연습: 간단한 개체 모델 및 쿼리 (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)합니다. 이 연습은 c:\linqtest5에 있는 northwnd.mdf 파일을 비롯하여 해당 개체 모델 및 쿼리를 기반으로 합니다.  
  
## <a name="overview"></a>개요  
 이 연습은 다음과 같은 세 가지 주요 작업으로 구성됩니다.  
  
-   Northwind 샘플 데이터베이스의 Orders 테이블을 나타내는 엔터티 클래스 추가  
  
-   `Customer` 및 `Customer` 클래스 간의 관계를 향상시키기 위해 `Order` 클래스에 주석 추가  
  
-   `Order` 클래스를 사용하여 `Customer` 정보 가져오기를 테스트하는 쿼리 만들기 및 실행  
  
## <a name="mapping-relationships-across-tables"></a>테이블 간 관계 매핑  
 `Customer` 클래스 정의 후에 `Order`가 외래 키로 `Order.Customer`에 관련된다는 것을 나타내는 다음 코드가 포함된 `Customer.CustomerID` 엔터티 클래스 정의를 만듭니다.  
  
#### <a name="to-add-the-order-entity-class"></a>Order 엔터티 클래스를 추가하려면  
  
-   `Customer` 클래스 뒤에 다음 코드를 입력하거나 붙여넣습니다.  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a>Customer 클래스에 주석 지정  
 이 단계에서는 `Customer` 클래스에 대한 관계를 나타내기 위해 `Order` 클래스에 주석을 지정합니다. 어느 방향으로든 관계를 정의하여 링크를 충분히 만들 수 있으므로 이 추가 작업이 반드시 필요한 것은 아닙니다. 그러나 이 주석을 추가하면 어느 방향으로나 개체를 쉽게 탐색할 수 있습니다.  
  
#### <a name="to-annotate-the-customer-class"></a>Customer 클래스에 주석을 지정하려면  
  
-   `Customer` 클래스에 다음 코드를 입력하거나 붙여넣습니다.  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Customer 및 Order 관계에서 쿼리 만들기 및 실행  
 이제 `Order` 개체에서 `Customer` 개체를 직접 액세스하거나 그 반대 방향으로 액세스할 수 있습니다. 명시적 필요가 *조인* customers와 orders 합니다.  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a>Customer 개체를 사용하여 Order 개체에 액세스하려면  
  
1.  다음 코드를 `Main` 메서드에 입력하거나 붙여넣어 이 메서드를 수정합니다.  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2.  F5 키를 눌러 응용 프로그램을 디버깅합니다.  
  
    > [!NOTE]
    >  `db.Log = Console.Out;`을 주석으로 처리하여 콘솔 창에서 SQL 코드를 제거할 수 있습니다.  
  
3.  콘솔 창에서 Enter 키를 눌러 디버깅을 중지합니다.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>강력한 형식의 데이터베이스 뷰 만들기  
 강력한 형식의 데이터베이스 뷰로 작업을 시작하는 것이 훨씬 더 쉽습니다. <xref:System.Data.Linq.DataContext> 개체를 강력한 형식으로 설정하면 <xref:System.Data.Linq.DataContext.GetTable%2A> 호출이 필요하지 않습니다. 강력한 형식의 <xref:System.Data.Linq.DataContext> 개체를 사용할 경우 모든 쿼리에서 강력한 형식의 테이블을 사용할 수 있습니다.  
  
 다음 단계에서는 `Customers`를 데이터베이스의 Customers 테이블에 매핑되는 강력한 형식의 테이블로 만듭니다.  
  
#### <a name="to-strongly-type-the-datacontext-object"></a>DataContext 개체를 강력한 형식으로 설정하려면  
  
1.  `Customer` 클래스 선언 위에 다음 코드를 추가합니다.  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2.  다음과 같이 강력한 형식의 `Main`를 사용하도록 <xref:System.Data.Linq.DataContext> 메서드를 수정합니다.  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3.  F5 키를 눌러 응용 프로그램을 디버깅합니다.  
  
     콘솔 창 출력은 다음과 같습니다.  
  
     `ID=WHITC`  
  
4.  콘솔 창에서 Enter 키를 눌러 디버깅을 중지합니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음 연습 ([연습: 데이터 조작 (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) 데이터를 조작 하는 방법을 보여 줍니다. 다음 연습에서는 이미 완료한 이 시리즈의 연습 두 개를 저장할 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
