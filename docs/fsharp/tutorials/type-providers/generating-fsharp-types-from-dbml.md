---
title: "연습: DBML 파일에서 F# 형식 생성(F#)"
description: ".Dbml 파일에 인코딩된 스키마 정보가 있는 경우 F # 3.0의 데이터베이스에서 데이터에 대 한 F # 형식을 만드는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: a919c2acb2b5b8c2ce93124f2f541bd092d15c35
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>연습: DBML 파일에서 F# 형식 생성

> [!NOTE]
이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.  최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.

> [!NOTE]
API 참조 링크 MSDN을 이동 합니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 연습에서는 F # 3.0에 대 한 스키마 정보 인코딩된.dbml 파일에 있는 경우 데이터베이스에서 데이터에 대 한 종류를 만드는 방법을 설명 합니다. LINQ to SQL 데이터베이스 스키마를 나타내기 위해이 파일 형식을 사용 합니다. 개체 관계 (O/R) 디자이너를 사용 하 여 Visual Studio에서 LINQ to SQL 스키마 파일을 생성할 수 있습니다. 자세한 내용은 참조 [O/R 디자이너 개요](https://msdn.microsoft.com/library/bb384511.aspx) 및 [LINQ to SQL에서에서 코드 생성](../../../../docs/framework/data/adonet/sql/linq/index.md)합니다.

데이터베이스 태그 언어 (DBML) 형식 공급자를 사용 하면 컴파일 타임에 정적 연결 문자열을 지정 하지 않아도 데이터베이스 스키마에 따라 형식을 사용 하는 코드를 작성할 수 있습니다. 다른 데이터베이스, 다른 자격 증명 또는 응용 프로그램을 개발 하는 데 1 보다 다양 한 연결 문자열은 최종 응용 프로그램과 사용 합니다 가능성에 대 한 허용 해야 하는 경우에 유용할 수 있습니다. 컴파일 타임에 사용할 수 있는 데이터베이스를 직접 연결 하는 경우이 동일한 데이터베이스와 결국 빌드된 응용 프로그램에서 사용할 자격 증명도 SQLDataConnection 형식 공급자를 사용할 수 있습니다. 자세한 내용은 참조 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다.

이 연습에서는 다음 작업을 수행합니다. 이 연습을 완료 하려면이 순서 대로 완료 해야 합니다.


- .Dbml 파일 만들기
<br />

- 만들기 및 F # 프로젝트를 설정 합니다.
<br />

- 형식 공급자를 구성 하 고 형식을 생성 합니다.
<br />

- 데이터베이스 쿼리
<br />


## <a name="prerequisites"></a>필수 구성 요소

## <a name="creating-a-dbml-file"></a>.Dbml 파일 만들기
데이터베이스에서 테스트를 없는 경우 아래쪽의 지침에 따라 하나를 만들 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다. 다음이 지침을 따를 경우 몇 가지 간단한 테이블 및 저장된 프로시저 SQL Server에 포함 된 MyDatabase 라는 데이터베이스를 만들어집니다.

.Dbml 파일을 이미 보유 하는 경우 섹션으로 건너뛸 수 있습니다 **만들고는 F # 프로젝트 설정**합니다. 그렇지 않으면 기존 SQL 데이터베이스를 지정 하는.dbml 파일을 만들 수 있으며 명령줄을 사용 하 여 SqlMetal.exe 도구.


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>SqlMetal.exe를 사용 하 여.dbml 파일을 만들려면

1. 열기는 **개발자 명령 프롬프트**합니다.
<br />

2. 입력 하 여 SqlMetal.exe에 액세스할 수 있는지 확인 하십시오. `SqlMetal.exe /?` 명령 프롬프트입니다. SqlMetal.exe 아래에 일반적으로 설치 되는 **Microsoft Sdk** 폴더에 **Program Files** 또는 **Program Files (x86)**합니다.
<br />

3. 다음 명령줄 옵션으로 SqlMetal.exe를 실행 합니다. 대신 적절 한 경로 대체 `c:\destpath` .dbml 파일을 만들고 데이터베이스 서버에 대 한 적절 한 값을 삽입 하려면 인스턴스 이름과 데이터베이스 이름입니다.
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
SqlMetal.exe 권한 문제로 인해 파일을 만드는 데 문제가 있으면 현재 디렉터리에 대 한 쓰기 권한이 있는 폴더로 변경 합니다.


