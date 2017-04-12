---
title: "방법: LINQ (Visual Basic)를 사용 하 여 데이터베이스의 데이터 수정 | Microsoft 문서"
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
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 44ca3e44d8411a6329d176eb778677bfab2b365c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 데이터베이스의 데이터 수정(Visual Basic)
언어 통합 쿼리 (LINQ) 쿼리를 사용 하면 쉽게 데이터베이스 정보를 액세스 하 고 데이터베이스의 값을 수정할 수 있도록 합니다.  
  
 다음 예제에서는 SQL Server 데이터베이스에서 검색 하는 새 응용 프로그램을 만드는 방법 및 업데이트 정보를 보여 줍니다.  
  
 이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다. 개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 있습니다에서 다운로드할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다. 자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 연결을 만들려면  
  
1.  Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여는 **보기** 메뉴를 선택한 다음 선택 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **데이터 연결** 에서 **서버 탐색기**/**데이터베이스 탐색기**를 클릭 하 고 **연결 추가**합니다.  
  
3.  Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>SQL 파일에는 LINQ 사용 하 여 프로젝트를 추가 하려면  
  
1.  Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다. Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. 선택 된 **LINQ to SQL 클래스** 항목 템플릿.  
  
3.  파일 이름을 `northwind.dbml`합니다. **추가**를 클릭합니다. 개체 관계형 디자이너 (O/R 디자이너)에 대 한 열은 `northwind.dbml` 파일입니다.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>쿼리 디자이너를 수정 하는 테이블을 추가 하려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다. 확장 된 **테이블** 폴더입니다.  
  
     O/R 디자이너를 닫은 경우 있습니다 다시 열 수를 두 번 클릭 하 여는 `northwind.dbml` 이전에 추가한 파일입니다.  
  
2.  Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.  
  
     디자이너는 프로젝트에 대 한 새 Customer 개체를 만듭니다.  
  
3.  변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>데이터베이스를 수정 하 고 결과 표시 하는 코드를 추가 하려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.DataGridView>Form1 프로젝트에 대 한 기본 Windows Form 컨트롤을.</xref:System.Windows.Forms.DataGridView>  
  
2.  O/R 디자이너에 테이블을 추가한 경우 디자이너 추가 <xref:System.Data.Linq.DataContext>프로젝트에는 개체입니다.</xref:System.Data.Linq.DataContext> 이 개체에는 Customers 테이블에 액세스 하는 데 사용할 수 있는 코드가 포함 됩니다. 또한 로컬 고객 개체는 테이블에 대 한 Customers 컬렉션을 정의 하는 코드를 포함 합니다. <xref:System.Data.Linq.DataContext>.dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext> 이 프로젝트는 <xref:System.Data.Linq.DataContext>개체의 이름은 `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext>코드의 쿼리 개체를 O/R 디자이너에서 지정 된 고객 컬렉션을 수정 합니다.</xref:System.Data.Linq.DataContext> 호출 하 여 제출 하기 전에 Customers 컬렉션에 수행한 변경 내용을 데이터베이스에 반영 되지 않습니다는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>의 메서드는 <xref:System.Data.Linq.DataContext>개체.</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A>  
  
     Windows Form Form1 코드 추가 하는 <xref:System.Windows.Forms.Form.Load> <xref:System.Data.Linq.DataContext>.</xref:System.Data.Linq.DataContext> 의 속성으로 노출 되는 Customers 테이블을 쿼리 하는 이벤트</xref:System.Windows.Forms.Form.Load> 를 두 번 클릭 다음 코드를 추가합니다.  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  **도구 상자**, 세 개의 끌어 <xref:System.Windows.Forms.Button>컨트롤을 폼에.</xref:System.Windows.Forms.Button> 첫 번째 선택 `Button` 제어 합니다. 에 **속성** 창의 설정의 `Name` 의 `Button` 컨트롤을 `AddButton` 및 `Text` 를 `Add`합니다. 두 번째 단추를 선택 하 고 설정 된 `Name` 속성을 `UpdateButton` 및 `Text` 속성을 `Update`합니다. 세 번째 단추를 선택 하 고 설정 된 `Name` 속성을 `DeleteButton` 및 `Text` 속성을 `Delete`합니다.  
  
4.  두 번 클릭은 **추가** 단추 코드를 추가 하려면 해당 `Click` 이벤트입니다. 다음 코드를 추가합니다.  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  두 번 클릭은 **업데이트** 단추 코드를 추가 하려면 해당 `Click` 이벤트입니다. 다음 코드를 추가합니다.  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  두 번 클릭은 **삭제** 단추 코드를 추가 하려면 해당 `Click` 이벤트입니다. 다음 코드를 추가합니다.  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  F5 키를 눌러 프로젝트를 실행합니다. 클릭 **추가** 새 레코드를 추가 합니다. 클릭 **업데이트** 새 레코드를 수정 합니다. 클릭 **삭제** 새 레코드를 삭제 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [DataContext 메서드 (O/R 디자이너)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
