---
title: Visual Basic에서 쿼리 작성
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: beb192f6b136455cb1adcb6cf2616578b63fcebf
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245741"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>연습: Visual Basic에서 쿼리 작성
이 연습에서는 쓸 Visual Basic 언어 기능을 사용 하는 방법을 보여 줍니다. [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 식입니다. 이 연습에서는 학생 개체의 목록에 쿼리를 만드는 방법, 쿼리를 실행 하는 방법 및 수정 하는 방법을 보여 줍니다. 쿼리 개체 이니셜라이저, 지역 형식 유추 및 익명 형식을 비롯 한 여러 기능을 통합 합니다.  
  
 이 연습을 완료 한 후 샘플 및 특정 문서를 진행할 준비가 됩니다 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 관심이 있습니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 포함 됩니다 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], 및 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]합니다.  
  
## <a name="create-a-project"></a>프로젝트 만들기  
  
#### <a name="to-create-a-console-application-project"></a>콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  에 **설치 된 템플릿** 목록에서 클릭 **Visual Basic**합니다.  
  
4.  프로젝트 형식 목록에서 클릭 **콘솔 응용 프로그램**합니다. 에 **이름을** 상자, 프로젝트의 이름을 입력 한 다음 클릭 **확인**합니다.  
  
     프로젝트를 만듭니다. 기본적으로 System.Core.dll에 대 한 참조를 포함 합니다. 또한 합니다 **가져온 네임 스페이스** 목록에서 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) 포함를 <xref:System.Linq?displayProperty=nameWithType> 네임 스페이스입니다.  
  
5.  에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 했는지 **Option infer** 로 설정 되어 **에서**합니다.  
  
## <a name="add-an-in-memory-data-source"></a>메모리 내 데이터 원본을 추가합니다  
 이 연습에서 쿼리에 대 한 데이터 원본이 목록을 `Student` 개체입니다. 각 `Student` 개체 이름, 성, 클래스 1 년 및 학생 본문에는 교육 순위를 포함 합니다.  
  
#### <a name="to-add-the-data-source"></a>데이터 소스를 추가하려면  
  
-   정의 `Student` 클래스 및 클래스의 인스턴스 목록을 만듭니다.  
  
    > [!IMPORTANT]
    >  정의 하는 데 필요한 코드를 `Student` 사용 되는 목록을 만들어 클래스 연습 예제에 제공 됩니다 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다. 여기에서 복사를 프로젝트에 붙여 넣습니다. 새 코드를 프로젝트를 만들 때 표시 되는 코드를 바꿉니다.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>학생 목록에 새 학생을 추가 하려면  
  
-   패턴에 따라 합니다 `getStudents` 의 다른 인스턴스를 추가 하는 방법의 `Student` 목록에 클래스. 학생을 추가 개체 이니셜라이저를 소개 합니다. 자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.  
  
