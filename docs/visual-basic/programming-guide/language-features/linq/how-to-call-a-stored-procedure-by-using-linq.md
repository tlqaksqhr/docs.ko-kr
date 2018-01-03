---
title: "방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bb7b970d42a44ad925883b7a935aae386b1f1d5
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)
통합 언어 쿼리 (LINQ) 쉽게 데이터베이스 개체와 같은 저장 프로시저를 포함 하 여 데이터베이스 정보에 액세스할 수 있습니다.  
  
 다음 예제에는 SQL Server 데이터베이스의 저장된 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다. 샘플은 데이터베이스에 두 개의 다른 저장된 프로시저를 호출 하는 방법을 보여 줍니다. 각 프로시저 쿼리의 결과 반환합니다. 하나의 프로시저 입력된 매개 변수를 사용 하 고 다른 프로시저 매개 변수를 사용 하지 않는 합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다. 개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우에서 다운로드할 수 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다. 자세한 내용은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 연결을 만들려면  
  
1.  Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.  
  
2.  마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.  
  
3.  Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다. Visual basic **Windows Forms 응용 프로그램** 프로젝트 형식으로.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. 선택 된 **LINQ to SQL 클래스** 항목 템플릿을 합니다.  
  
3.  파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. 개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>저장된 프로시저를 O/R 디자이너에 추가 하려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다. 확장 된 **Stored Procedures** 폴더입니다.  
  
     O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일이 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2.  클릭는 **연도별 매출** 저장 프로시저를 디자이너의 오른쪽 창으로 끕니다. 클릭는 **10 개의 가장 비싼 제품** 저장된 프로시저는 디자이너의 오른쪽 창으로 끕니다.  
  
3.  변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>저장된 프로시저의 결과 표시 하는 코드를 추가 하려면  
  
1.  **도구 상자**를 끌어는 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.  
  
2.  Form1 코드를 추가 하려면 두 번 클릭 해당 `Load` 이벤트입니다.  
  
3.  디자이너에 추가 된 저장된 프로시저를 O/R 디자이너에 추가 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체입니다. 이 개체는 해당 프로시저에 액세스 해야 하는 코드를 포함 합니다. <xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트 이름은 대 한 개체입니다. 이 프로젝트는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.  
  
     인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 지정 O/R 디자이너에서 저장된 프로시저 메서드에서 코드를 호출 합니다. 바인딩할는 <xref:System.Windows.Forms.DataGridView> 개체 쿼리를 호출 하 여 즉시 실행 해야 할 수 있습니다는 <xref:System.Linq.Enumerable.ToList%2A> 메서드 저장된 프로시저의 결과를 합니다.  
  
     다음 코드를 추가 하 고 `Load` 데이터 컨텍스트에 대 한 메서드로 노출 된 저장된 프로시저 중 하나를 호출 하는 이벤트입니다.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
