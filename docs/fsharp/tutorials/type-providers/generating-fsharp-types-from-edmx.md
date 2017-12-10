---
title: "연습: EDMX 스키마 파일에서 F# 형식 생성(F#)"
description: "F #으로 데이터 모델 EDM (엔터티) F # 3.0에서는.edmx 파일에는 스키마가 지정 하는 표시 된 데이터에 대 한 유형을 만드는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 1df0344e8dab2b40d82d1b9c61ccd2f026906243
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>연습: EDMX 스키마 파일에서 F# 형식 생성

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

F# 3.0에 대한 이 연습에서는 .edmx 파일에 지정된 스키마인 EDM(엔터티 데이터 모델)으로 표시하는 데이터 형식을 만드는 방법을 보여줍니다. 또한 이 연습에서는 EdmxFile 형식 공급자를 사용하는 방법을 보여줍니다. 시작하기 전에 SqlEntityConnection 형식 공급자가 보다 적절한 형식 공급자 옵션인지 고려하십시오. SqlEntityConnection 형식 공급자는 프로젝트 개발 단계 동안 연결할 수 있는 라이브 데이터베이스가 있는 시나리오에 가장 적합하며 컴파일 시간에 연결 문자열을 지정해도 됩니다. 그러나 이 형식 공급자는 EdmxFile 형식 공급자만큼 많은 데이터베이스 기능을 노출하지 않는다는 제한도 있습니다. 또한 엔터티 데이터 모델을 사용하는 데이터베이스 프로젝트에 대한 라이브 데이터베이스 연결이 없는 경우 .edmx 파일을 사용하여 데이터베이스를 코딩할 수 있습니다. EdmxFile 형식 공급자를 사용하면 F# 컴파일러에서 EdmGen.exe를 실행하여 여기에서 제공하는 형식을 생성합니다.

이 연습에서는 다음 작업을 설명하는데, 연습을 성공적으로 수행하려면 이 순서대로 작업을 수행해야 합니다.


- EDMX 파일 만들기
<br />

- 프로젝트 만들기
<br />

- 엔터티 데이터 모델 연결 문자열 찾기 또는 만들기
<br />

- 형식 공급자 구성
<br />

- 데이터 쿼리
<br />

- 저장 프로시저 호출
<br />


## <a name="prerequisites"></a>필수 구성 요소

## <a name="creating-an-edmx-file"></a>EDMX 파일 만들기
EDMX 파일이 이미 있는 경우 이 단계를 건너뛸 수 있습니다.


#### <a name="to-create-an-edmx-file"></a>EDMX 파일을 만들려면

- EDMX 파일이 없는 경우 단계에서이 연습의 끝에 있는 지침을 따라 수 있습니다 [엔터티 데이터 모델 구성](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model)합니다.
<br />

## <a name="creating-the-project"></a>프로젝트 만들기
이 단계에서 EDMX 형식 공급자를 사용하려면 프로젝트를 만들고 이 프로젝트에 적절한 참조를 추가합니다.


#### <a name="to-create-and-set-up-an-f-project"></a>F# 프로젝트를 만들고 설정하려면

1. 이전 프로젝트를 닫고 SchoolEDM이라는 새 프로젝트를 만듭니다.
<br />

2. **솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.
<br />

3. 에 **어셈블리** 영역에서 선택 된 **프레임 워크** 노드.
<br />

4. 사용할 수 있는 어셈블리의 목록에서 선택은 **System.Data.Entity** 및 **System.Data.Linq** 어셈블리를 선택한 후는 **추가** 이러한에 대 한 참조를 추가 하려면 단추 프로젝트에 어셈블리입니다.
<br />

5. 에 **어셈블리** 영역 선택 하는 **확장** 노드.
<br />

6. 사용 가능한 확장명 목록에서 FSharp.Data.TypeProviders 어셈블리에 대한 참조를 추가합니다.
<br />

