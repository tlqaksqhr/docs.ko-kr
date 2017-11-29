---
title: "연습: 형식 공급자를 사용하여 SQL Database에 액세스(F#)"
description: "F # 3.0에서 SqlDataConnection (LINQ to SQL) 형식 공급자를 사용 하 여 라이브 데이터베이스에 연결 하는 경우 SQL 데이터베이스에 대 한 형식을 생성 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>연습: 형식 공급자를 사용하여 SQL Database에 액세스

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 연습에서는 데이터베이스에 라이브 연결을 사용 하는 경우 SQL 데이터베이스에서 데이터에 대 한 형식을 생성 하려면 F # 3.0에서 사용할 수 있는 SqlDataConnection (LINQ to SQL) 형식 공급자를 사용 하는 방법을 설명 합니다. 참조 데이터베이스에 라이브 연결 되어 있지 않으면 LINQ to SQL 스키마 파일 (DBML 파일) 권한이 표시 되지만 [연습: DBML 파일에서 생성 F # 형식](generating-fsharp-types-from-dbml.md)합니다.

이 연습에서는 다음 작업을 수행합니다. 이 연습을 완료 하려면이 순서 대로 이러한 작업을 수행 해야 합니다.


- 테스트 데이터베이스를 준비합니다.

- 프로젝트 만들기

- 형식 공급자를 설정합니다.

- 데이터 쿼리

- Nullable 필드 작업

- 저장 프로시저 호출

- 데이터베이스 업데이트

- Transact SQL 코드를 실행합니다.

- 전체 데이터 컨텍스트를 사용 하 여

- 데이터 삭제

- 필요에 따라 테스트 데이터베이스를 만듭니다

