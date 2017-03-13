---
title: "How to: Call a Stored Procedure by Using LINQ (Visual Basic) | Microsoft Docs"
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
  - "queries [LINQ in Visual Basic], stored procedure calls"
  - "stored procedures sample [Visual Basic]"
  - "stored procedures [LINQ to SQL]"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Call a Stored Procedure by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

LINQ\(통합 언어 쿼리\)는 저장 프로시저와 같은 데이터베이스 개체를 비롯하여 데이터베이스 정보에 쉽게 액세스할 수 있습니다.  
  
 다음 예제에서는 SQL Server 데이터베이스의 저장 프로시저를 호출하는 응용 프로그램을 만드는 방법을 보여 줍니다.  샘플에서는 데이터베이스에서 두 개의 다른 저장 프로시저를 호출하는 방법을 보여 줍니다.  각 프로시저는 쿼리의 결과를 반환합니다.  한 프로시저는 입력 매개 변수를 사용하며 다른 프로시저는 매개 변수를 사용하지 않습니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.  개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트에서 다운로드할 수 있습니다.  자세한 내용은 [샘플 데이터베이스 다운로드](../Topic/Downloading%20Sample%20Databases.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 데이터베이스에 대한 연결을 만들려면  
  
1.  Visual Studio의 **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 클릭하여 **서버 탐색기**\/**데이터베이스 탐색기**를 엽니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**을 마우스 오른쪽 단추로 클릭한 다음 **연결 추가**를 클릭합니다.  
  
3.  Northwind 샘플 데이터베이스에 대한 유효한 연결을 지정합니다.  
  
### LINQ to SQL 파일이 포함된 프로젝트를 추가하려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  Visual Basic **Windows Forms 응용 프로그램**을 프로젝트 형식으로 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  **LINQ to SQL 클래스** 항목 템플릿을 선택합니다.  
  
3.  파일 이름을 `northwind.dbml`로 지정합니다.  **추가**를 클릭합니다.  northwind.dbml 파일에 대한 O\/R 디자이너\(개체 관계형 디자이너\)가 열립니다.  
  
### 저장 프로시저를 O\/R 디자이너에 추가하려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대한 연결을 확장합니다.  **저장 프로시저** 폴더를 확장합니다.  
  
     O\/R 디자이너를 닫은 경우에는 앞서 추가한 northwind.dbml 파일을 두 번 클릭하여 다시 열 수 있습니다.  
  
2.  **Sales by Year** 저장 프로시저를 클릭하여 디자이너의 오른쪽 창으로 끌어 옵니다.  **Ten Most Expensive Products** 저장 프로시저를 클릭하여 디자이너의 오른쪽 창으로 끌어 옵니다.  
  
3.  변경 내용을 저장한 다음 디자이너를 닫습니다.  
  
4.  프로젝트를 저장합니다.  
  
### 코드를 추가하여 저장 프로시저의 결과를 표시하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows Form인 Form1로 끌어 옵니다.  
  
2.  Form1을 두 번 클릭하여 폼의 `Load` 이벤트에 코드를 추가합니다.  
  
3.  O\/R 디자이너에 저장 프로시저를 추가한 경우 디자이너는 프로젝트의 <xref:System.Data.Linq.DataContext> 개체를 추가한 것입니다.  이 개체에는 해당 프로시저에 액세스해야 하는 코드가 포함됩니다.  프로젝트에 대한 <xref:System.Data.Linq.DataContext> 개체의 이름은 .dbml 파일 이름을 기반으로 지정됩니다.  이 프로젝트에서 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.  
  
     코드에서 <xref:System.Data.Linq.DataContext>의 인스턴스를 만든 다음 O\/R 디자이너로 지정된 저장 프로시저 메서드를 쿼리할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 개체에 바인딩하려면 저장 프로시저의 결과에서 <xref:System.Linq.Enumerable.ToList%2A> 메서드를 호출하여 쿼리가 강제로 바로 실행되도록 할 수 있습니다.  
  
     다음 코드를 `Load` 이벤트에 추가하여 데이터 컨텍스트에 대한 메서드로 노출된 저장 프로시저 중 하나를 호출합니다.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  F5 키를 눌러 프로젝트를 실행하고 결과를 봅니다.  
  
## 참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext 메서드\(O\/R 디자이너\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)