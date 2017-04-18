---
title: "질문과 대답 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 질문과 대답
다음 단원에서는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]를 구현할 때 발생할 수 있는 일반적인 문제에 대한 해결 방법을 제시합니다.  
  
 다른 문제는 [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)에 설명되어 있습니다.  
  
## 연결할 수 없음  
 질문.  데이터베이스에 연결할 수 없습니다.  
  
 대답:  연결 문자열이 올바르고 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 인스턴스가 실행 중인지 확인하세요.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려면 명명된 파이프 프로토콜도 사용하도록 설정해야 합니다.  자세한 내용은 [연습을 통한 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)을 참조하세요.  
  
## 데이터베이스 변경 내용 손실  
 질문.  데이터베이스의 데이터를 변경했는데 응용 프로그램을 다시 실행했더니 변경 내용이 없어졌습니다.  
  
 대답:  <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하여 결과를 데이터베이스에 저장해야 합니다.  
  
## 데이터베이스 연결: 연결 시간  
 질문.  데이터베이스는 얼마 동안 연결된 상태로 유지됩니까?  
  
 대답:  일반적으로 연결은 쿼리 결과를 사용할 때까지 유지됩니다.  모든 결과를 처리하는 데 시간이 많이 걸릴 것으로 예상되고 결과를 캐시해도 상관 없다면 쿼리에 <xref:System.Linq.Enumerable.ToList%2A>를 적용하세요.  각 개체를 한 번만 처리하는 일반적인 시나리오에서는 `DataReader` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 모두에서 스트리밍 모델을 사용하는 것이 더 효과적입니다.  
  
 세부적인 연결 사용은 다음에 따라 달라집니다.  
  
-   연결 개체를 사용하여 <xref:System.Data.Linq.DataContext>를 만든 경우의 연결 상태  
  
-   연결 문자열 설정\(예: MARS\(Multiple Active Result Sets\) 사용\).  자세한 내용은 [MARS\(Multiple Active Result Sets\)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)를 참조하세요.  
  
## 쿼리하지 않고 업데이트  
 질문.  데이터베이스를 먼저 쿼리하지 않고 테이블 데이터를 업데이트할 수 있습니까?  
  
 대답:  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에는 설정 기반의 업데이트 명령이 없지만 다음 기술 중 하나를 사용하여 쿼리 없이 업데이트할 수 있습니다.  
  
-   <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 SQL 코드를 보냅니다.  
  
-   개체의 새 인스턴스를 만든 후 업데이트에 영향을 주는 현재 값\(필드\)을 모두 초기화합니다.  그런 다음 <xref:System.Data.Linq.DataContext>를 사용하여 개체를 <xref:System.Data.Linq.Table%601.Attach%2A>에 연결하고 변경할 필드를 수정합니다.  
  
## 예기치 않은 쿼리 결과  
 질문.  쿼리가 예기치 않은 결과를 반환합니다.  무슨 문제가 있는지 어떻게 확인합니까?  
  
 대답:  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에는 생성된 SQL 코드를 검사할 수 있는 도구가 여러 가지 있습니다.  그 중에서도 <xref:System.Data.Linq.DataContext.Log%2A>가 가장 중요합니다.  자세한 내용은 [디버깅 지원](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)을 참조하세요.  
  
## 예기치 않은 저장 프로시저 결과  
 질문.  `MAX()`를 사용하여 반환 값을 계산하는 저장 프로시저를 사용하고 있습니다.  저장 프로시저를 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 화면으로 끌어 오면 반환 값이 올바르지 않습니다.  
  
 대답:  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음과 같은 두 가지 방법으로 데이터베이스에서 생성된 값을 저장 프로시저를 통해 반환합니다.  
  
-   출력 결과에 이름을 지정하는 방법  
  
-   출력 매개 변수를 명시적으로 지정하는 방법  
  
 다음은 잘못된 출력의 예제입니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 결과를 매핑할 수 없기 때문에 항상 0을 반환합니다.  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select max(i) from t where name like 'hello'`  
  
 `end`  
  
 다음은 출력 매개 변수를 사용하여 얻은 올바른 출력의 예제입니다.  
  
 `create procedure proc2`  
  
 `@result int OUTPUT`  
  
 `as`  
  
 `select @result = MAX(i) from t where name like 'hello'`  
  
 `go`  
  
 다음은 출력 결과에 이름을 지정하여 얻은 올바른 출력의 예제입니다.  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select nax(i) AS MaxResult from t where name like 'hello'`  
  
 `end`  
  
 자세한 내용은 [저장 프로시저를 사용하여 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)을 참조하세요.  
  