## <a name="preparing-a-test-database"></a>테스트 데이터베이스를 준비합니다.
SQL Server를 실행 하는 서버에서 테스트 목적으로 데이터베이스를 만듭니다. 데이터베이스를 사용할 수 섹션에서이 페이지의 맨 아래에 스크립트를 만들 [테스트 데이터베이스를 만드는](#creating-a-test-database) 에이 작업을 수행 합니다.


#### <a name="to-prepare-a-test-database"></a>테스트 데이터베이스를 준비 하려면

MyDatabase 작성 스크립트를 실행 하려면 열고는 **보기** 메뉴를 선택한 후 **SQL Server 개체 탐색기** 하거나 선택 하 고 Ctrl +\, Ctrl + S 키. **SQL Server 개체 탐색기** 창에서 적절 한 인스턴스에 대 한 바로 가기 메뉴를 열고, 선택 **새 쿼리**이 페이지의 맨 아래에 스크립트를 복사 하 고 다음 스크립트를 편집기에 붙여 넣습니다. SQL 스크립트를 실행 하려면 삼각형 기호로 도구 모음 아이콘을 선택 하거나 Ctrl + Q 키를 선택 합니다. 에 대 한 자세한 내용은 **SQL Server 개체 탐색기**, 참조 [연결 된 데이터베이스 개발](https://msdn.microsoft.com/library/hh272679(VS.103).aspx)합니다.


## <a name="creating-the-project"></a>프로젝트 만들기
다음으로, F # 응용 프로그램 프로젝트를 만듭니다.


#### <a name="to-create-and-set-up-the-project"></a>프로젝트를 만들고 설정하려면

1. F # 응용 프로그램 프로젝트를 새로 만듭니다.

2. 에 대 한 참조를 추가 [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3),으로 `System.Data`, 및 `System.Data.Linq`합니다.

3. F # 코드 파일 Program.fs의 맨 위에 다음 코드 줄을 추가 하 여 적절 한 네임 스페이스를 엽니다.

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. 대부분의 F # 프로그램와 마찬가지로 컴파일된 프로그램으로이 연습에서 코드를 실행할 수 있습니다 또는 스크립트로 대화형으로 실행할 수 있습니다. 스크립트를 사용 하는 것을 선호 하는 경우 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **새 항목 추가**, F # 스크립트 파일을 추가 하 고 각 단계에는 스크립트에 코드를 추가 합니다. 어셈블리 참조를 로드할 파일 맨 위에 있는 다음 줄을 추가 해야 합니다.

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  그런 다음 추가 하 고 F # Interactive에서 실행 하려면 Alt + Enter를 눌러 코드의 각 블록을 선택할 수 있습니다.

## <a name="setting-up-a-type-provider"></a>형식 공급자를 설정합니다.
이 단계에서는 데이터베이스 스키마에 대 한 형식 공급자를 만듭니다.


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>데이터베이스를 직접 연결에서 형식 공급자를 설정 하려면

형식 공급자를 사용 하 여 SQL 데이터베이스를 쿼리 하는 데 사용할 수 있는 형식을 만드는 데 필요한 코드의 두 가지 중요 한 줄 있습니다. 첫째, 형식 공급자를 인스턴스화할 수 있습니다. 이렇게 하려면 형식 약어에 대 한 모양을 만들는 `SqlDataConnection` 정적 제네릭 매개 변수를 사용 합니다. `SqlDataConnection`SQL 형식 공급자는 및와 혼동 해서는 안 `SqlConnection` 즉 입력 ADO.NET 프로그래밍에서 사용 합니다. 형식 공급자를 호출할 수,에 연결 하려는 데이터베이스 있고 연결 문자열을 사용할 경우 다음 코드를 사용 합니다. 제공 된 예에서는 문자열에 대 한 사용자 지정 연결 문자열을 대체 합니다. 예를 들어 MYSERVER 및 데이터베이스 인스턴스는 인스턴스, 데이터베이스 이름, MyDatabase 이며 데이터베이스를 선택한 연결 문자열에 액세스 하려면 Windows 인증을 사용 하려면 서버도 되는 경우 다음 예제 코드에 제공 합니다.

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

이제는 형식 `dbSchema`, 데이터베이스 테이블을 표시 하는 모든 생성 된 형식을 포함 하는 부모 형식인 합니다. 갖게 되는 개체로, `db`, 데이터베이스의 모든 테이블의 구성원으로가 있습니다. 테이블 이름 속성에는 이러한 속성의 형식이 F # 컴파일러에 의해 발생 합니다. 형식 자체에서 중첩 된 형식으로 표시 `dbSchema.ServiceTypes`합니다. 따라서 이러한 테이블의 행에 대해 검색 된 모든 데이터는 해당 테이블에 대해 생성 된 적절 한 형식의 인스턴스입니다. 형식의 이름은 `ServiceTypes.Table1`합니다.

F # 언어 SQL 쿼리로 쿼리를 해석 하는 방법을 익히는 감사를 설정 하는 줄 검토는 `Log` 데이터 컨텍스트 속성입니다.

형식 공급자에서 만든 형식을 탐색 하려면 다음 코드를 추가 합니다.

```fsharp
let table1 = db.Table1
```

위로 마우스를 가져가고 `table1` 해당 형식을 볼 수 있습니다. 해당 형식이 `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` 과 같습니다. 제네릭 인수 각 행의 유형이 생성 된 형식 인지 `dbSchema.ServiceTypes.Table1`합니다. 컴파일러는 데이터베이스의 각 테이블에 대해 비슷한 종류를 만듭니다.

## <a name="querying-the-data"></a>데이터 쿼리
이 단계에서는 F # 쿼리 식을 사용 하 여 쿼리를 작성 합니다.


#### <a name="to-query-the-data"></a>데이터를 쿼리하려면

1. 이제 데이터베이스에서 해당 테이블에 대 한 쿼리를 만듭니다. 다음 코드를 추가 합니다.

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  단어의 모양을 `query` 비슷한 쿼리 결과를 일반적인 데이터베이스에 변수의 컬렉션을 생성 하는 계산 식의 형식을 쿼리 식 임을 나타냅니다. 쿼리를 가리키면 나타납니다의 인스턴스이면 [Linq.QueryBuilder 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), 쿼리 계산 식 정의 하는 형식입니다. 위로 가져가면 `query1`의 인스턴스이면 나타납니다 `System.Linq.IQueryable`합니다. 이름에서 알 수 있듯이 `System.Linq.IQueryable` 쿼리의 결과인 쿼리할 수 있는 데이터를 나타냅니다. 쿼리 지연 평가 데이터베이스가을 의미 하는 쿼리가 평가 되는 경우 쿼리 될 수 있습니다. 통해 쿼리를 전달 하는 마지막 줄 `Seq.iter`합니다. 쿼리는 열거 가능 하며 시퀀스와 같은 반복 될 수 있습니다. 자세한 내용은 참조 [쿼리 식](../../language-reference/query-expressions.md)합니다.

2. 이제 쿼리에 쿼리 연산자를 추가 합니다. 더 복잡 한 쿼리를 구성 하는 데 사용할 수 있는 사용 가능한 쿼리 연산자의 여러 가지가 있습니다. 또한이 예제에는 쿼리 변수를 제거 하 고 파이프라인 연산자를 대신 사용할 수 있는 보여 줍니다.

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. 두 테이블의 조인으로 더 복잡 한 쿼리를 추가 합니다.

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. 실제 코드에 쿼리에 매개 변수는 일반적으로 값 또는 변수, 하지 컴파일 시간 상수입니다. 매개 변수를 사용 하 고 다음 값 10 해당 함수를 호출 하는 함수에는 쿼리를 래핑하는 다음 코드를 추가 합니다.

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>Nullable 필드 작업
데이터베이스에서 필드 종종 null 값을 허용 합니다. .NET 형식 시스템에서 null을 허용 하는 형식에 없기 때문에 가능한 값으로 null 데이터에 대 한 일반 숫자 데이터 형식과 사용할 수 없습니다. 따라서 이러한 값의 인스턴스로 표현 된 `System.Nullable` 유형입니다. 필드의 이름으로 직접 이러한 필드의 값에 액세스 하는 대신 추가 단계를 추가 해야 합니다. 사용할 수는 `System.Nullable.Value` nullable 형식의 기본 값에 액세스 하는 속성입니다. `System.Nullable.Value` 속성 개체가 값 대신 null 인 경우 예외를 throw 합니다. 사용할 수는 `System.Nullable.HasValue` 부울 메서드는 값이 존재 하는지 확인 하거나 사용 하 여를 `System.Nullable.GetValueOrDefault()` 모든 경우에에서는 실제 값을 갖도록 합니다. 사용 하는 경우 `System.Nullable.GetValueOrDefault()` 데이터베이스에는 null이 고 다음 대체 될 정수 계열 형식의 0 또는 0.0 부동 소수점 형식 문자열 형식에 대 한 빈 문자열 같은 값을 사용 합니다.

Null 허용 값에 대해 같음 테스트 또는 비교를 수행 해야 하는 경우는 `where` 쿼리에서 절에 null 허용 연산자를 사용할 수 있습니다는 [Linq.NullableOperators 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)합니다. 일반 비교 연산자 처럼 이들은 `=`, `>`, `<=`등의 물음표가 나타납니다 연산자의 오른쪽 또는 왼쪽에 null을 허용 하는 값이 제외 하 고 있습니다. 예를 들어 연산자 `>?` 는 큰-연산자 오른쪽의 값이 null을 허용 합니다. 이러한 연산자는 작동 방식은 식의 어느 쪽이 null 이면 식으로 평가 되었음이 `false`합니다. 에 `where` 절, 일반적으로 의미는 null 필드가 포함 된 행을 선택 하지 않으며 쿼리 결과에 반환 되지 않습니다.


#### <a name="to-work-with-nullable-fields"></a>Nullable 필드를 작성 하려면

다음 코드와 작업에 null 허용 값이 있습니다. 가정 **TestData1** null을 허용 하는 정수 필드입니다.

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a>저장 프로시저 호출
F #에서 데이터베이스의 모든 저장된 프로시저를 호출할 수 있습니다. Static 매개 변수를 설정 해야 `StoredProcedures` 를 `true` 의 형식 공급자 인스턴스화에서 합니다. 형식 공급자 `SqlDataConnection` 생성 되는 형식을 구성 하는 데 사용할 수 있는 몇 가지 정적 메서드를 포함 합니다. 이러한 대 한 전체 설명은 참조 하세요. [SqlDataConnection 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)합니다. 데이터 컨텍스트 형식에 대해 메서드를 각 저장된 프로시저에 대해 생성 됩니다.


#### <a name="to-call-a-stored-procedure"></a>저장 프로시저를 호출하려면

적절 한 전달 해야 하는 경우는 null을 허용 하는 매개 변수를 사용 하는 저장된 프로시저, `System.Nullable` 값입니다. 스칼라 또는 테이블을 반환 하는 저장된 프로시저 메서드의 반환 값은 `System.Data.Linq.ISingleResult`, 반환 된 데이터에 액세스할 수 있도록 하는 속성을 포함 하 합니다. 에 대 한 형식 인수 `System.Data.Linq.ISingleResult` 특정 절차에 따라 달라 지 며 형식 공급자가 생성 된 형식 중 하나 이기도 합니다. 라는 이름의 저장된 프로시저에 대 한 `Procedure1`, 형식이 `Procedure1Result`합니다. 형식 `Procedure1Result` 이름이 포함 된 열에서 반환 된 테이블 또는 스칼라 값을 반환 하는 저장된 프로시저에 대 한 반환 값을 나타내는 것입니다.

다음 코드는 프로시저 라고 가정 `Procedure1` 에서는 두 개의 nullable 정수 매개 변수로 데이터베이스 라는 열을 반환 하는 쿼리 실행 `TestData1`, 정수를 반환 합니다.

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>데이터베이스 업데이트
LINQ DataContext 형식을 보다 쉽게에 완벽 하 게 형식화 된 적절 하 게 생성된 된 형식으로의 트랜잭션된 데이터베이스 업데이트를 수행할 수 있도록 하는 메서드가 포함 되어 있습니다.


#### <a name="to-update-the-database"></a>데이터베이스를 업데이트하려면

1. 다음 코드에서는 행이 여러 데이터베이스에 추가 됩니다. 행만 추가 하는 경우 사용할 수 있습니다 `System.Data.Linq.Table.InsertOnSubmit()` 새 행을 추가 지정할 수 있습니다. 여러 행을 삽입 하는 경우 호출 및 컬렉션에 저장 해야 `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`합니다. 이러한 방법 중 하나를 호출 하는 경우 데이터베이스 즉시 변경 되지 않습니다. 호출 해야 `System.Data.Linq.DataContext.SubmitChanges` 실제로 변경 내용을 커밋 하도록 합니다. 기본적으로 호출 하기 전에 수행 하는 모든 `System.Data.Linq.DataContext.SubmitChanges` 는 암시적으로 동일한 트랜잭션의 일부입니다.

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. 이제는 삭제 작업을 호출 하 여 행을 정리 합니다.

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>Transact SQL 코드를 실행합니다.
TRANSACT-SQL를 사용 하 여 직접 지정할 수도 있습니다는 `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` 에서 메서드는 `DataContext` 클래스입니다.


#### <a name="to-execute-custom-sql-commands"></a>사용자 지정 SQL 명령을 실행 하려면

다음 코드를 테이블에 레코드를 삽입 하 고 테이블에서 레코드를 삭제 하는 SQL 명령을 보내는 방법을 보여 줍니다.

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>전체 데이터 컨텍스트를 사용 하 여
앞의 예에서 `GetDataContext` 메서드를 섞어 가져오는 데는 *단순화 된 데이터 컨텍스트* 데이터베이스 스키마에 대 한 합니다. 단순화 된 데이터 컨텍스트는 보다 쉽게 사용할 수 있는 많은 멤버 되지 않으므로 쿼리를 생성 하는 경우 사용할 수 있습니다. 따라서 IntelliSense에 속성을 검색할 때 테이블 및 저장된 프로시저와 같은 데이터베이스 구조에 집중할 수 있습니다. 그러나 단순화 된 데이터 컨텍스트를 수행할 수 있는 작업에 대 한 제한이 있습니다. 다른 작업을 수행 하는 기능을 제공 하는 전체 데이터 컨텍스트. 도 사용할 수 있는 64 \는 `ServiceTypes` 의 이름이 고는 *DataContext* 제공 하면 static 매개 변수입니다. 제공 하지 않은 경우 SqlMetal.exe 다른 입력을 기반으로 데이터 컨텍스트 형식 이름이 생성 됩니다. 상속 되는 전체 데이터 컨텍스트 `System.Data.Linq.DataContext` 와 같은 ADO.NET 데이터 형식에 대 한 참조를 포함 하는 기본 클래스의 멤버를 노출 하 고는 `Connection` 개체와 같은 메서드 `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` 및 `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` sql에서 쿼리를 작성 하는 데 사용할 수 있는 고도 명시적으로 트랜잭션을 사용 하는 수단입니다.


#### <a name="to-use-the-full-data-context"></a>전체 데이터 컨텍스트를 사용 하려면

다음 코드 전체 데이터 컨텍스트 개체를 가져오고 사용 하 여 데이터베이스에 직접 명령을 실행 하는 방법을 보여 줍니다. 이 경우 두 명령은 동일한 트랜잭션의 일부로 실행 됩니다.

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>데이터 삭제
이 단계에서는 데이터 테이블에서 행을 삭제 하는 방법을 보여 줍니다.


#### <a name="to-delete-rows-from-the-database"></a>데이터베이스에서 행을 삭제 하려면

이제 모든 정리 인스턴스의 지정된 된 테이블에서 행을 삭제 하는 함수를 작성 하 여 행 추가 `System.Data.Linq.Table` 클래스입니다. 그런 다음, 삭제 하려면 모든 행을 찾는 쿼리를 작성 하 고에 쿼리의 결과 `deleteRows` 함수입니다. 이 코드에서는 제공 함수 인수를 부분 적용 하는 기능을 활용 합니다.

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>테스트 데이터베이스를 만드는 중
이 절이이 연습에서는 테스트 데이터베이스를 설정 하는 방법을 보여 줍니다.

참고 어떤 식으로든에서 데이터베이스를 변경 하는 경우 형식 공급자를 다시 설정 해야 합니다. 형식 공급자를 다시 설정 하려면 빌드하거나 형식 공급자를 포함 하는 프로젝트를 정리 합니다.


#### <a name="to-create-the-test-database"></a>테스트 데이터베이스를 만들려면

1. **서버 탐색기**에 대 한 바로 가기 메뉴를 열고는 **데이터 연결** 노드를 선택 하 고 **연결 추가**합니다. **연결 추가** 대화 상자가 나타납니다.

2. 에 **서버 이름** 상자에 관리 권한이 있는 SQL Server 인스턴스의 이름을 지정 하거나 서버에 액세스할 수 없는 경우 (localdb\v11.0)을 지정 합니다. SQL Express LocalDB는 컴퓨터에서 개발 및 테스트에 대 한 간단한 데이터베이스 서버를 제공 합니다. 새 노드가 만들어집니다 **서버 탐색기** 아래 **데이터 연결**합니다. LocalDB에 대 한 자세한 내용은 참조 [연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](https://msdn.microsoft.com/library/ms233763.aspx)합니다.

3. 새 연결 노드의 바로 가기 메뉴를 열고 선택 **새 쿼리**합니다.

4. 다음 SQL 스크립트를 복사, 쿼리 편집기에 붙여 넣고 다음 선택에서 **Execute** 도구 모음 단추 또는 Ctrl + Shift + E 키를 선택 합니다.

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>참고 항목
[형식 공급자](index.md)

[SqlDataConnection 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[연습: DBML 파일에서 F # 형식 생성](generating-fsharp-types-from-dbml.md)

[쿼리 식](../../language-reference/query-expressions.md)

[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)

[SqlMetal.exe &#40; 코드 생성 도구 &#41;](https://msdn.microsoft.com/library/bb386987)