## <a name="create-a-query"></a>쿼리 만들기  
 를 실행 하면이 섹션에 추가한 쿼리 academic 차수가 상위 10 개를 배치 하는 학생의 목록을 생성 합니다. 쿼리는 전체 선택 되므로 `Student` 개체가 될 때마다 쿼리 결과의 형식 `IEnumerable(Of Student)`합니다. 그러나 쿼리 형식이 일반적으로 지정 하지 않았습니다 쿼리 정의에서. 대신, 컴파일러는 형식을 확인 하려면 지역 형식 유추를 사용 합니다. 자세한 내용은 [로컬 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다. 쿼리의 범위 변수 `currentStudent`, 각각에 대 한 참조로 사용 `Student` 원본에는 인스턴스 `students`에서 각 개체의 속성에 대 한 액세스를 제공 `students`합니다.  
  
#### <a name="to-create-a-simple-query"></a>단순 쿼리를 작성하려면  
  
1.  위치를 찾습니다는 `Main` 다음과 같이 표시 된 프로젝트의 메서드:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     다음 코드를 복사 하 고 붙여 넣습니다.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  위에 마우스 포인터를 놓고 `studentQuery` 컴파일러에 할당 된 형식 인지 확인 하기 위해 코드에 `IEnumerable(Of Student)`입니다.  
  
## <a name="run-the-query"></a>쿼리 실행  
 변수의 `studentQuery` 쿼리 실행 결과가 아니라 쿼리의 정의 포함 합니다. 쿼리를 실행 하기 위한 일반적인 메커니즘은 한 `For Each` 루프입니다. 반환된 된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스 됩니다. 쿼리 실행에 대 한 자세한 내용은 참조 하세요. [Your 첫 번째 LINQ 쿼리를 작성 하도록](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.  
  
#### <a name="to-run-the-query"></a>쿼리를 실행 하려면  
  
1.  다음 추가 `For Each` 프로젝트의 쿼리 아래 루프입니다.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  루프 제어 변수 위에 마우스 포인터를 놓고 `studentRecord` 해당 데이터 형식을 표시 합니다. 유형의 `studentRecord` 로 유추 됩니다 `Student`이므로 `studentQuery` 컬렉션을 반환 합니다 `Student` 인스턴스.  
  
3.  빌드하고 ctrl+f5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에 결과 note 합니다.  
  
## <a name="modify-the-query"></a>쿼리 수정  
 지정 된 순서로 경우 쿼리 결과 검색 하는 것이 쉽습니다. 사용 가능한 모든 필드를 기준으로 반환된 된 시퀀스를 정렬할 수 있습니다.  
  
#### <a name="to-order-the-results"></a>결과를 정렬하려면  
  
1.  다음을 추가 합니다 `Order By` 간의 절을 `Where` 문 및 `Select` 쿼리 문입니다. `Order By` 절은 결과 순서 사전순 A에서 z, 각 학생의 성에 따라 합니다.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  성 및 이름, 주문 하도록 쿼리에 두 필드를 추가:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     지정할 수도 있습니다 `Descending` Z에서 A로 주문  
  
3.  빌드하고 ctrl+f5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에 결과 note 합니다.  
  
#### <a name="to-introduce-a-local-identifier"></a>로컬 식별자 소개  
  
1.  쿼리 식의 로컬 식별자를 제공 하려면이 섹션의 코드를 추가 합니다. 로컬 식별자에는 중간 결과 보관 합니다. 다음 예에서 `name` 는 학생의 연결을 보유 하는 식별자의 첫 번째 및 마지막으로 이름을 지정 합니다. 여러 번 계산 해야 하는 식의 결과 저장 하 여 성능이 향상 될 수 또는 편의 위해 로컬 식별자를 사용할 수 있습니다.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  빌드하고 ctrl+f5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에 결과 note 합니다.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Select 절에 하나의 필드를 프로젝트에  
  
1.  쿼리를 추가 하 고 `For Each` 소스의 요소와 다른 요소 시퀀스를 생성 하는 쿼리를 만들려면이 섹션에서 루프입니다. 다음 예제에서는 소스는 컬렉션인 `Student` 개체가 아니라 각 개체의 멤버가 하나만 반환 됩니다: 성이 가르시아 학생의 이름입니다. 때문에 `currentStudent.First` 문자열을 반환 하는 시퀀스 데이터 형식의 `studentQuery3` 는 `IEnumerable(Of String)`, 문자열의 시퀀스입니다. 이전 예제에서와 같이 데이터 할당에 대 한 입력 `studentQuery3` 지역 형식 유추를 사용 하 여 결정 컴파일러.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  위에 마우스 포인터를 놓고 `studentQuery3` 할당 된 형식 인지 확인 하기 위해 코드에 `IEnumerable(Of String)`입니다.  
  
3.  빌드하고 ctrl+f5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에 결과 note 합니다.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Select 절에서 무명 형식을 만들려면  
  
1.  쿼리에서 사용할 방법을 익명 형식을 확인 하려면이 섹션의 코드를 추가 합니다. 완전 한 레코드 보다는 데이터 원본에서 여러 필드를 반환 하려는 경우 쿼리에서 사용 합니다 (`currentStudent` 이전 예제에서 레코드) 또는 단일 필드 (`First` 이전 섹션에서). 필드를 지정 하면 결과에 포함 하려는 필드가 포함 된 새 명명 된 형식을 정의 하는 대신는 `Select` 절 및 컴파일러는 속성으로 해당 필드를 사용 하 여 무명 형식을 만듭니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예제에서는 이름과 academic 차수가 1 ~ 10, academic 순위 순서로 상급의 순위를 반환 하는 쿼리를 만듭니다. 이 예제에서는 형식의 `studentQuery4` 유추할 수 있어야 합니다는 `Select` 익명 형식의 인스턴스를 반환 하는 절 및 익명 형식에 사용할 수 있는 이름이 없습니다.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  빌드하고 ctrl+f5를 눌러 응용 프로그램을 실행 합니다. 콘솔 창에 결과 note 합니다.  
  
## <a name="additional-examples"></a>추가 예  
 다음은의 기능과 유연성을 보여 주기 위해 추가 예제 목록을 기본을 이해 했으므로 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. 각 예에서는 앞에 수행 하는 작업의 간략 한 설명입니다. 유추 된 형식을 확인 하려면 각 쿼리에 대 한 쿼리 결과 변수가 위에 마우스 포인터를 놓습니다. 사용 된 `For Each` 결과 생성 하는 루프입니다.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>추가 정보  
 특정 유형에 대 한 설명서와 샘플을 읽을 준비가 쿼리 작업의 기본 개념에 익숙한 후 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 에서 관심 있는 공급자:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
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
