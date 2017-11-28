---
title: "연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스(F#)"
description: "F # 3.0의 ADO.NET 엔터티 데이터 모델에 따라 SQL 데이터베이스에 대 한 형식화 된 데이터에 액세스 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 770d405921758eeb7e8d7ea98b95c29c99631475
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

F# 3.0에 대한 이 연습에서는 ADO.NET 엔터티 데이터 모델을 기반으로 SQL 데이터베이스에 대해 형식화된 데이터에 액세스하는 방법을 보여줍니다. 이 연습에서는 SQL 데이터베이스와 함께 사용할 F# `SqlEntityConnection` 형식 공급자를 설정하는 방법, 데이터에 대해 쿼리를 작성하는 방법, 데이터베이스에서 저장 프로시저를 호출하는 방법, ADO.NET Entity Framework 형식 및 메서드 중 일부를 사용하여 데이터베이스를 업데이트하는 방법을 보여줍니다.

이 연습에서는 다음 작업을 설명하는데, 연습을 성공적으로 수행하려면 이 순서대로 작업을 수행해야 합니다.


- School 데이터베이스를 만듭니다.
<br />

- F# 프로젝트를 만들고 구성합니다.
<br />

- 형식 공급자를 구성 하 고 엔터티 데이터 모델에 연결
<br />

- 데이터베이스 쿼리
<br />

- 데이터베이스 업데이트
<br />


## <a name="prerequisites"></a>필수 구성 요소
이러한 단계를 완료하려면 데이터베이스를 만들 수 있는 SQL Server를 실행하는 서버에 액세스할 수 있어야 합니다.

## <a name="create-the-school-database"></a>School 데이터베이스를 만듭니다.
관리자 액세스 권한을 가진 SQL Server를 실행하는 서버에 School 데이터베이스를 만들거나 LocalDB를 사용할 수 있습니다.


#### <a name="to-create-the-school-database"></a>School 데이터베이스 만들려면

1. **서버 탐색기**에 대 한 바로 가기 메뉴를 열고는 **데이터 연결** 노드를 선택한 후 **연결 추가**합니다.
<br />  **연결 추가** 대화 상자가 나타납니다.
<br />