4. 다른 사용 가능한 명령줄 옵션을 살펴볼 수도 있습니다. 예를 들어, 보기 및 생성된 된 형식에 포함 된 SQL 함수를 사용할 수 있는 옵션 있습니다. 자세한 내용은 참조 [SqlMetal.exe &#40; 코드 생성 도구 &#41; ](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>만들기 및 F # 프로젝트를 설정 합니다.
이 단계에서는 프로젝트를 만들고 DBML 형식 공급자를 사용 하려면 적절 한 참조를 추가 합니다.


#### <a name="to-create-and-set-up-an-f-project"></a>F# 프로젝트를 만들고 설정하려면

1. 새 F # 콘솔 응용 프로그램 프로젝트를 솔루션에 추가 합니다.
<br />

2. **솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.
<br />

3. 에 **어셈블리** 영역에서 선택 된 **프레임 워크** 노드를 사용할 수 있는 어셈블리의 목록에서 선택 합니다는 **System.Data** 및 **System.Data.Linq**  어셈블리입니다.
<br />

4. 에 **어셈블리** 영역에서 선택 **확장**, 한 다음 사용할 수 있는 어셈블리의 목록에서 선택 **FSharp.Data.TypeProviders**합니다.
<br />

5. 선택 된 **확인** 단추를 프로젝트에 이러한 어셈블리에 대 한 참조를 추가 합니다.
<br />

6. (선택 사항) 이전 단계에서 만든.dbml 파일을 복사한 프로젝트에 대 한 기본 폴더에 파일을 붙여 넣습니다. 이 폴더는 프로젝트 파일 (.fsproj) 및 코드 파일에 있습니다. 메뉴 모음에서 **프로젝트**, **기존 항목 추가**, 프로젝트에 추가 하려면.dbml 파일을 지정 합니다. 이러한 단계를 완료 하는 경우 다음 단계에서 ResolutionFolder static 매개 변수를 생략할 수 있습니다.
<br />

## <a name="configuring-the-type-provider"></a>형식 공급자 구성
이 섹션에서는 형식 공급자를 만들고.dbml 파일에 설명 되어 있는 스키마에서 형식을 생성 합니다.


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>형식 공급자 구성 하는 형식을 생성 합니다.

- 열립니다는 코드를 추가 **TypeProviders** 네임 스페이스를 사용 하려면.dbml 파일에 대 한 형식 공급자를 인스턴스화합니다. 프로젝트에.dbml 파일을 추가한 경우 ResolutionFolder static 매개 변수를 생략할 수 있습니다.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

DataContext 형식의 생성 된 모든 형식에 액세스할 수 있고에서 상속 `System.Data.Linq.DataContext`합니다. DbmlFile 형식 공급자가 설정할 수 있는 다양 한 정적 매개 변수입니다. DataContext 형식에 다른 이름을 지정 하 여 사용할 수는 예를 들어 `DataContext=MyDataContext`합니다. 이 경우 코드에는 다음 예제를 비슷합니다.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>데이터베이스 쿼리
이 섹션에서는 F # 쿼리 식을 사용 하 여 데이터베이스를 쿼리 합니다.


#### <a name="to-query-the-data"></a>데이터를 쿼리하려면

- 데이터베이스를 쿼리 하는 코드를 추가 합니다.
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>다음 단계
다른 쿼리 식을 사용 하 여 또는 데이터베이스 연결에서 데이터 컨텍스트를 가져오고 일반 ADO.NET 데이터 작업을 수행할 진행할 수 있습니다. 추가 단계에 대 한 섹션을 참조 "의 데이터 쿼리" 후에 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다.


## <a name="see-also"></a>참고 항목
[DbmlFile 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[형식 공급자](index.md)

[연습: 형식 공급자를 사용하여 SQL Database에 액세스](accessing-a-sql-database.md)

[SqlMetal.exe &#40; 코드 생성 도구 &#41;](https://msdn.microsoft.com/library/bb386987)

[쿼리 식](../../language-reference/query-expressions.md)
