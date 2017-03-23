---
title: "방법: LINQ (Visual Basic)를 사용 하 여 저장된 프로시저를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: abc3970fc5ab6f4a2f4b67b5efa2b19afb07337b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)
언어 통합 쿼리 (LINQ) 쉽게 데이터베이스 개체와 같은 저장 프로시저를 포함 하 여 데이터베이스 정보에 액세스할 수 있습니다.  
  
 다음 예제에는 SQL Server 데이터베이스의 저장된 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다. 데이터베이스에 두 개의 다른 저장된 프로시저를 호출 하는 방법을 보여 줍니다. 각 프로시저는 쿼리 결과 반환합니다. 입력된 매개 변수를 사용 하는 하나의 절차 및 다른 프로시저 매개 변수를 사용 하지 않습니다.  
  
 이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다. 개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 있습니다에서 다운로드할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다. 자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 연결을 만들려면  
  
1.  Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.  
  
2.  마우스 오른쪽 단추로 클릭 **데이터 연결** 에서 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.  
  
3.  Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다. Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. 선택 된 **LINQ to SQL 클래스** 항목 템플릿.  
  
3.  파일 이름을 `northwind.dbml`합니다. **추가**를 클릭합니다. 개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>저장된 프로시저를 O/R 디자이너에 추가 하려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다. 확장 된 **저장 프로시저** 폴더입니다.  
  
     O/R 디자이너를 닫은 경우 앞에 추가 되는 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2.  클릭 된 **연도별 매출** 저장 프로시저 및 디자이너의 오른쪽 창으로 끕니다. 클릭 하 고 **Ten Most Expensive Products** 저장된 프로시저는 디자이너의 오른쪽 창으로 끕니다.  
  
3.  변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>저장된 프로시저의 결과 표시 하는 코드를 추가 하려면  
  
1.  **도구 상자**, 끌어는 <xref:System.Windows.Forms.DataGridView>Form1 프로젝트에 대 한 기본 Windows Form 컨트롤을.</xref:System.Windows.Forms.DataGridView>  
  
2.  Form1 코드를 추가 하려면 두 번 클릭 하 여 `Load` 이벤트입니다.  
  
3.  디자이너에 추가 된 저장된 프로시저를 O/R 디자이너를 추가한 경우는 <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext> 이 개체는 해당 프로시저에 액세스 해야 하는 코드를 포함 합니다. <xref:System.Data.Linq.DataContext>.dbml 파일의 이름에 따라 프로젝트에 대해 개체.</xref:System.Data.Linq.DataContext> 이 프로젝트는 <xref:System.Data.Linq.DataContext>개체의 이름은 `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext>O/R 디자이너에서 지정 된 저장된 프로시저 메서드에서 코드를 호출 합니다.</xref:System.Data.Linq.DataContext> 에 바인딩하는 <xref:System.Windows.Forms.DataGridView>개체를 호출 하 여 즉시 실행 하도록 할 수는 <xref:System.Linq.Enumerable.ToList%2A>메서드는 저장된 프로시저의 결과를.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView>  
  
     다음 코드를 추가 하는 `Load` 데이터 컨텍스트에 대 한 메서드로 노출 하는 저장된 프로시저 중 하나를 호출 하는 이벤트입니다.  
  
     [!code-vb[VbLINQtoSQLHowTos #&1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos #&2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [DataContext 메서드 (O/R 디자이너)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)

