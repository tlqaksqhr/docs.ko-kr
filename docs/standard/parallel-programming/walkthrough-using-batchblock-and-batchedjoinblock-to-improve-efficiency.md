---
title: "Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, improving efficiency"
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency
TPL 데이터 흐름 라이브러리는 여러분이 하나 이상의 소스에서 데이터를 버퍼링하고 받은 다음 하나의 컬렉션으로 버퍼링된 데이터가 전파되도록 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=fullName> 과 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=fullName> 클래스들을 제공합니다.  이 일괄 처리 메커니즘을 여러 소스에서 데이터를 수집하고 여러 데이터 요소를 일괄 처리로 처리할 때 유용 합니다.  예를 들어, 응용 프로그램이 데이터 흐름을 사용하여 데이터베이스에 레코드를 삽입 하는 것이 좋습니다.  이 작업은 여러 항목을 한 번에 하나씩 연속적으로 넣는 대신 동시에 여러개를 삽입하는 것이 더 효율적일 수 있습니다.  이 문서에서는 데이터 베이스 삽입 작업의 효율성 향상을 위한 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스의 사용 방법을 설명합니다.  또한 결과와 데이터베이스로부터 프로그램이 읽어올때 발생하는 예외 모두를 캡쳐하기 위해 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 클래스를 사용하는 방법을 설명합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 사전 요구 사항  
  
1.  이 연습을 시작하기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 에서 '블록 세션 참가'를 확인합니다.  
  
