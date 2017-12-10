---
title: "Visual Basic에서 쿼리 작성"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: "70"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d30ad7f0db2760427493610c630f3fff8dcfac31
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>연습: Visual Basic에서 쿼리 작성
이 연습에서는 Visual Basic 언어 기능을 사용 하 여 작성 하는 방법을 보여 줍니다. [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 식입니다. 이 연습에는 쿼리를 만드는 방법을 학생 개체의 목록에서 다음 쿼리를 실행 하는 방법 및 수정 하는 방법을 보여 줍니다. 이 쿼리는 개체 이니셜라이저, 지역 형식 유추, 익명 형식을 비롯 한 몇 가지 기능을 통합 합니다.  
  
 이 연습을 완료 한 후 샘플 및 특정에 대 한 설명서로 이동할 준비가 됩니다 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 관심이 있습니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]공급자에 포함 되어 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], 및 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]합니다.  
  
## <a name="create-a-project"></a>프로젝트 만들기  
  
#### <a name="to-create-a-console-application-project"></a>콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  에 **설치 된 템플릿** 목록에서 클릭 **Visual Basic**합니다.  
  
4.  프로젝트 형식 목록에서 클릭 **콘솔 응용 프로그램**합니다. 에 **이름** 상자, 프로젝트에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.  
  
     프로젝트를 만들 수 있습니다. 기본적으로 System.Core.dll에 대 한 참조를 포함 합니다. 또한는 **가져온 네임 스페이스** 목록에 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) 포함는 <xref:System.Linq?displayProperty=nameWithType> 네임 스페이스입니다.  
  
5.  에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 되도록 **Option infer** 로 설정 된 **에**합니다.  
  
## <a name="add-an-in-memory-data-source"></a>메모리 내 데이터 원본 추가  
 이 연습에서 쿼리의 데이터 원본이 목록이 `Student` 개체입니다. 각 `Student` 개체 이름, 성, 학년 및 생 학생 본문에는 포함 되어 있습니다.  
  
#### <a name="to-add-the-data-source"></a>데이터 소스를 추가하려면  
  
-   정의 `Student` 클래스와 클래스의 인스턴스 목록을 만듭니다.  
  
    > [!IMPORTANT]
    >  정의 하는 데 필요한 코드는 `Student` 클래스를 만들고 사용 하는 목록을 연습 예제에 제공 됩니다 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다. 여기에서 복사 하 고 프로젝트에 붙여 수 있습니다. 새 코드를 프로젝트를 만들 때 표시 하는 코드를 바꿉니다.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>새 학생 학생 목록에 추가 하려면  
  
-   패턴에 따라는 `getStudents` 의 다른 인스턴스를 추가 하는 메서드는 `Student` 목록에는 클래스입니다. 학생을 추가 개체 이니셜라이저를 소개 합니다. 자세한 내용은 참조 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.  
  
## <a name="create-a-query"></a>쿼리 만들기  
 를 실행 하면이 섹션에 추가 된 쿼리 상위 10 개의 추가한 등 수가 학생의 목록을 생성 합니다. 쿼리 전체를 선택 하기 때문에 `Student` 개체 때마다 쿼리 결과의 종류는 `IEnumerable(Of Student)`합니다. 그러나 쿼리 형식이 일반적으로 지정 하지 않았습니다 쿼리 정의에. 대신, 컴파일러는 형식을 확인 하려면 지역 형식 유추를 사용 합니다. 자세한 내용은 참조 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다. 쿼리의 범위 변수 `currentStudent`, 각각에 대 한 참조로 사용 `Student` 는 소스인 `students`에 있는 각 개체의 속성에 대 한 액세스를 제공 하 `students`합니다.  
  
#### <a name="to-create-a-simple-query"></a>단순 쿼리를 작성하려면  
  
1.  위치를 찾습니다는 `Main` 다음과 같이 표시 하는 프로젝트의 메서드:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     다음 코드를 복사 하 고 붙여 넣습니다.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  마우스 포인터로 가리켜 `studentQuery` 컴파일러에서 할당 유형이 인지 확인 하기 위해 코드에 `IEnumerable(Of Student)`합니다.  
  