## Serialization 오류  
 질문.  serialize하려고 하면 "...'System.Data.Linq.ChangeTracker\+StandardChangeTracker' 형식이 serializable로 표시되어 있지 않습니다."라는 오류 메시지가  표시됩니다.  
  
 대답:  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 코드 생성은 <xref:System.Runtime.Serialization.DataContractSerializer> serialization을 지원하지만  <xref:System.Xml.Serialization.XmlSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>는 지원하지 않습니다.  자세한 내용은 [Serialization](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)를 참조하세요.  
  
## 여러 DBML 파일  
 질문.  여러 DBML 파일에서 일부 테이블을 공유할 경우 컴파일 오류가 발생합니다.  
  
 대답:  에서 각 DBML 파일에 대해 **컨텍스트 네임스페이스** 및 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] **엔터티 네임스페이스** 속성에 고유한 값을 설정하세요.  이렇게 하면 이름\/네임스페이스 충돌이 해결됩니다.  
  
## 삽입 또는 업데이트 시 데이터베이스에서 생성된 값을 명시적으로 설정해야 하는 문제 방지  
 질문.  데이터베이스 테이블에 SQL `DateCreated`를 기본값으로 사용하는 `Getdate()` 열이 있습니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하여 새 레코드를 삽입하려고 하면 값이 `NULL`로 설정됩니다.  데이터베이스의 기본값이 설정되어야 하지 않나요?  
  
 대답:  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 ID\(자동 증분\)와 rowguidcol\(데이터베이스에서 생성된 GUID\) 및 타임스탬프 열에 대해서만 이와 같이 기본값을 적용합니다.  그 외의 경우에는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>\=`true` 및 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>\=<xref:System.Data.Linq.Mapping.AutoSync>\/<xref:System.Data.Linq.Mapping.AutoSync>\/<xref:System.Data.Linq.Mapping.AutoSync>와 같이 속성을 직접 설정해야 합니다.  
  
## 여러 DataLoadOptions  
 질문.  첫 번째 로드 옵션을 덮어쓰지 않고 다른 로드 옵션을 지정할 수 있습니까?  
  
 대답:  예.  다음 예제에서처럼 첫 번째 로드 옵션을 덮어쓰지 않습니다.  
  
```vb  
Dim dlo As New DataLoadOptions()  
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)  
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)  
```  
  
```csharp  
DataLoadOptions dlo = new DataLoadOptions();  
dlo.LoadWith<Order>(o => o.Customer);  
dlo.LoadWith<Order>(o => o.OrderDetails);  
```  
  