7. 다음 코드를 추가하여 적절한 네임스페이스를 엽니다.
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>엔터티 데이터 모델에 대한 연결 문자열 찾기 또는 만들기
엔터티 데이터 모델에 대한 연결 문자열(EDMX 연결 문자열)에는 데이터베이스 공급자 연결 문자열뿐 아니라 추가 정보도 포함됩니다. 예를 들어, 간단한 SQL Server 데이터베이스에 대한 EDMX 연결 문자열은 다음 코드와 유사합니다.

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

EDMX 연결 문자열에 대 한 자세한 내용은 참조 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)합니다.


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>엔터티 데이터 모델에 대한 연결 문자열을 찾거나 만들려면

1. EDMX 연결 문자열을 직접 생성하는 것은 어려울 수 있으므로 프로그래밍 방식으로 생성하여 시간을 절약할 수 있습니다. EDMX 연결 문자열을 알고 있는 경우 이 단계를 건너뛰고 다음 단계에서 단순히 해당 연결 문자열을 사용할 수 있습니다. 그렇지 않으면 다음 코드를 사용하여 사용자가 제공하는 데이터베이스 연결 문자열에서 EDMX 연결 문자열을 생성합니다.
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a>형식 공급자 구성
이 단계에서는 EDMX 연결 문자열로 형식 공급자를 만들고 구성하며 .edmx 파일에 정의된 스키마에 대해 형식을 생성합니다.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>형식 공급자를 구성하고 형식을 생성하려면

1. 이 연습의 첫 번째 단계에서 생성한 .edmx 파일을 프로젝트 폴더에 복사합니다.
<br />

2. F # 프로젝트의 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 선택 **기존 항목 추가**, 프로젝트에 추가할.edmx 파일을 선택 합니다.
<br />

3. .edmx 파일의 형식 공급자를 활성화하려면 다음 코드를 입력합니다. 대체 *서버*\*인스턴스 * SQL Server 이름과 해당 인스턴스를 실행 하 고이 연습에는 첫 번째 단계에서.edmx 파일의 이름을 사용 하는 서버의 이름으로 합니다.
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>데이터 쿼리
이 단계에서는 F# 쿼리 식을 사용하여 데이터베이스를 쿼리합니다.


#### <a name="to-query-the-data"></a>데이터를 쿼리하려면

- 엔터티 데이터 모델의 데이터를 쿼리하려면 다음 코드를 입력합니다.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a>저장 프로시저 호출
EDMX 형식 공급자를 사용하여 저장 프로시저를 호출할 수 있습니다. 다음 절차에서 School 데이터베이스 저장된 프로시저를 포함 **UpdatePerson**, 새 값 열에 대 한 레코드를 업데이트 합니다. DataContext 형식의 메서드로 노출되기 때문에 이 저장된 프로시저를 사용할 수 있습니다.


#### <a name="to-call-a-stored-procedure"></a>저장 프로시저를 호출하려면

- 다음 코드를 추가하여 레코드를 업데이트합니다.
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

성공한다면 결과는 1입니다. 다음에 유의 **exactlyOne** 반환 되 고, 그렇지 않으면은 한 결과만, 예외가 throw 되는 쿼리 식에서 사용 됩니다. 또한 null 허용 값을 보다 쉽게 작업할 수 있습니다 사용할 간단한 **nullable** 일반 값에서 null 허용 값을 만드는 데이 코드에 정의 된 함수입니다.

<br />

## <a name="configuring-the-entity-data-model"></a>엔터티 데이터 모델 구성
데이터베이스에서 전체 엔터티 데이터 모델을 생성하는 방법을 알고 싶고 테스트할 데이터베이스가 없는 경우에만 이 절차를 완료해야 합니다.


#### <a name="to-configure-the-entity-data-model"></a>엔터티 데이터 모델을 구성하려면

1. 메뉴 모음에서 **SQL**, **TRANSACT-SQL 편집기**, **새 쿼리** 데이터베이스를 만들 수 있습니다. 메시지가 나타나면 데이터베이스 서버 및 인스턴스를 지정합니다.
<br />

