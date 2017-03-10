---
title: "How to: Modify Data in a Database by Using LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inserting rows [LINQ to SQL]"
  - "deleting rows [LINQ to SQL]"
  - "updating rows [LINQ to SQL]"
  - "inserting data [Visual Basic]"
  - "deleting data"
  - "data [Visual Basic], updating"
  - "updating data [LINQ]"
  - "queries [LINQ in Visual Basic], data changes in database"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Modify Data in a Database by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

LINQ\(통합 언어 쿼리\) 쿼리를 사용하면 손쉽게 데이터베이스 정보에 액세스하고 데이터베이스의 값을 수정할 수 있습니다.  
  
 다음 예제에서는 SQL Server 데이터베이스의 정보를 검색하고 업데이트하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.  개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트에서 다운로드할 수 있습니다.  자세한 내용은 [샘플 데이터베이스 다운로드](../Topic/Downloading%20Sample%20Databases.md)를 참조하십시오.  
  
### 데이터베이스에 대한 연결을 만들려면  
  
1.  Visual Studio의 **보기** 메뉴를 클릭한 다음 **서버 탐색기**\/**데이터베이스 탐색기**를 선택하여 **서버 탐색기**\/**데이터베이스 탐색기**를 엽니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**을 마우스 오른쪽 단추로 클릭하고 **연결 추가**를 클릭합니다.  
  
3.  Northwind 샘플 데이터베이스에 대한 유효한 연결을 지정합니다.  
  
### 프로젝트에 LINQ to SQL 파일을 추가하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  Visual Basic **Windows Forms 응용 프로그램**을 프로젝트 형식으로 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  **LINQ to SQL 클래스** 항목 템플릿을 선택합니다.  
  
3.  파일 이름을 `northwind.dbml`로 지정합니다.  **추가**를 클릭합니다.  `northwind.dbml` 파일에 대한 O\/R 디자이너\(개체 관계형 디자이너\)가 열립니다.  
  
### 쿼리 및 수정할 테이블을 디자이너에 추가하려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대한 연결을 확장합니다.  **테이블** 폴더를 확장합니다.  
  
     O\/R 디자이너를 닫은 경우에는 앞서 추가한 `northwind.dbml` 파일을 두 번 클릭하여 다시 열 수 있습니다.  
  
2.  Customers 테이블을 클릭하여 디자이너의 왼쪽 창으로 끌어 옵니다.  
  
     디자이너에서 프로젝트에 대한 새 Customer 개체를 만듭니다.  
  
3.  변경 내용을 저장한 다음 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### 데이터베이스를 수정하여 결과를 표시하는 코드를 추가하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows Form인 Form1로 끌어 옵니다.  
  
2.  O\/R 디자이너에 테이블을 추가한 경우 디자이너는 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가한 것입니다.  이 개체에는 Customers 테이블에 액세스하는 데 사용할 수 있는 코드가 포함되어 있습니다.  또한 이 개체에는 테이블의 로컬 Customer 개체 및 Customers 컬렉션을 정의하는 코드가 포함되어 있습니다.  프로젝트에 대한 <xref:System.Data.Linq.DataContext> 개체의 이름은 .dbml 파일 이름을 기반으로 지정됩니다.  이 프로젝트에서 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.  
  
     코드에서 <xref:System.Data.Linq.DataContext> 개체의 인스턴스를 만들어 O\/R 디자이너에서 지정한 Customers 컬렉션을 쿼리하고 수정할 수 있습니다.  Customers 컬렉션에 대한 변경 내용은 <xref:System.Data.Linq.DataContext> 개체의 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드를 호출하여 해당 변경 내용을 전송하기 전까지는 데이터베이스에 반영되지 않습니다.  
  
     Windows Form인 Form1을 두 번 클릭하여 사용자의 <xref:System.Data.Linq.DataContext> 속성으로 노출되는 Customers 테이블을 쿼리하려면 코드를 <xref:System.Windows.Forms.Form.Load> 이벤트에 추가합니다.  아래와 같은 코드를 추가합니다.  
  
    ```vb#  
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
  
3.  **도구 상자**에서 세 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼으로 끌어 옵니다.  첫 번째 `Button` 컨트롤을 선택합니다.  **속성** 창에서 `Button` 컨트롤의 `Name`은 `AddButton`으로 설정하고 `Text`는 `추가`로 설정합니다.  두 번째 단추를 선택하여 `Name` 속성은 `UpdateButton`으로 설정하고 `Text` 속성은 `업데이트`로 설정합니다.  세 번째 단추를 선택하여 `Name` 속성은 `DeleteButton`으로 설정하고 `Text` 속성은 `삭제`로 설정합니다.  
  
4.  **추가** 단추를 두 번 클릭하여 코드를 해당 `Click` 이벤트에 추가합니다.  아래와 같은 코드를 추가합니다.  
  
    ```vb#  
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
  
5.  **업데이트** 단추를 두 번 클릭하여 코드를 해당 `Click` 이벤트에 추가합니다.  아래와 같은 코드를 추가합니다.  
  
    ```vb#  
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
  
6.  **삭제** 단추를 두 번 클릭하여 코드를 해당 `Click` 이벤트에 추가합니다.  아래와 같은 코드를 추가합니다.  
  
    ```vb#  
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
  
7.  F5 키를 눌러 프로젝트를 실행합니다.  **추가**를 클릭하여 새 레코드를 추가합니다.  **업데이트**를 클릭하여 새 레코드를 수정합니다.  **삭제**를 클릭하여 새 레코드를 삭제합니다.  
  
## 참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext 메서드\(O\/R 디자이너\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)