---
title: "연습: 형식 공급자를 사용하여 OData 서비스에 액세스(F#)"
description: "F # 3.0의 F # ODataService 형식 공급자를 사용 하 여 OData 서비스에 대 한 클라이언트 형식을 생성 하는 방법을 알아보고 쿼리 하는 데이터 서비스를 제공 하는 피드를 제공 합니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 750407c36a989cece30c0c0654ff905c8eee3b33
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>연습: 형식 공급자를 사용하여 OData 서비스에 액세스

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](https://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

개방형 데이터 프로토콜 의미 OData는 인터넷을 통해 데이터를 전송 하기 위한 프로토콜입니다. 많은 데이터 공급자는 OData 웹 서비스를 게시 하 여 자신의 데이터에 대 한 액세스를 제공 합니다. F # 3.0의 데이터 형식을 사용 하 여 자동으로 생성 되는 모든 OData 원본에서 데이터에 액세스할 수는 `ODataService` 형식 공급자입니다. OData에 대 한 자세한 내용은 https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62를 참조 합니다.

이 연습에서는 OData 서비스에 대 한 클라이언트 형식을 생성 하는 F # ODataService 형식 공급자를 사용 하는 방법을 보여 줍니다. 및 쿼리 하는 데이터 서비스를 제공 하는 피드를 제공 합니다.

이 연습에서는 다음 작업을 설명하는데, 연습을 성공적으로 수행하려면 이 순서대로 작업을 수행해야 합니다.


- OData 서비스에 대 한 클라이언트 프로젝트 구성
<br />

- OData 형식 액세스
<br />

- OData 서비스 쿼리
<br />

- OData 요청 확인
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>OData 서비스에 대 한 클라이언트 프로젝트 구성
이 단계에서는 OData 형식 공급자를 사용 하도록 프로젝트를 설정 하면 됩니다.


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>OData 서비스에 대 한 클라이언트 프로젝트를 구성 하려면

- F # 콘솔 응용 프로그램 프로젝트를 연 다음에 대 한 참조를 추가 `System.Data.Services.Client` 프레임 워크 어셈블리입니다.
<br />

- 아래 `Extensions`에 대 한 참조 추가 `FSharp.Data.TypeProviders` 어셈블리입니다.
<br />

## <a name="accessing-odata-types"></a>OData 형식 액세스
이 단계에서는 OData 서비스에 대 한 유형 및 데이터에 대 한 액세스를 제공 하는 형식 공급자를 만듭니다.


#### <a name="to-access-odata-types"></a>OData 형식에 액세스 하려면

- 코드 편집기에서 F # 소스 파일을 열고 다음 코드를 입력 합니다.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"https://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

이 예제에서는 F # 형식 공급자를 호출에 있고 지정 된 OData URI를 기반으로 하는 형식의 집합을 만드는 것을 지시 합니다. 사용할 수 있는 두 개의 개체에서 데이터에 대 한 정보를 포함 하는 하나는 간단한 데이터 컨텍스트 `db` 예제에서입니다. 이 개체는 데이터 형식만 데이터베이스와 연결 된 테이블 또는 피드에 대 한 형식을 포함 하는 포함 되어 있습니다. 다른 개체 `fullContext` 이 예제에서는의 인스턴스가 `System.Data.Linq.DataContext` 많은 추가 속성, 메서드 및 이벤트를 포함 합니다.
<br />


## <a name="querying-an-odata-service"></a>OData 서비스 쿼리
이 단계에서는 F # 쿼리 식을 사용 하 여 OData 서비스를 쿼리.


#### <a name="to-query-an-odata-service"></a>OData 서비스를 쿼리할 수

1. 형식 공급자를 설정한 했으므로 OData 서비스를 쿼리할 수 있습니다.
<br />  OData는 사용 가능한 쿼리 작업의 하위 집합만을 지원합니다. 다음 작업 및 해당 하는 키워드가 지원 됩니다.
<br />
  - 프로젝션 (`select`)
<br />

  - 필터링 (`where`문자열을 사용 하 여 여을 작업 날짜)
<br />

  - 페이징 (`skip`, `take`)
<br />

  - 순서 지정 (`orderBy`, `thenBy`)
<br />

  - `AddQueryOption` 및 `Expand`, 하는 OData 전용 작업
<br />

  자세한 내용은 참조 [LINQ 고려 사항 &#40; WCF Data Services &#41; ](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  모든 피드 또는 테이블에 항목을 하려는 경우 다음 코드 에서처럼 쿼리 식의 가장 간단한 형태를 사용 합니다.
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. 필드 또는 select 키워드 다음 튜플을 사용 하 여 원하는 열을 지정 합니다.
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. 조건을 사용 하 여 지정 된 `where` 절.
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. 쿼리 하는 부분 문자열 조건을 사용 하 여 지정 된 `System.String.Contains(System.String)` 메서드. 다음 쿼리는 이름에 "Chef"를 포함 하는 모든 제품을 반환 합니다. 또한 사용 하는 것을 볼 `System.Nullable<'T>.GetValueOrDefault()`합니다. `UnitPrice` 는 null 허용 값, 사용 하 여 값을 가져올 하거나 해야는 `Value` 속성 또는 있습니다 호출 해야 `System.Nullable<'T>.GetValueOrDefault()`합니다.
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. 사용 하 여는 `System.String.EndsWith(System.String)` 문자열이 특정 하위 문자열로 끝나는지를 지정 하는 메서드.
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. where 조건을 결합 사용 하 여 절은 `&&` 연산자입니다.
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

연산자 `?>` 및 `?<` null 허용 연산자 됩니다. Null 허용 같음 및 비교 연산자의 전체 집합을 사용할 수 있습니다. 자세한 내용은 참조 [Linq.NullableOperators 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)합니다.
<br />

7. 사용 하 여는 `sortBy` 순서를 지정 하는 연산자를 쿼리하고 사용할 `thenBy` 다른 수준의 순서를 지정할 수 있습니다. 쿼리의 select 부분에 있는 튜플의 사용을 확인할 수 있습니다. 따라서 쿼리 요소 형식을 자기 튜플을입니다.
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. Skip 연산자를 사용 하 여 지정 된 레코드 수를 무시 하 고 take 연산자를 사용 하 여 반환할 레코드 수를 지정 합니다. 이러한 방식으로 데이터 피드에서 페이징을 구현할 수 있습니다.
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>OData 요청 확인
모든 OData 쿼리는 특정 OData 요청 URI로 변환 됩니다. URI, 아마도 디버깅용으로 이벤트 처리기를 추가 하 여 확인할 수 있습니다는 `SendingRequest` 전체 데이터 컨텍스트 개체의 이벤트입니다.


#### <a name="to-verify-the-odata-request"></a>OData 요청을 확인 하려면

- OData 요청 URI를 확인 하려면 다음 코드를 사용 합니다.
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

이전 코드의 출력은입니다.
<br />`requesting https://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>참고 항목
[쿼리 식](../../language-reference/query-expressions.md)

[LINQ 고려 사항 (WCF Data Services)](https://msdn.microsoft.com/library/ee622463.aspx)

[ODataService 형식 공급자 (F #)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