2. 에 설명 된 대로 학생 데이터베이스가 생성 하는 데이터베이스 스크립트의 내용을 복사한는 [Entity Framework 설명서](http://msdn.microsoft.com/data/JJ614587.aspx) 데이터 개발자 센터에서.
<br />

3. 삼각형 기호 있는 도구 모음 단추를 선택 하거나 Ctrl + Q 키를 선택 하 여 SQL 스크립트를 실행 합니다.
<br />

4. **서버 탐색기**, 바로 가기 메뉴를 열고 **데이터 연결**, 선택 **연결 추가**, 인스턴스 이름의 이름 데이터베이스 서버의 이름을 입력 합니다 및 School 데이터베이스입니다.
<br />

5. C# 또는 Visual Basic 콘솔 응용 프로그램 프로젝트 만들기, 해당 바로 가기 메뉴를 열고, 선택 **새 항목 추가**를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.
<br />  엔터티 데이터 모델 마법사가 열립니다. 이 마법사를 사용하면 엔터티 데이터 모델을 생성하는 방법을 선택할 수 있습니다.
<br />

6. 아래 **모델 콘텐츠 선택**, 선택는 **데이터베이스에서 생성** 확인란 합니다.
<br />

7. 다음 페이지에서 새로 만든 School 데이터베이스를 데이터 연결로 선택합니다.
<br />  이 연결 비슷해야  **&lt;servername&gt;.&lt; instancename&gt;합니다. School.dbo**합니다.
<br />

8. 엔터티 연결 문자열은 나중에 중요할 수 있으므로 클립보드에 복사합니다.
<br />

9. 엔터티 연결 문자열을 저장 하려면 확인란이 선택 되어 있는지 확인은 **App.Config** 파일을 선택 하 고 필요한 경우 나중에, 연결 문자열을 찾고 하는 데 도움이 되도록 하 고 텍스트 상자에서 문자열 값을 확인 합니다.
<br />

10. 다음 페이지에서 선택 **테이블** 및 **저장 프로시저 및 함수**합니다.
<br />  이러한 최상위 노드를 선택하여 테이블, 저장 프로시저 및 함수를 모두 선택합니다. 원할 경우 개별적으로 선택할 수도 있습니다.
<br />

11. 다른 설정의 확인란이 선택되어 있는지 확인합니다.
<br />  첫 번째 **복수화 또는 생성 된 개체 이름을 단 수 화** 확인란 데이터베이스 테이블을 나타내는 명명 개체의 규칙과 일치 하도록 복수로, 단 수 양식을 변경 여부를 나타냅니다. **모델에 외래 키 열을 포함할** 확인란 목적은 데이터베이스 스키마에 대해 생성 된 개체 유형의 다른 필드에 조인 하려면 필드를 포함할지 여부를 결정 합니다. 세 번째 확인란은 모델에 저장 프로시저 및 함수를 포함하는지 여부를 나타냅니다.
<br />

12. 선택 된 **마침** School 데이터베이스를 기반으로 하는 엔터티 데이터 모델을 포함 하는.edmx 파일을 생성 하는 단추입니다.
<br />  파일을 **Model1.edmx**, 프로젝트에 추가 데이터베이스 다이어그램이 나타납니다.
<br />

13. 메뉴 모음에서 **보기**, **다른 창**, **엔터티 데이터 모델 브라우저** 모델의 모든 세부 정보를 보려면 또는 **엔터티 데이터 모델 매핑 정보**  생성 된 개체 모델을 데이터베이스 테이블 및 열에 매핑하는 방법을 보여 주는 창을 엽니다.
<br />


## <a name="next-steps"></a>다음 단계
에 나열 된 사용 가능한 쿼리 연산자 확인 하 여 다른 쿼리를 탐색 [쿼리 식](../../language-reference/query-expressions.md)합니다.


## <a name="see-also"></a>참고 항목
[형식 공급자](index.md)

[EdmxFile 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스](accessing-a-sql-database-entities.md)

[Entity Framework](http://msdn.microsoft.com/data/ef)

[.edmx 파일 개요](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[EDM 생성기 &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)

