---
title: "연습: 데이터 조작(C#)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 502023c3929ffaa6766c906ca32489b43915f0ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-manipulating-data-c"></a>연습: 데이터 조작(C#)
이 연습에서는 데이터베이스의 데이터를 추가, 수정 및 삭제하기 위한 기본 종단 간 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다. Northwind 샘플 데이터베이스의 복사본을 사용하여 고객을 추가하고, 고객의 이름을 변경하고, 주문을 삭제합니다.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습에서는 다음 사항이 필요합니다.  
  
-   이 연습에서는 파일을 보유하기 위해 전용 폴더("c:\linqtest6")가 사용됩니다. 연습을 시작하기 전에 먼저 이 폴더를 만듭니다.  
  
-   Northwind 샘플 데이터베이스  
  
     이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다. 자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다. 이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest6 폴더에 복사합니다.  
  
-   Northwind 데이터베이스에서 생성된 C# 코드 파일  
  
     [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 또는 SQLMetal을 사용하여 이 파일을 생성할 수 있습니다. 이 연습은 다음 명령줄을 사용하여 SQLMetal 도구를 통해 작성했습니다.  
  
     **sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**  
  
     자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.  
  
## <a name="overview"></a>개요  
 이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 솔루션 만들기  
  
-   데이터베이스 코드 파일을 프로젝트에 추가  
  
-   새 Customer 개체 만들기  
  
-   고객의 연락처 이름 수정  
  
-   주문 삭제  
  
-   이러한 변경 내용을 Northwind 데이터베이스로 전송  
  
## <a name="creating-a-linq-to-sql-solution"></a>LINQ to SQL 솔루션 만들기  
 이 첫 번째 작업에서는 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 프로젝트를 빌드하고 실행하는 데 필요한 참조가 들어 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 솔루션을 만듭니다.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>LINQ to SQL 솔루션을 만들려면  
  
1.  에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.  
  
2.  에 **프로젝트 형식** 창에는 **새 프로젝트** 대화 상자를 클릭 **Visual C#**합니다.  
  
3.  **템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.  
  
4.  에 **이름** 상자에서 입력 **LinqDataManipulationApp**합니다.  
  
5.  에 **위치** 상자, 프로젝트 파일을 저장할 위치를 확인 합니다.  
  
6.  **확인**을 클릭합니다.  
  
## <a name="adding-linq-references-and-directives"></a>LINQ 참조 및 지시문 추가  
 이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다. System.Data.Linq가 프로젝트에 참조로 나열되지 않은 경우 다음 단계에 설명된 대로 추가합니다.  
  
#### <a name="to-add-systemdatalinq"></a>System.Data.Linq를 추가하려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 클릭 하 고 **참조 추가**합니다.  
  
2.  에 **참조 추가** 대화 상자를 클릭 **.NET**System.Data.Linq 어셈블리를 클릭 한 다음 클릭, **확인**합니다.  
  
     어셈블리가 프로젝트에 추가됩니다.  
  
3.  Program.cs 맨 위에 다음 지시문을 추가합니다.  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Northwind 코드 파일을 프로젝트에 추가  
 이 단계에서는 SQLMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다. 자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>northwind 코드 파일을 프로젝트에 추가하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**합니다.  
  
2.  에 **기존 항목 추가** 대화 상자에서 c:\linqtest6\northwind.cs로 이동한 다음 **추가**합니다.  
  
     northwind.cs 파일이 프로젝트에 추가됩니다.  
  
## <a name="setting-up-the-database-connection"></a>데이터베이스 연결 설정  
 먼저 데이터베이스에 대한 연결을 테스트합니다. 특히 데이터베이스 이름 Northwnd에 i 문자가 없는 것을 확인합니다. 다음 단계에서 오류를 생성하는 경우 northwind.cs 파일을 검토하여 Northwind partial 클래스의 맞춤법을 확인합니다.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>데이터베이스 연결을 설정하고 테스트하려면  
  
1.  Program 클래스의 `Main` 메서드에 다음 코드를 입력하거나 붙여넣습니다.  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2.  이때 F5 키를 눌러 응용 프로그램을 테스트합니다.  
  
     A **콘솔** 창이 열립니다.  
  
     Enter 키를 눌러 응용 프로그램을 닫을 수 있습니다는 **콘솔** 창을 클릭 하 여 **디버깅 중지** 에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **디버그** 메뉴.  
  
## <a name="creating-a-new-entity"></a>새 엔터티 만들기  
 새 엔터티를 만드는 과정은 단순합니다. `Customer` 키워드를 사용하여 개체(예: `new`)를 만들 수 있습니다.  
  
 이 단원과 다음 단원에서는 로컬 캐시만 변경합니다. 이 연습의 끝에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때까지 변경 내용이 데이터베이스로 전송되지 않습니다.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>새 Customer 엔터티 개체를 추가하려면  
  
1.  `Customer` 메서드의 `Console.ReadLine();` 앞에 다음 코드를 추가하여 새 `Main`를 만듭니다.  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2.  F5 키를 눌러 솔루션을 디버깅합니다.  
  
3.  Enter 키를 **콘솔** 창 디버깅을 중지 하 고 연습을 계속 합니다.  
  
## <a name="updating-an-entity"></a>엔터티 업데이트  
 다음 단계에서는 `Customer` 개체를 검색하고 해당 속성 중 하나를 수정합니다.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Customer 이름을 변경하려면  
  
-   `Console.ReadLine();` 위에 다음 코드를 추가합니다.  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a>엔터티 삭제  
 동일한 Customer 개체를 사용하여 첫 번째 주문을 삭제할 수 있습니다.  
  
 다음 코드에서는 행 간의 관계를 끊는 방법과 데이터베이스에서 행을 삭제하는 방법을 보여 줍니다. `Console.ReadLine` 앞에 다음 코드를 추가하여 개체 삭제 방법을 확인합니다.  
  
#### <a name="to-delete-a-row"></a>행을 삭제하려면  
  
-   `Console.ReadLine();` 바로 위에 다음 코드를 추가합니다.  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a>변경 내용을 데이터베이스로 전송  
 개체를 만들고 업데이트 및 삭제하는 데 필요한 첫 번째 단계는 실제로 변경 내용을 데이터베이스로 전송하는 것입니다. 이 단계를 수행하지 않으면 변경 내용은 로컬에만 적용되고 쿼리 결과에 나타나지 않습니다.  
  
#### <a name="to-submit-changes-to-the-database"></a>변경 내용을 데이터베이스로 전송하려면  
  
1.  `Console.ReadLine` 바로 위에 다음 코드를 삽입합니다.  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2.  `SubmitChanges` 뒤에 다음 코드를 삽입하여 변경 내용 전송 전후의 결과를 보여 줍니다.  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3.  F5 키를 눌러 솔루션을 디버깅합니다.  
  
4.  Enter 키를 **콘솔** 응용 프로그램을 닫으려면 창.  
  
> [!NOTE]
>  변경 내용을 전송하여 새 고객을 추가한 후에는 이 솔루션을 있는 그대로 다시 실행할 수 없습니다. 솔루션을 다시 실행하려면 추가할 고객의 이름과 고객 ID를 변경합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
