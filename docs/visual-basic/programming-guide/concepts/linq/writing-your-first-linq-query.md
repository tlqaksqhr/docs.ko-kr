---
title: LINQ 쿼리 처음 작성(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 44fbf35ee4ab5a0c4763269808f0817a33d05b40
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998439"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>LINQ 쿼리 처음 작성(Visual Basic)
*쿼리*는 데이터 소스에서 데이터를 검색하는 식입니다. 쿼리는 전용된 쿼리 언어로 표현 됩니다. 시간이 지남에 따라 다른 언어가 개발 되었습니다 다양 한 유형의 데이터 원본에 대 한 예를 들어, 관계형 데이터베이스에 대 한 SQL 및 XML에 대 한 XQuery입니다. 이렇게 하면 응용 프로그램 개발자가 각 유형의 데이터 원본 또는 지원 되는 데이터 형식에 대 한 새 쿼리 언어를 배울 필요 합니다.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 다양 한 종류의 데이터 소스 및 형식 데이터로 작업 하기 위한 일관 된 모델을 제공 하 여 상황을 간소화 합니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서는 항상 개체를 사용하고 있습니다. 동일한 기본 코딩 패턴을 사용 하 여 쿼리는 XML 문서에서 데이터, SQL 데이터베이스, ADO.NET 데이터 집합 및 엔터티,.NET Framework 컬렉션 및 모든 다른 원본 또는 형식으로 변환 하는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자를 사용할 수 있습니다. 이 문서에서는 생성의 3 단계인 및 basic 사용 하 여 설명 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다.  
  
## <a name="three-stages-of-a-query-operation"></a>쿼리 작업의 세 단계  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 작업의 세 가지 작업으로 구성 됩니다.  
  
1.  데이터 소스 또는 소스를 가져옵니다.  
  
2.  쿼리 만들기.  
  
3.  쿼리 실행.  
  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 쿼리의 실행 된 쿼리 만들기와에서 다릅니다. 쿼리를 만들어 모든 데이터를 검색할 수 없습니다. 이 내용에 대해서는 이 항목의 뒷부분에서 자세히 설명합니다.  
  
 다음 예제에서는 쿼리 작업의 세 부분을 보여 줍니다. 이 예제에서는 데모용으로 편리 하 게 데이터 원본으로 정수 배열을 사용합니다. 그러나 동일한 개념이 다른 데이터 원본에도 적용 합니다.  
  
> [!NOTE]
>  에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 했는지 **Option infer** 로 설정 되어 **에서**합니다.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 출력:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>데이터 소스  
 제네릭 이전 예제에서 데이터 원본을 배열 이기 때문에 암시적으로 지원 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스입니다. 이 사실을 배열에 대 한 데이터 원본으로 사용할 수 있도록 하는 것을 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. <xref:System.Collections.Generic.IEnumerable%601> 또는 제네릭 <xref:System.Linq.IQueryable%601> 같은 파생된 인터페이스를 지원하는 형식을 *쿼리 가능 형식*이라고 합니다.  
  
 암시적으로 쿼리 가능한 형식으로 배열 필요 없거나 수정으로 사용할 특별 한 처리를 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 원본입니다. 마찬가지 지 원하는 모든 컬렉션 형식에 대 한 <xref:System.Collections.Generic.IEnumerable%601>, 제네릭 포함 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, 및.NET Framework 클래스 라이브러리의 다른 클래스입니다.  
  
 원본 데이터를 이미 구현 하지 않는 경우 <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자의 기능을 구현 하는 데 필요한 합니다 *표준 쿼리 연산자* 해당 데이터 원본에 대 한 합니다. 예를 들어 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 를 쿼리 가능한 XML 문서를 로드 하는 작업 처리 <xref:System.Xml.Linq.XElement> 다음 예제에서와 같이 입력 합니다. 표준 쿼리 연산자에 대 한 자세한 내용은 참조 하세요. [표준 쿼리 연산자 개요 (Visual Basic)](standard-query-operators-overview.md)합니다.  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 사용 하 여 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에 개체 관계형 매핑을 디자인 타임에 수동으로 또는 사용 하 여 먼저 만들어야 합니다 [LINQ to SQL 도구 Visual Studio에서](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) Visual Studio에서. 개체에 대해 쿼리를 작성하면 런타임에 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 데이터베이스와의 통신을 처리합니다. 다음 예에서 `customers` 데이터베이스의 특정 테이블을 나타내며 및 <xref:System.Data.Linq.Table%601> 지 원하는 일반 <xref:System.Linq.IQueryable%601>합니다.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 특정 형식의 데이터 소스를 만드는 방법에 대한 자세한 내용은 다양한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 대한 설명서를 참조하세요. (이러한 공급자 목록은 참조 하세요 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) 기본 규칙은 간단 합니다:는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 소스는 제네릭을 지 원하는 모든 개체 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 인터페이스에서 상속 된 합니다.  
  
> [!NOTE]
>  같은 형식의 <xref:System.Collections.ArrayList> 제네릭이 아닌 지 <xref:System.Collections.IEnumerable> 인터페이스를 사용할 수도 있습니다 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 원본입니다. 사용 하는 예는 <xref:System.Collections.ArrayList>를 참조 하세요 [하는 방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>쿼리  
 쿼리에서 데이터 소스 또는 소스에서 검색 하려는 정보를 지정 합니다. 방법 정보 정렬, 그룹화 이거나 반환 되기 전에 구조적 지정할 수가 있습니다. 쿼리 생성을 사용 하려면 Visual Basic 언어에 새로운 쿼리 구문이 통합 했습니다.  
  
 다음 예제에서는 쿼리에서 정수 배열에서 모든 짝수를 반환 합니다 실행 될 때 `numbers`합니다.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 세 가지 절을 포함 하는 쿼리 식: `From`, `Where`, 및 `Select`합니다. 특정 함수 및 각 쿼리 식 절의 용도 설명 되어 [기본 쿼리 작업 (Visual Basic)](basic-query-operations.md)합니다. 자세한 내용은 [쿼리](../../../../visual-basic/language-reference/queries/index.md)합니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 쿼리 정의 종종은 변수에 저장 하 고 나중에 실행 합니다. 쿼리 변수를 같은 `evensQuery` 이전 예에서 쿼리 가능 형식 이어야 합니다. 유형의 `evensQuery` 는 `IEnumerable(Of Integer)`, 지역 형식 유추를 사용 하 여 컴파일러에서 할당 합니다.  
  
 쿼리 변수 자체 아무 작업도 수행 하지 않고 데이터를 반환 해야 하는 것이 반드시 합니다. 쿼리 정의 저장 하기만 합니다. 에서는 이전 예에서 `For Each` 쿼리를 실행 하는 루프입니다.  
  
## <a name="query-execution"></a>쿼리 실행  
 쿼리 실행은 쿼리 만들기 다릅니다. 쿼리 만들기는 쿼리를 정의 하지만 실행 하는 다른 메커니즘에 의해 트리거됩니다. 정의 된 대로 쿼리를 실행할 수 있습니다 (*즉시 실행*), 또는 정의 저장할 수 있으며 쿼리는 나중에 실행할 수 있습니다 (*지연 된 실행*).  
  
### <a name="deferred-execution"></a>지연된 실행  
 일반적인 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리는 이전 예제에서는 한 선언과 유사 `evensQuery` 정의 됩니다. 이 쿼리를 만들지만 즉시 실행 되지 않습니다. 대신 쿼리 정의가 쿼리 변수에 저장 됩니다 `evensQuery`합니다. 쿼리를 실행할 때는 나중에 일반적으로 사용 하 여는 `For Each` 와 같은 표준 쿼리 연산자를 적용 하거나 값의 시퀀스를 반환 하는 루프 `Count` 또는 `Max`합니다. 이 프로세스 라고 *지연 된 실행*합니다.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 값의 시퀀스를 반복 변수를 사용 하 여 검색된 데이터에 액세스 합니다 `For Each` 루프 (`number` 이전 예제에서). 때문에 쿼리 변수를 `evensQuery`, 쿼리 결과 보다는 쿼리 정의 보유 한 번만 쿼리 변수를 사용 하 여 원하는 만큼 자주 쿼리를 실행할 수 있습니다. 예를 들어, 별도 응용 프로그램에서 지속적으로 업데이트 되는 응용 프로그램에서 데이터베이스가 있을 수 있습니다. 데이터베이스에서 데이터를 검색 하는 쿼리를 만든 후 사용할 수 있습니다는 `For Each` 루프를 반복적으로 쿼리를 실행 될 때마다 최신 데이터를 검색 합니다.  
  
 다음 예제에서는 어떻게 지연 된 실행 작동 합니다. 후 `evensQuery2` 정의 되 고 사용 하 여 실행을 `For Each` 데이터 원본에서 일부 요소 앞의 예에서 같이 루프 `numbers` 변경 됩니다. 다음 두 번째 `For Each` 루프가 실행 `evensQuery2` 다시 합니다. 결과 서로 다른 두 번째로 때문에 합니다 `For Each` 루프가 쿼리를 다시 실행, 새 값을 사용 하 여 `numbers`입니다.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 출력:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>즉시 실행  
 쿼리의 실행을 지연 쿼리 정의 나중에 실행에 대 한 쿼리 변수에 저장 됩니다. 즉시 실행에 포함 된 쿼리 정의 시 실행 됩니다. 실행은 쿼리 결과의 개별 요소에 대 한 액세스를 사용 하는 메서드에 적용할 때 트리거됩니다. 단일 값을 반환 하는 표준 쿼리 연산자 중 하나를 사용 하 여 즉시 실행 종종 forced입니다. 예로 `Count`, `Max`를 `Average`, 및 `First`합니다. 이러한 표준 쿼리 연산자를 계산 하 고 단일 결과 반환 하기 위해 적용 되는 즉시 쿼리를 실행 합니다. 단일 값을 반환 하는 표준 쿼리 연산자에 대 한 자세한 내용은 참조 하세요. [집계 작업](aggregation-operations.md)를 [작업에서 앨리어싱이](element-operations.md), 및 [수량자 작업](quantifier-operations.md)합니다.  
  
 다음 쿼리는 정수 배열에서 짝수의 개수를 반환합니다. 쿼리 정의 저장 하지 않으면 및 `numEvens` 단순 `Integer`합니다.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 사용 하 여 동일한 결과 얻을 수 있습니다는 `Aggregate` 메서드.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 호출 하 여 쿼리 실행을 강제할 수도 있습니다는 `ToList` 또는 `ToArray` 쿼리를 즉시 또는 다음 코드 에서처럼 쿼리 변수 (지연) 메서드.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 이전 예에서 `evensQuery3` 쿼리 변수 이지만 `evensList` 은 목록 및 `evensArray` 배열.  
  
 사용 하 여 `ToList` 또는 `ToArray` 강제로 즉시 실행이 즉시 쿼리를 실행 하 고 결과 단일 컬렉션 개체를 캐시 하려는 시나리오에서 특히 유용 합니다. 이러한 방법에 대 한 자세한 내용은 참조 하세요. [데이터 형식 변환](converting-data-types.md)합니다.  
  
 할 수도 있습니다는 쿼리를 사용 하 여 실행할 수는 `IEnumerable` 와 같은 메서드는 <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 LINQ 시작](getting-started-with-linq.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/index.md)
