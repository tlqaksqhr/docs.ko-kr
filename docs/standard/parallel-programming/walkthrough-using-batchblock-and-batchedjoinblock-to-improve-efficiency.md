---
title: "연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc74b4acc5b29395c05e7c8302caefeb51718282
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상
TPL 데이터 흐름 라이브러리가 제공는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> 클래스를 수신 하 고 하나 이상의 소스에서 데이터를 버퍼링 하 고 다음 하나의 컬렉션으로 버퍼링 된 해당 데이터를 전파 수 있도록 합니다. 이 일괄 처리 메커니즘 하나 이상의 소스에서 데이터를 수집 하 고 다음 일괄 처리로 여러 데이터 요소를 처리 하는 경우에 유용 합니다. 예를 들어 데이터 흐름을 사용 하 여 데이터베이스에 레코드를 삽입 하는 응용 프로그램을 것이 좋습니다. 이 작업은 여러 항목을 한 번에 하나씩 대신 한 번에 순차적 삽입 하는 경우 보다 효율적일 수 있습니다. 이 문서에 사용 하는 방법에 설명 된 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 이러한 데이터베이스의 효율성을 개선 하기 위해 클래스 삽입 작업입니다. 사용 하는 방법에 대해서도 설명는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 결과 프로그램이 데이터베이스에서 읽는 경우 발생 하는 모든 예외를 캡처하는 클래스입니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
1.  블록 조인 섹션을 읽어는 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 이 연습을 시작 하기 전에 문서화 합니다.  
  
2.  컴퓨터에서 사용할 수 있는 Northwind.sdf Northwind 데이터베이스의 복사본을가지고 있는지 확인 합니다. 이 파일은 % Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples 폴더에에서 있습니다 일반적으로\\합니다.  
  
    > [!IMPORTANT]
    >  일부 버전의 Windows에서 연결할 수 없으면 Northwind.sdf 경우 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 관리자가 아닌 모드로 실행 되 고 있습니다. 시작 Northwind.sdf 연결할 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 의 명령 프롬프트는 **관리자 권한으로 실행** 모드입니다.  
  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
