---
title: "Walkthrough: Writing Queries in C# (LINQ) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], walkthroughs"
  - "LINQ [C#], writing queries"
  - "queries [LINQ in C#], writing"
  - "writing LINQ queries"
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Walkthrough: Writing Queries in C# (LINQ)
이 연습에서는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 식을 작성하는 데 사용되는 C\# 언어 기능을 보여 줍니다.  이 연습을 마치고 나면 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] to DataSet 또는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]과 같은 원하는 특정 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자에 대한 샘플과 설명서를 진행할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습에서는 Visual Studio 2008에 도입 된 기능이 필요 합니다.  
  
 ![비디오에 링크](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") 이 항목의 비디오 버전을 보려면 [Video How to: Writing Queries in C\# \(LINQ\)](http://go.microsoft.com/fwlink/?LinkId=100393)을 참조하십시오.  
  
## C\# 프로젝트 만들기  
  
#### 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  확장  **설치 된**, 확장  **템플릿**, 확장  **C\#**, 다음을 선택 하 고  **콘솔 응용 프로그램**.  
  
4.  에  **이름** 텍스트 상자 다른 이름을 입력 하거나 기본 이름을 적용 및 다음 선택은  **확인** 단추.  
  
     **솔루션 탐색기**에 새 프로젝트가 나타납니다.  
  
5.  프로젝트에는 System.Core.dll에 대한 참조 및 <xref:System.Linq?displayProperty=fullName> 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
## 메모리 내 데이터 소스 만들기  
 쿼리의 데이터 소스는 간단한 `Student` 개체 목록입니다.  각 `Student` 레코드는 이름, 성 및 클래스에서의 테스트 점수를 나타내는 정수 배열을 포함합니다.  프로젝트에 이 코드를 복사합니다.  다음 특성에 주의합니다.  
  
-   `Student` 클래스는 자동 구현된 속성으로 구성됩니다.  
  
-   목록의 각 학생은 개체 이니셜라이저를 사용하여 초기화됩니다.  
  
-   목록 자체는 컬렉션 이니셜라이저를 사용하여 초기화됩니다.  
  
 이 전체 데이터 구조는 명시적 멤버 액세스나 생성자에 대한 명시적 호출 없이 초기화 및 인스턴스화됩니다.  이러한 새로운 기능에 대한 자세한 내용은 [자동으로 구현된 속성](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하십시오.  
  
#### 데이터 소스를 추가하려면  
  
-   `Student` 클래스와 학생의 초기화된 목록을 프로젝트의 `Program` 클래스에 추가합니다.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#11)]  
  
#### 새 학생을 학생 목록에 추가하려면  
  
1.  새 `Student`를 `Students` 목록에 추가하고 원하는 이름과 테스트 점수를 사용합니다.  개체 이니셜라이저의 구문을 더 잘 배울 수 있도록 새 학생 정보를 모두 직접 입력해 봅니다.  
  
## 쿼리 만들기  
  
#### 단순 쿼리를 만들려면  
  
-   응용 프로그램의 `Main` 메서드에서 첫 번째 테스트의 점수가 90점을 넘는 모든 학생의 목록을 실행 시에 생성하는 간단한 쿼리를 만듭니다.  전체 `Student` 개체가 선택되어 있으므로 쿼리의 형식은 `IEnumerable<Student>`입니다.  [var](../../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 코드에서 암시적 형식 지정을 사용할 수도 있지만 결과를 더 분명하게 나타내기 위해 명시적 형식 지정이 사용됩니다.  `var`에 대한 자세한 내용은 [암시적으로 형식화한 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을 참조하십시오.  
  
     또한 쿼리의 범위 변수인 `student`가 소스의 각 `Student`에 대한 참조로 사용되어 각 개체에 대한 멤버 액세스를 제공한다는 것에 주의합니다.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#12)]  
  
## 쿼리 실행  
  
#### 쿼리를 실행하려면  
  
1.  이제 쿼리를 실행하게 만드는 `foreach` 루프를 작성합니다.  코드에 대한 다음 사항에 주의합니다.  
  
    -   반환된 시퀀스의 각 요소는 `foreach` 루프에서 반복 변수를 통해 액세스합니다.  
  
    -   이 변수의 형식은 `Student`이고 쿼리 변수의 형식은 호환되는 `IEnumerable<Student>`입니다.  
  
2.  이 코드를 추가한 후 Ctrl \+ F5를 눌러 응용 프로그램을 빌드 및 실행하여 **콘솔** 창에서 결과를 봅니다.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#13)]  
  
#### 다른 필터 조건을 추가하려면  
  
1.  쿼리를 더 구체화하기 위해 `where` 절에서 여러 부울 조건을 결합할 수 있습니다.  다음 코드는 첫 번째 점수가 90점을 넘고 마지막 점수가 80점 미만인 학생을 쿼리에서 반환하도록 조건을 추가합니다.  `where` 절은 다음 코드와 유사해야 합니다.  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하십시오.  
  
## 쿼리 수정  
  
#### 결과의 순서를 지정하려면  
  
1.  결과가 일정한 순서로 되어 있을 경우 결과를 더 쉽게 검색할 수 있습니다.  소스 요소의 액세스 가능한 임의 필드별로 반환된 시퀀스의 순서를 지정할 수 있습니다.  예를 들어 다음 `orderby` 절은 각 학생의 성에 따라 사전순으로 A부터 Z까지 결과의 순서를 지정합니다.  다음 `orderby` 절을 쿼리에서 `where` 문 바로 뒤 및 `select` 문 앞에 추가합니다.  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  이제 첫 번째 테스트의 점수에 따라 최고 점수부터 최하 점수까지 역순으로 결과의 순서를 지정하도록 `orderby` 절을 변경합니다.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  점수를 볼 수 있도록 `WriteLine` 형식 문자열을 변경합니다.  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하십시오.  
  
#### 결과를 그룹화하려면  
  
1.  그룹화는 쿼리 식의 강력한 기능입니다.  group 절이 있는 쿼리는 그룹 시퀀스를 생성하고 각 그룹 자체는 `Key`와 해당 그룹의 모든 멤버로 구성된 시퀀스를 포함합니다.  다음 새 쿼리는 성의 첫 글자를 키로 사용하여 학생을 그룹화합니다.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#14)]  
  
2.  이제 쿼리 형식이 변경되었다는 것에 주의합니다.  `char` 형식을 키로 포함하고 시퀀스와 `Student` 개체 시퀀스를 포함하는 그룹 시퀀스가 생성됩니다.  쿼리 형식이 변경되었으므로 다음 코드에서는 또한 `foreach` 실행 루프가 변경됩니다.  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#15)]  
  
3.  Ctrl \+ F5를 눌러 응용 프로그램을 실행하고 **콘솔** 창에서 결과를 봅니다.  
  
     자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
#### 변수의 형식이 암시적으로 지정되게 하려면  
  
1.  `IGroupings`의 `IEnumerables`에 대한 코드를 명시적으로 작성하는 작업은 금방 지루해질 수 있습니다.  `var`를 사용하면 동일한 쿼리와 `foreach` 루프를 훨씬 더 편리하게 작성할 수 있습니다.  `var` 키워드는 개체의 형식을 변경하지 않으며 단순히 형식을 유추할 것을 컴파일러에 지시합니다.  형식을 변경 `studentQuery` 및 반복 변수 `group` 에 `var` 및 쿼리를 다시 실행 합니다.  이 경우 내부 `foreach` 루프에서 반복 변수의 형식은 여전히 `Student`로 지정되며 쿼리가 이전과 동일하게 작동합니다.  `s` 반복 변수를 `var`로 변경하고 쿼리를 다시 실행하면  동일한 결과가 나타나는 것을 볼 수 있습니다.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#16)]  
  
     [var](../../../../csharp/language-reference/keywords/var.md)에 대한 자세한 내용은 [암시적으로 형식화한 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을 참조하십시오.  
  
#### 키 값별로 그룹의 순서를 지정하려면  
  
1.  앞의 쿼리를 실행하면 그룹은 사전순으로 되어 있지 않습니다.  그룹에 이 순서를 지정하려면 `group` 절 뒤에 `orderby` 절을 제공해야 합니다.  그러나 `orderby` 절을 사용하려면 먼저 `group` 절에 의해 만들어진 그룹에 대한 참조로 사용되는 식별자가 필요합니다.  다음과 같이 `into` 키워드를 사용하여 이 식별자를 제공합니다.  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#17)]  
  
     이 쿼리를 실행하면 그룹은 이제 사전순으로 정렬됩니다.  
  
#### let을 사용하여 식별자를 제공하려면  
  
1.  `let` 키워드를 사용하여 쿼리 식의 임의 식 결과에 대한 식별자를 제공할 수 있습니다.  이 식별자는 다음 예제와 같이 편의상 제공될 수도 있고 여러 번 계산할 필요가 없도록 식 결과를 저장하여 성능을 향상시킬 수도 있습니다.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#18)]  
  
     자세한 내용은 [let 절](../../../../csharp/language-reference/keywords/let-clause.md)을 참조하십시오.  
  
#### 쿼리 식에서 메서드 구문을 사용하려면  
  
1.  [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)에 설명된 것처럼 일부 쿼리 작업은 메서드 구문에 의해서만 표현될 수 있습니다.  다음 코드는 소스 시퀀스에서 각 `Student`의 총 점수를 계산한 다음 해당 쿼리의 결과에서 `Average()` 메서드를 호출하여 클래스의 평균 점수를 계산합니다.  쿼리 식을 묶은 괄호에 주의합니다.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#19)]  
  
#### Select 절에서 변환 또는 프로젝션하려면  
  
1.  쿼리에서는 소스 시퀀스의 요소와 다른 요소를 가진 시퀀스를 생성하는 것이 매우 일반적입니다.  이전 쿼리 또는 실행 루프를 삭제하거나 주석으로 처리하고 다음 코드로 바꿉니다.  쿼리는 `Students`가 아니라 문자열 시퀀스를 반환하며 `foreach` 루프에서 이 사실이 반영됩니다.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#20)]  
  
2.  이 연습의 앞부분에 있는 코드는 평균 클래스 점수가 약 334라는 것을 나타냈습니다.  클래스 평균보다 총 점수가 높은 `Students`의 시퀀스를 생성하려면 해당 `Student ID`와 함께 익명 형식을 `select` 문에서 사용할 수 있습니다.  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#21)]  
  
## 다음 단계  
 C\#에서 쿼리를 사용하는 기본적인 측면에 익숙해진 후에는 원하는 특정 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자 형식에 대한 설명서와 샘플을 읽을 수 있습니다.  
  
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## 참고 항목  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)