2. 에 **서버 이름** 상자를 관리 액세스 권한이 있는 SQL Server 인스턴스의 이름을 지정 하거나 서버에 액세스할 수 없는 경우 (localdb\v11.0)을 지정 합니다.
<br />  SQL Server Express LocalDB는 사용자 컴퓨터에서 개발 및 테스트를 위한 간단한 데이터베이스 서버를 제공합니다. LocalDB에 대 한 자세한 내용은 참조 [연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](https://msdn.microsoft.com/library/ms233763.aspx)합니다.
<br />  새 노드가 만들어집니다 **서버 탐색기** 아래 **데이터 연결**합니다.
<br />

3. 새 연결 노드의 바로 가기 메뉴를 연 다음 선택 **새 쿼리**합니다.
<br />

4. 열기 [School 샘플 데이터베이스 만들기](http://go.microsoft.com/fwlink/?LinkID=237278) Microsoft 웹 사이트 및 다음 복사 및 붙여넣기에서 데이터베이스 스크립트를 만드는 학생 데이터베이스 편집기 창에 있습니다.
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>F# 프로젝트를 만들고 구성합니다.
이 단계에서 형식 공급자를 사용하려면 프로젝트를 만들고 설정합니다.


#### <a name="to-create-and-configure-an-f-project"></a>F# 프로젝트를 만들고 구성하려면

1. 이전에 만든 프로젝트를 닫고 다른 프로젝트를 만들고 이름을 **SchoolEDM**합니다.
<br />

2. **솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.
<br />

3. 선택 된 **프레임 워크** 노드를 선택한 다음는 **프레임 워크** 목록에서 선택 **System.Data**, **System.Data.Entity**, 및 **System.Data.Linq**합니다.
<br />

4. 선택은 **확장** 노드를에 대 한 참조를 추가 [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) 어셈블리를 선택한 후는 **확인** 단추 대화 상자를 닫습니다.
<br />

5. 다음 코드를 추가하여 내부 모듈을 정의하고 적절한 네임스페이스를 엽니다. 형식 공급자는 형식을 개인 또는 내부 네임스페이스로만 주입할 수 있습니다.
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. 로 컴파일된 프로그램 대신 스크립트 대화형으로이 연습에서 코드를 실행 하려면를 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **새 항목 추가**, F # 스크립트 파일을 추가 하 고 스크립트에 코드의 각 단계를 추가 합니다. 어셈블리 참조를 로드하려면 다음 줄을 추가합니다.
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. 코드 블록을 추가할 때 각 블록을 강조 표시하고 F# Interactive에서 Alt + Enter 키를 눌러 강조 표시한 블록을 실행합니다.
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>형식 공급자를 구성하고 엔터티 데이터 모델에 연결합니다.
이 단계에서 데이터 연결을 사용하여 형식 공급자를 설정하고 데이터로 작업할 수 있는 데이터 컨텍스트를 가져옵니다.


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>형식 공급자를 구성하고 엔터티 데이터 모델에 연결하려면

1. 다음 코드를 입력하여 이전에 사용자가 만든 엔터티 데이터 모델을 기반으로 F# 형식을 생성하는 `SqlEntityConnection` 형식 공급자를 구성합니다. 전체 EDMX 연결 문자열 대신 SQL 연결 문자열만 사용합니다.
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  이 작업을 통해 앞에서 만든 데이터베이스 연결로 형식 공급자를 설정합니다. `MultipleActiveResultSets` 속성을 통해 한 연결로 데이터베이스에서 비동기적으로 여러 명령을 실행할 수 있고 ADO.NET Entity Framework 코드에서 이런 일이 자주 발생할 수 있기 때문에, ADO.NET Entity Framework를 사용할 때 이 속성이 필요합니다. 자세한 내용은 [MARS(여러 활성 결과 집합)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars)를 참조하세요.
<br />

2. 데이터베이스 테이블을 속성으로 포함하고 데이터베이스 저장 프로시저와 함수를 메서드로 포함하는 개체인 데이터 컨텍스트를 가져옵니다.
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>데이터베이스 쿼리
이 단계에서는 F# 쿼리 식을 사용하여 데이터베이스에서 다양한 쿼리를 실행합니다.


#### <a name="to-query-the-data"></a>데이터를 쿼리하려면

- 엔터티 데이터 모델에서 데이터를 쿼리하려면 다음 코드를 입력합니다. 데이터베이스 테이블 Course를 Courses로, Person을 People로 변경하는 Pluralize = true의 효과에 유의하십시오.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a>데이터베이스 업데이트
데이터베이스를 업데이트하려면 Entity Framework 클래스와 메서드를 사용합니다. 두 가지 형식의 데이터 컨텍스트를 SQLEntityConnection 형식 공급자와 함께 사용할 수 있습니다. 첫째, `ServiceTypes.SimpleDataContextTypes.EntityContainer`는 데이터베이스 테이블과 열을 나타내는 제공된 속성만 포함하는 단순화된 데이터 컨텍스트입니다. 둘째, 전체 데이터 컨텍스트는 데이터베이스에 행을 추가하기 위해 `System.Data.Objects.ObjectContext` 메서드를 포함하는 Entity Framework 클래스 `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)`의 인스턴스입니다. Entity Framework는 테이블과 이 테이블 사이의 관계를 인식하므로 데이터베이스 일관성이 적용됩니다.


#### <a name="to-update-the-database"></a>데이터베이스를 업데이트하려면

1. 프로그램에 다음 코드를 추가합니다. 이 예제에서 관계가 있는 두 개체를 추가하고 강사 및 사무실 할당을 추가합니다. `OfficeAssignments` 테이블에는 `InstructorID` 테이블의 `PersonID` 열을 참조하는 `Person` 열이 포함되어 있습니다.
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

`System.Data.Objects.ObjectContext.SaveChanges`를 호출할 때까지 데이터베이스에서 변경된 사항이 없습니다.
<br />

2. 이제 추가한 개체를 삭제하여 데이터베이스를 이전 상태로 복원합니다.
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
쿼리 식을 사용하는 경우 쿼리에서 평가가 지연될 수 있음을 기억해야 합니다. 따라서 데이터베이스는 각 쿼리 식 다음에 lambda 식 블록에서처럼 연결된 평가 중에 읽을 수 있도록 계속 열려 있습니다. 명시적 또는 묵시적으로 트랜잭션을 사용하는 데이터베이스 작업은 읽기 작업이 완료된 후에 발생해야 합니다.


## <a name="next-steps"></a>다음 단계
사용할 수 있는 쿼리 연산자를 검토 하 여 다른 쿼리 옵션을 탐색할 [쿼리 식은](../../language-reference/query-expressions.md)도 검토 하 고는 [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) 어떤 기능을 사용할 수를 이해 하려면 이 형식 공급자를 사용 합니다.


## <a name="see-also"></a>참고 항목
[형식 공급자](index.md)

[SqlEntityConnection 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)

[연습: EDMX 스키마 파일에서 F # 형식 생성](generating-fsharp-types-from-edmx.md)

[ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572)

[.edmx 파일 개요](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[EDM 생성기 &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)
