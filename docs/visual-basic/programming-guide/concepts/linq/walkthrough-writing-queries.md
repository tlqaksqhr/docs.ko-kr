---
title: "연습: Visual Basic에서 쿼리 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "쿼리[Visual Basic의 LINQ], 작성"
  - "LINQ[Visual Basic], 연습"
  - "LINQ[Visual Basic], 쿼리 작성"
  - "LINQ 쿼리 작성[Visual Basic]"
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 68
---
# 연습: Visual Basic에서 쿼리 작성
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 Visual Basic 언어 기능을 사용하여 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] 쿼리 식을 작성하는 방법을 보여 줍니다.  이 연습에서는 Student 개체 목록에 대한 쿼리를 만들어 실행하고 수정하는 방법을 보여 줍니다.  이 쿼리는 개체 이니셜라이저, 로컬 형식 유추 및 익명 형식을 비롯하여 Visual Basic 2008에 새로 제공된 여러 기능을 통합합니다.  
  
 이 연습을 마치고 나면 원하는 특정 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자에 대한 샘플과 설명서를 진행해도 좋습니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자에는 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)] 및 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]이 포함됩니다.  
  
## 프로젝트 만들기  
  
#### 콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **설치된 템플릿** 목록에서 **Visual Basic**을 클릭합니다.  
  
4.  프로젝트 형식 목록에서 **콘솔 응용 프로그램**을 클릭합니다.  **이름** 상자에 프로젝트의 이름을 입력한 다음 **확인**을 클릭합니다.  
  
     프로젝트가 만들어집니다.  기본적으로 System.Core.dll에 대한 참조가 포함됩니다.  또한 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)의 **가져온 네임스페이스** 목록에는 <xref:System.Linq?displayProperty=fullName> 네임스페이스가 포함됩니다.  
  
5.  에 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), 되도록  **Option infer** 로 설정 된  **의**.  
  
## 메모리 내 데이터 소스 추가  
 이 연습에서 쿼리의 데이터 소스는 `Student` 개체 목록입니다.  각 `Student` 개체는 이름, 성, 학년 및 전교 등수를 포함합니다.  
  
#### 데이터 소스를 추가하려면  
  
-   `Student` 클래스를 정의하고 이 클래스의 인스턴스 목록을 만듭니다.  
  
    > [!IMPORTANT]
    >  연습 예제에서 사용된 목록을 만들고 `Student` 클래스를 정의하는 데 필요한 코드는 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 제공됩니다.  이 코드를 복사하여 프로젝트에 붙여넣을 수 있습니다.  프로젝트를 만들 때 표시된 코드는 새 코드로 대체됩니다.  
  
#### 새 학생을 학생 목록에 추가하려면  
  
-   `getStudents` 메서드의 패턴에 따라 `Student` 클래스의 다른 인스턴스를 목록에 추가합니다.  학생을 추가하면 개체 이니셜라이저로 이동하게 됩니다.  자세한 내용은 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조하십시오.  
  
## 쿼리 만들기  
 이 섹션에서 추가된 쿼리는 실행될 경우 등수가 10등 안에 드는 학생 목록을 생성합니다.  쿼리가 매번 완전한 `Student` 개체를 선택하기 때문에 쿼리 결과의 형식은 `IEnumerable(Of Student)`입니다.  그러나 쿼리의 형식은 일반적으로 쿼리 정의에 지정되지 않습니다.  대신에 컴파일러는 로컬 형식 유추를 사용하여 형식을 결정합니다.  자세한 내용은 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)을 참조하십시오.  쿼리의 범위 변수인 `currentStudent`는 소스인 `students`의 각 `Student`에 대한 참조로 사용되어 `students`의 각 개체에 대한 속성에 액세스할 수 있게 합니다.  
  
#### 단순 쿼리를 만들려면  
  
1.  프로젝트의 `Main` 메서드에서 다음과 같이 표시된 위치를 찾습니다.  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     다음 코드를 복사하여 붙여넣습니다.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  코드에서 `studentQuery` 위에 마우스 포인터를 놓고 컴파일러에서 할당한 형식이 `IEnumerable(Of Student)`인지 확인합니다.  
  