-   [콘솔 응용 프로그램 만들기](#creating)  
  
-   [직원 클래스 정의](#employeeClass)  
  
-   [직원 데이터베이스 작업을 정의합니다.](#operations)  
  
-   [직원 데이터를 버퍼링을 사용 하지 않고 데이터베이스에 추가](#nonBuffering)  
  
-   [버퍼링을 사용 하 여 직원 데이터는 데이터베이스를 추가 하려면](#buffering)  
  
-   [버퍼링 된 Join을 사용 하 여 데이터베이스에서 직원 데이터를 읽을 수](#bufferedJoin)  
  
-   [전체 예제](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a>콘솔 응용 프로그램 만들기  
  
<a name="consoleApp"></a>   
1.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], Visual C# 또는 Visual Basic 만들 **콘솔 응용 프로그램** 프로젝트. 이 문서에서 프로젝트 이름은 `DataflowBatchDatabase`입니다.  
  
2.  프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대 한 참조 및 System.Data.SqlServerCe.dll에 대 한 참조를 추가 합니다.  
  
3.  확인 해당 Form1.cs (Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])는 다음이 포함 `using` (`Imports` 에 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 문입니다.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  `Program` 클래스에 다음 데이터 멤버를 추가합니다.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a>직원 클래스 정의  
 에 추가 된 `Program` 클래스는 `Employee` 클래스입니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 `Employee` 세 가지 속성을 포함 하는 클래스 `EmployeeID`, `LastName`, 및 `FirstName`합니다. 이러한 속성에 해당 하는 `Employee ID`, `Last Name`, 및 `First Name` 열에는 `Employees` Northwind 데이터베이스의 테이블입니다. 이 데모에서는 `Employee` 클래스도 정의 `Random` 을 만드는 메서드는 `Employee` 해당 속성에 대 한 임의 값을 가진 개체를 합니다.  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a>직원 데이터베이스 작업을 정의합니다.  
 에 추가 된 `Program` 클래스는 `InsertEmployees`, `GetEmployeeCount`, 및 `GetEmployeeID` 메서드.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 `InsertEmployees` 메서드는 새 직원 레코드가 데이터베이스에 추가 합니다. `GetEmployeeCount` 에 있는 항목의 수를 검색 하는 메서드는 `Employees` 테이블입니다. `GetEmployeeID` 메서드는 제공 된 이름이 있는 첫 번째 직원의 식별자를 검색 합니다. Northwind 데이터베이스에 연결 문자열을 사용 하 고에서 기능을 사용 하 여 이러한 각 방법의 `System.Data.SqlServerCe` 네임 스페이스는 데이터베이스와 통신할 수 있습니다.  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>직원 데이터를 버퍼링을 사용 하지 않고 데이터베이스에 추가  
 에 추가 된 `Program` 클래스는 `AddEmployees` 및 `PostRandomEmployees` 메서드.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 `AddEmployees` 메서드에서 데이터베이스에 데이터 흐름을 사용 하 여 무작위 직원 데이터를 추가 합니다. 만듭니다는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 호출 하는 개체는 `InsertEmployees` 메서드는 데이터베이스에 직원 항목을 추가 하도록 합니다. `AddEmployees` 메서드를 호출는 `PostRandomEmployees` 메서드 여러 게시를 `Employee` 개체는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다. `AddEmployees` 메서드는 다음 모든 삽입 작업 완료에 대 한 대기 합니다.  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a>버퍼링을 사용 하 여 직원 데이터는 데이터베이스를 추가 하려면  
 에 추가 된 `Program` 클래스는 `AddEmployeesBatched` 메서드.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 이 메서드가 유사한 `AddEmployees`사용 하 여 제외 하 고는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 여러 버퍼링 할 클래스 `Employee` 해당 개체를 보내기 전에 개체는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다. 때문에 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스 요소를 여러 컬렉션으로 전파는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체의 배열에 대해 작동 하도록 수정 됩니다 `Employee` 개체입니다. 그러나와 같이 `AddEmployees` 메서드를 `AddEmployeesBatched` 호출은 `PostRandomEmployees` 메서드 여러 게시를 `Employee` 개체이 고, `AddEmployeesBatched` 이러한 개체를 게시는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체입니다. `AddEmployeesBatched` 메서드는 또한 모든 삽입 작업 완료에 대 한 대기 합니다.  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>버퍼링 된 Join을 사용 하 여 데이터베이스에서 직원 데이터를 읽을 수  
 에 추가 된 `Program` 클래스는 `GetRandomEmployees` 메서드.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 이 메서드는 콘솔에 무작위 직원에 대 한 정보를 인쇄 합니다. 만들 여러 임의 `Employee` 개체와 호출은 `GetEmployeeID` 각 개체에 대 한 고유 식별자를 검색 하는 메서드입니다. 때문에 `GetEmployeeID` 메서드에서 지정 된 첫 번째 및 마지막 이름으로 일치 하는 직원이 없는 경우 예외가 throw는 `GetRandomEmployees` 메서드는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 저장할 수 있도록 클래스 `Employee` 개체에 대 한 성공적인 호출 `GetEmployeeID` 및 <xref:System.Exception?displayProperty=nameWithType> 대 한 호출에 실패 하는 개체입니다. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 이 예제는 개체에 작업을 수행는 <xref:System.Tuple%602> 목록을 보유 하는 개체 `Employee` 개체 및 목록이 <xref:System.Exception> 개체입니다. <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체가이 데이터 전파 때 받은 총 `Employee` 및 <xref:System.Exception> 개체 수와 동일한 일괄 처리 크기입니다.  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>전체 예제  
 다음 예제에서는 전체 코드를 보여 줍니다. `Main` 메서드 데이터베이스 비 일괄 처리 삽입 하는 데 시간 및 일괄 처리 된 데이터베이스 삽입 하는 데 필요한 시간을 비교 합니다. 또한 데이터베이스에서 직원 데이터를 읽고 오류를 보고할 수도 버퍼링 된 조인의 사용을 보여 줍니다.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