## SQL Compact 3.5 사용 오류  
 질문.  [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 데이터베이스에서 테이블을 끌어 오면 오류가 발생합니다.  
  
 대답:  [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 런타임과 달리 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 지원하지 않습니다.  이 경우에는 고유 엔터티 클래스를 만들어 적절한 특성을 추가해야 합니다.  
  
## 상속 관계 오류  
 질문.  [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서 도구 상자의 상속 모양을 사용하여 두 엔터티를 연결했는데 오류가 발생합니다.  
  
 대답:  관계를 만드는 것만으로는 부족합니다.  판별자 열, 기본 클래스 판별자 값 및 파생 클래스 판별자 값 등의 정보를 제공해야 합니다.  
  
## 공급자 모델  
 질문.  사용할 수 있는 공용 공급자 모델이 있습니까?  
  
 대답:  아니요, 사용할 수 있는 공용 공급자 모델은 없습니다.  현재 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 및 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)]만 지원합니다.  
  
## SQL 삽입 공격  
 질문.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL 삽입 공격으로부터 어떻게 보호됩니까?  
  
 대답:  사용자 입력을 연결하여 만든 기존 SQL 쿼리의 경우에는 SQL 삽입 공격이 상당히 큰 위협 요소였습니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 쿼리에 <xref:System.Data.SqlClient.SqlParameter>를 사용하여 이러한 삽입 공격을 방지합니다.  즉, 사용자 입력은 매개 변수 값으로 변환됩니다.  이 방법을 사용하면 사용자 입력을 통해 악의적인 명령이 사용되는 문제를 방지할 수 있습니다.  
  
## DBML 파일에서 읽기 전용 플래그 변경  
 질문.  DBML 파일에서 개체 모델을 만들 때 일부 속성의 setter를 어떻게 제거합니까?  
  
 대답:  이와 같은 고급 시나리오에서는 다음과 같은 단계를 수행하세요.  
  
1.  .dbml 파일에서 <xref:System.Data.Linq.ITable.IsReadOnly%2A> 플래그를 `True`로 변경하여 속성을 수정합니다.  
  
2.  부분 클래스를 추가합니다.  읽기 전용 멤버에 대해 매개 변수가 있는 생성자를 만듭니다.  
  
3.  기본 <xref:System.Data.Linq.Mapping.UpdateCheck> 값\(<xref:System.Data.Linq.Mapping.UpdateCheck>\)을 검토하여 응용 프로그램에 사용할 수 있는 올바른 값인지 확인합니다.  
  
    > [!CAUTION]
    >  [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용할 경우에는 변경 내용이 덮어쓰여질 수 있습니다.  
  
## APTCA  
 질문.  부분적으로 신뢰할 수 있는 코드에서 System.Data.Linq를 사용할 수 있습니까?  
  
 대답:  예, System.Data.Linq.dll 어셈블리도 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 특성이 표시된 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 어셈블리 중 하나입니다.  [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]에서 이 특성이 표시되지 않은 어셈블리는 완전히 신뢰할 수 있는 코드에서만 사용할 수 있습니다.  
  
 일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]신뢰가 보통으로 설정된 웹 응용 프로그램에서  *어셈블리에 액세스할 수 있도록 설정하여 부분적으로 신뢰할 수 있는 호출자의 어셈블리 사용을 허용합니다.*  
  
## 여러 테이블의 데이터 매핑  
 질문.  사용하는 엔터티의 데이터를 여러 테이블에서 가져오는데  이러한 데이터를 어떻게 매핑합니까?  
  
 대답:  데이터베이스에 뷰를 만들어 엔터티를 해당 뷰에 매핑할 수 있습니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 테이블과 마찬가지로 뷰에 대해서도 동일한 SQL을 생성합니다.  
  
> [!NOTE]
>  그러나 이 시나리오에서는 뷰 사용이 제한됩니다.  이 방법은 기본 뷰에서 <xref:System.Data.Linq.Table%601>에 대해 수행되는 작업을 지원하는 경우에 가장 안전하게 사용할 수 있습니다.  수행하려는 작업은 사용자 자신만이 알고 있습니다.  예를 들어 대부분의 응용 프로그램은 읽기 전용이고 다른 많은 수의 응용 프로그램은 뷰에 대해 저장 프로시저를 사용하는 방법으로만 `Create`\/`Update`\/`Delete` 작업을 수행합니다.  
  
## 연결 풀링  
 질문.  <xref:System.Data.Linq.DataContext> 풀링에 도움이 되는 생성자가 있습니까?  
  
 대답:  <xref:System.Data.Linq.DataContext>의 인스턴스는 다시 사용하지 마세요.  각 <xref:System.Data.Linq.DataContext>는 하나의 특정 편집\/쿼리 세션에 대한 상태\(ID 캐시 포함\)를 유지합니다.  데이터베이스의 현재 상태를 기반으로 새 인스턴스를 사용하려면 새 <xref:System.Data.Linq.DataContext>를 사용하세요.  
  
 기본 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 연결 풀링은 사용할 수 있습니다.  자세한 내용은 [SQL Server 연결 풀링\(ADO.NET\)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)을 참조하세요.  
  
## 두 번째 DataContext가 업데이트되지 않음  
 질문.  <xref:System.Data.Linq.DataContext>의 인스턴스 하나를 사용하여 데이터베이스에 값을 저장했습니다.  그런데 동일한 데이터베이스에 대한 두 번째 <xref:System.Data.Linq.DataContext>에 업데이트된 값이 반영되지 않습니다.  두 번째 <xref:System.Data.Linq.DataContext> 인스턴스가 캐시된 값을 반환하는 것 같습니다.  
  
 대답:  이 동작은 설계 시 의도된 것입니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 첫 번째 인스턴스와 동일한 인스턴스\/값을 계속해서 반환합니다.  데이터를 업데이트할 경우에는 낙관적 동시성을 사용합니다.  이 경우 현재 데이터베이스 상태를 원래 데이터와 비교하여 데이터가 변경되지 않았는지 확인합니다.  데이터가 변경된 경우 충돌이 발생하고 응용 프로그램에서는 이 문제를 해결해야 합니다.  응용 프로그램에서는 한 가지 옵션으로 원래 상태를 현재 데이터베이스 상태로 다시 설정한 후 업데이트를 다시 시도합니다.  자세한 내용은 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)를 참조하세요.  
  
 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 false로 설정하여 캐싱 및 변경 추적을 해제할 수도 있습니다.  이렇게 하면 쿼리할 때마다 최신 값을 검색할 수 있습니다.  
  
## 읽기 전용 모드에서 SubmitChanges를 호출할 수 없음  
 질문.  읽기 전용 모드에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하려고 하면 오류가 발생합니다.  
  
 대답:  읽기 전용 모드에서는 컨텍스트에서 변경 내용을 추적하지 않습니다.  
  
## 참고 항목  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)   
 [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)   
 [LINQ to SQL의 보안](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)