## <a name="run-the-query"></a>쿼리 실행  
 변수 `studentQuery` 쿼리를 실행 결과가 아니라 쿼리의 정의 포함 합니다. 쿼리를 실행 하기 위한 일반적인 메커니즘은는 `For Each` 루프입니다. 반환된 된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스 됩니다. 쿼리 실행에 대 한 자세한 내용은 참조 [쓰기 Your LINQ 쿼리 처음](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.  
  
#### <a name="to-run-the-query"></a>쿼리를 실행 하려면  
  
1.  다음 추가 `For Each` 루프 아래 프로젝트에 쿼리 합니다.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  루프 제어 변수 위에 마우스 포인터를 놓고 `studentRecord` 해당 데이터 형식을 볼 수 있습니다. 유형의 `studentRecord` 것으로 유추 `Student`때문에, `studentQuery` 의 컬렉션을 반환 `Student` 인스턴스.  
  
3.  빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에서 결과 note 합니다.  
  
## <a name="modify-the-query"></a>쿼리 수정  
 지정된 된 순서에 있는 경우 쿼리 결과 검색 하는 것이 쉽습니다. 사용 가능한 모든 필드에 따라 반환된 된 시퀀스를 정렬할 수 있습니다.  
  
#### <a name="to-order-the-results"></a>결과를 정렬하려면  
  
1.  다음 추가 `Order By` 절 간의 `Where` 문 및 `Select` 쿼리 문입니다. `Order By` 절은 결과 순서 사전순으로 a에서-Z, 성의 성에 따라 합니다.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  요청 된 성 및 이름, 쿼리에 두 필드를 추가 합니다.  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     표시할 `Descending` a z에서 순서  
  
3.  빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에서 결과 note 합니다.  
  
#### <a name="to-introduce-a-local-identifier"></a>로컬 식별자를 제공 하려면  
  
1.  쿼리 식의 로컬 식별자를 제공 하려면이 섹션의 코드를 추가 합니다. 로컬 식별자는 중간 결과 보관 합니다. 다음 예에서 `name` 학생의 연결을 보유 하는 식별자의 첫 번째 이름과 성이 됩니다. 여러 번 계산 해야 하는 식의 결과 저장 하 여 성능이 향상 될 수 또는 편의 위해 로컬 식별자를 사용할 수 있습니다.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에서 결과 note 합니다.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Select 절에 필드를 하나에 프로젝트  
  
1.  쿼리를 추가 하 고 `For Each` 해당 요소가 원본의 요소와 다른 시퀀스를 생성 하는 쿼리를 만들려면이 섹션에서 루프입니다. 다음 예제에서는 소스 컬렉션을는 `Student` 개체가 아니라는 각 개체의 멤버를 하나만 반환 됩니다: 성이 Garcia 인 학생의 성입니다. 때문에 `currentStudent.First` 는 문자열에서 반환 된 시퀀스의 데이터 형식을 `studentQuery3` 은 `IEnumerable(Of String)`, 문자열의 시퀀스입니다. 이전 예제에서와 같이 데이터의 할당에 대 한 형식 `studentQuery3` 컴파일러 지역 형식 유추를 사용 하 여 결정 합니다.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  마우스 포인터로 가리켜 `studentQuery3` 할당 된 형식이 확인 하기 위해 코드에 `IEnumerable(Of String)`합니다.  
  
3.  빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에서 결과 note 합니다.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Select 절에 익명 형식을 만들려면  
  
1.  쿼리에서 사용할 방법을 익명 유형을 확인 하려면이 섹션에서 코드를 추가 합니다. 완전 한 레코드 아닌 데이터 원본에서 여러 필드를 반환 하려면 쿼리에서 사용으로 (`currentStudent` 이전 예제에서 레코드) 또는 단일 필드 (`First` 이전 섹션에). 결과에 포함할 필드를 포함 하는 새 명명 된 형식을 정의 하는 대신에 필드를 지정 된 `Select` 절과 컴파일러 속성으로 해당 필드가 있는 익명 형식을 만듭니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예에서는 이름 및 등 수가 1 ~ 10 생 순서로 상급의 순위를 반환 하는 쿼리를 만듭니다. 이 예제에서는 유형의 `studentQuery4` 유추 되어야 합니다는 `Select` 절 익명 형식의 인스턴스를 반환 하 고 익명 형식에 사용할 수 있는 이름이 없습니다.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에서 결과 note 합니다.  
  
## <a name="additional-examples"></a>추가 예  
 다음은 유연성을 설명 하기 위해 추가 예제를 보려면 목록 및의 기본 사항을 살펴보았으므로 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. 각 예에서는 역할에 대 한 간략 한 설명을 뒤에 옵니다. 유추 된 유형 참조를 각 쿼리에 대 한 쿼리 결과 변수 위에 마우스 포인터를 놓습니다. 사용 하 여 한 `For Each` 루프는 결과를 생성 합니다.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>추가 정보  
 특정 형식에 대 한 설명서와 샘플을 읽을 준비가 쿼리 작업의 기본 개념에 익숙한 후 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 에 관심이 있는 공급자:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a>참고 항목  
 [LINQ(Language-Integrated Query)(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)