2.  컴퓨터에서 사용할 수 있는 Northwind.sdf, Northwind 데이터베이스의 복사본을 가지고 있는지 확인하세요.  이 파일은 일반적으로 %Program Files%\\Microsoft SQL Server Compact Edition\\v3.5\\Samples\\. 폴더에 있습니다.  
  
    > [!IMPORTANT]
    >  일부 버전의 Windows에서, [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 이 비 관리자 모드로 실행되고 있으면 Northwind.sdf 에 연결할 수 없습니다.  Northwind.sdf에 연결 하려면, **관리자 권한으로 실행** 모드에서 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 의 명령 프롬프트를 시작합니다.  
  
 이 연습에는 다음 단원이 포함되어 있습니다.  
  
-   [콘솔 응용 프로그램 만들기](#creating)  
  
-   [Employee 클래스 정의](#employeeClass)  
  
-   [Employee 데이터베이스 작업을 정의합니다.](#operations)  
  
-   [Employee 데이터를 버퍼링을 사용하지 않고 데이터베이스에 추가](#nonBuffering)  
  
-   [Employee 데이터를 데이터베이스에 추가하기 위해 버퍼링을 사용](#buffering)  
  
-   [데이터베이스로부터 버퍼된 Employee 데이터를 추가하여 사용](#bufferedJoin)  
  
-   [전체 예제](#complete)  
  
<a name="creating"></a>   
## 콘솔 응용 프로그램 만들기  
  
<a name="consoleApp"></a>   
1.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 에서, Visual C\# 또는 Visual Basic **콘솔 응용 프로그램** 프로젝트를 만듭니다.  이 문서에서, 프로젝트 이름은 `DataflowBatchDatabase` 입니다.  
  
2.  프로젝트에서, System.Data.SqlServerCe.dll에 대한 참조 및 System.Threading.Tasks.Dataflow.dll에 대한 참조를 프로젝트에 추가 합니다.  
  
3.  다음 `using` \( [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서`Imports` \)명세서들을 포함하는 해당 Form1.cs \( [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에 대한 Form1.vb\) 을 확인하세요.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  `Program` 클래스에 다음의 데이터 멤버를 추가합니다.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## Employee 클래스 정의  
 `Program` 클래스에 `Employee` 클래스를 추가합니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 `Employee` 클래스는 `EmployeeID`, `LastName` 및 `FirstName` 이라는 세가지 속성을 가지고 있습니다.  이러한 속성인 `Employee ID`, `Last Name`, 및 `First Name` 들은 Northwind 데이터베이스에서 `Employees` 테이블의 열에 해당됩니다.  이 데모에서, `Employee` 클래스 역시 이들 속성에 대한 임의의 값을 가지는 `Employee` 개체를 만드는 `Random` 메서드를 정의합니다.  
  
<a name="operations"></a>   
## Employee 데이터베이스 작업을 정의합니다.  
 `Program` 클래스에 `InsertEmployees` 및 `GetEmployeeCount`, `GetEmployeeID` 메서드를 추가합니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 `InsertEmployees` 메서드는 데이터베이스에 새 직원 레코드를 추가 합니다.  `GetEmployeeCount` 메서드는 `Employees` 테이블에서 엔트리들의 수를 검색합니다.  `GetEmployeeID` 메서드는 제공된 이름을 가진 첫 번째 직원의 식별자를 검색 합니다.  이러한 각 메서드들은 Northwind 데이터베이스에 연결 문자열을 사용하고 데이터베이스와 통신하기위해 `System.Data.SqlServerCe` 네임 스페이스에서 기능적으로 사용합니다.  
  
<a name="nonBuffering"></a>   
## Employee 데이터를 버퍼링을 사용하지 않고 데이터베이스에 추가  
 `Program` 클래스에 `AddEmployees` 및 `PostRandomEmployees`, 메서드를 추가합니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 `AddEmployees` 메서드는 데이터 흐름을 사용하여 임의의 직원 데이터를 데이터베이스에 추가 합니다.  데이터베이스의 직원 엔트리를 추가하려면 `InsertEmployees` 메서드를 부르는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체를 생성합니다.  `AddEmployees` 메서드 이후에는 여러개의 `Employee` 개체들과 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개채를 게시하기 위해 `PostRandomEmployees` 메서드를 호출합니다.  `AddEmployees` 메서드 이후 모든 삽입 작업이 끝날때까지 기다립니다.  
  
<a name="buffering"></a>   
## Employee 데이터를 데이터베이스에 추가하기 위해 버퍼링을 사용  
 다음 `Program` 클래스에 `AddEmployeesBatched` 메서드를 추가합니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 이 메서드는 이들 개체를 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체로 보내기 전에 여러 `Employee` 개체를 버퍼링하기 위해 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 를 사용한다는 것을 제외하고 `AddEmployees`와 유사합니다.  <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스가 한 컬렉션으로 여러 요소들을 전파하기 때문에, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 `Employee` 개체의 배열에 따라 행동하도록 수정됩니다.  `AddEmployees` 메서드에서처럼, `AddEmployeesBatched` 는 여러 `Employee` 개체들을 게시하기 위해 `PostRandomEmployees` 메서드를 호출합니다; 하지만 `AddEmployeesBatched` 는 이러한 개체들을 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체로 표시합니다.  `AddEmployeesBatched`  메서드 역시 모든 삽입 작업이 끝날때까지 기다립니다.  
  
<a name="bufferedJoin"></a>   
## 데이터베이스로부터 버퍼된 Employee 데이터를 추가하여 사용  
 다음 `Program` 클래스에 `GetRandomEmployees` 메서드를 추가합니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 이 메서드는 콘솔에 임의의 직원에 대한 정보를 출력합니다.  이것은 몇 가지 임의의 `Employee` 개체를 만들고 각 개체들의 고유 식별자를 검색하기 위해 `GetEmployeeID` 메서드를 호출합니다.  만일 주어진 성과 이름이 일치하는 직업이 없는 경우, `GetEmployeeID` 메서드는 예외를 표시하기때문에, `GetRandomEmployees` 메서드는 `GetEmployeeID` 의 호출이 성공했다면 `Employee` 개체를 저장하고 호출에 실패했다면 <xref:System.Exception?displayProperty=fullName> 개체를 처리하기 위해 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 클래스를 사용합니다.  이 예제에서 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 `Employee` 개체들과 <xref:System.Exception> 개체들의 목록을 수용하는 <xref:System.Tuple%602> 개체에 따라 행동합니다.  `Employee` 와 <xref:System.Exception> 개체 합의 수가 일괄 처리 크리와 동일해 졌을 때, <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체는 이 데이터를 전파합니다.  
  
<a name="complete"></a>   
## 전체 예제  
 다음 예제에서는 전체 코드를 보여 줍니다.  `Main` 메서드는 일괄 처리되지않은 데이터베이스에 삽입 하는데 드는 시간과 일괄 처리된 데이터베이스 삽입하는데 필요한 시간을 비교 합니다.  이것은 데이터베이스에서 직원 데이터를 읽고 버퍼링된 조인에 사용되어 발표되고, 또한 보고서 오류에도 사용됩니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)