## 쿼리 실행  
 `studentQuery` 변수는 쿼리 실행 결과가 아니라 쿼리 정의를 포함합니다.  쿼리를 실행하기 위한 일반적인 메커니즘은 `For Each` 루프입니다.  반환된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스합니다.  쿼리 실행에 대한 자세한 내용은 [LINQ 쿼리 처음 작성](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조하십시오.  
  
#### 쿼리를 실행하려면  
  
1.  프로젝트의 쿼리 아래에 다음 `For Each` 루프를 추가합니다.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  루프 컨트롤 변수 `studentRecord` 위로 마우스 포인터를 이동하여 해당 데이터 형식을 표시합니다.  `studentQuery`가 `Student` 인스턴스의 컬렉션을 반환하므로 `studentRecord`의 형식은 `Student`로 유추됩니다.  
  
3.  Ctrl\+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.  콘솔 창의 결과를 확인합니다.  
  
## 쿼리 수정  
 쿼리 결과는 지정된 순서로 되어 있는 경우 더 쉽게 검색할 수 있습니다.  사용할 수 있는 모든 필드에 기초하여 반환된 시퀀스를 정렬할 수 있습니다.  
  
#### 결과의 순서를 지정하려면  
  
1.  쿼리의 `Where` 문과 `Select` 문 사이에 다음 `Order By` 절을 추가합니다.  `Order By` 절은 각 학생의 성에 따라 사전순으로 A부터 Z까지 결과의 순서를 지정합니다.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  성과 이름별로 차례로 순서를 지정하려면 두 필드를 쿼리에 모두 추가합니다.  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     Z에서 A로 순서를 지정하기 위해 `Descending`을 지정할 수도 있습니다.  
  
3.  Ctrl\+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.  콘솔 창의 결과를 확인합니다.  
  
#### 로컬 식별자를 제공하려면  
  
1.  이 섹션의 코드를 추가하여 쿼리 식에 로컬 식별자를 제공합니다.  로컬 식별자는 중간 결과를 보유합니다.  다음 예제에서 `name`은 학생의 이름과 성 연결을 보유하는 식별자입니다.  로컬 식별자는 편의상 사용할 수도 있고 여러 번 계산해야 하는 식의 결과를 저장하여 성능을 향상시킬 수도 있습니다.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Ctrl\+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.  콘솔 창의 결과를 확인합니다.  
  
#### Select 절에서 하나의 필드를 반환하려면  
  
1.  이 섹션의 쿼리와 `For Each` 루프를 추가하여 해당 요소가 소스의 요소와 다른 시퀀스를 생성하는 쿼리를 만듭니다.  다음 예제에서 소스는 `Student` 개체의 컬렉션이지만 각 개체의 한 멤버, 즉 성이 Garcia인 학생의 이름만 반환됩니다.  `currentStudent.First`가 문자열이므로 `studentQuery3`에 의해 반환된 시퀀스의 데이터 형식은 문자열 시퀀스인 `IEnumerable(Of String)`입니다.  앞에 예제와 같이 `studentQuery3`의 데이터 형식 할당은 컴파일러에서 로컬 형식 유추를 사용하여 결정합니다.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  코드에서 `studentQuery3` 위에 마우스 포인터를 놓고 할당된 형식이 `IEnumerable(Of String)`인지 확인합니다.  
  
3.  Ctrl\+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.  콘솔 창의 결과를 확인합니다.  
  
#### Select 절에서 익명 형식을 만들려면  
  
1.  이 섹션의 코드를 추가하여 쿼리에서 익명 형식이 사용되는 방법을 확인합니다.  완전한 레코드\(이전 예제의 `currentStudent` 레코드\) 또는 단일 필드\(이전 섹션의 `First`\) 대신에 데이터 소스의 여러 필드를 반환하려면 쿼리에서 익명 형식을 사용합니다.  결과에 포함할 필드가 들어 있는 새 명명 된 형식을 정의 하는 대신 필드에 지정 된 `Select` 절 컴파일러 만들고 익명 형식 속성으로 해당 필드를. 자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  
  
     다음 예제는 등수에 따라 1등에서 10등 사이에 있는 상급생의 이름과 등수를 반환하는 쿼리를 만듭니다.  이 예제에서 `Select` 절이 익명 형식의 인스턴스를 반환하고 사용할 수 있는 이름이 익명 형식에 없으므로 `studentQuery4`의 형식이 유추되어야 합니다.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Ctrl\+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.  콘솔 창의 결과를 확인합니다.  
  
## 추가 예제  
 이제 기본 사항을 이해했으므로 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리의 유연성과 강력한 기능을 보여 주는 다음 목록의 추가 예제를 볼 수 있습니다.  각 예제에는 해당 예제의 기능에 대한 간략한 설명이 앞에 옵니다.  유추 된 형식은 보려면 각 쿼리에 대 한 쿼리 결과 변수 위에 마우스 포인터를 놓습니다. 사용 된 `For Each` 결과 생성 하는 루프.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## 추가 정보  
 쿼리를 다루는 데 필요한 기본적인 개념을 숙지했다면 이제 각자 원하는 특정 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자 형식에 대한 설명서와 샘플을 읽어도 좋습니다.  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
## 참고 항목  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)