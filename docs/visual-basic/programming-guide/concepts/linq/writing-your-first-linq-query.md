---
title: LINQ 쿼리 처음 작성(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: f426aac5358837563081d2bf9783f6d4fe04d853
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654892"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>LINQ 쿼리 처음 작성(Visual Basic)
*쿼리*는 데이터 소스에서 데이터를 검색하는 식입니다. 쿼리는 전용된 쿼리 언어로 표현 됩니다. 시간이 지남에 따라 다른 언어로 개발 되었습니다 다양 한 유형의 데이터 원본에 대 한 예를 들어, 관계형 데이터베이스에 대 한 SQL 및 XML에 대 한 XQuery. 이렇게 하면 응용 프로그램 개발자가 각 유형의 데이터 원본 또는 지원 되는 데이터 형식에 대 한 새 쿼리 언어를 배울 필요 합니다.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 다양 한 종류의 데이터 소스 및 형식 데이터로 작업 하기 위한 일관 된 모델을 제공 하 여 상황을 간소화 합니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서는 항상 개체를 사용하고 있습니다. 동일한 기본 코딩 패턴을 사용 하 여 쿼리하고를 XML 문서에 데이터, SQL 데이터베이스, ADO.NET 데이터 집합 및 엔터티,.NET Framework 컬렉션 및 모든 다른 원본 또는 형식 변환에 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자를 사용할 수 있습니다. 이 문서에서는 basic 사용 하 여 만들고 만들기의 세 단계를 설명 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다.  
  
## <a name="three-stages-of-a-query-operation"></a>쿼리 작업의 세 단계  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 작업 세 가지 동작으로 구성 됩니다.  
  
1.  데이터 소스 또는 소스를 가져옵니다.  
  
2.  쿼리 만들기.  
  
3.  쿼리 실행.  
  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 쿼리 실행은 쿼리 만들기와에서 다릅니다. 쿼리를 만들어 데이터를 검색 하지 않습니다. 이 내용에 대해서는 이 항목의 뒷부분에서 자세히 설명합니다.  
  
 다음 예제 쿼리 작업의 세 부분입니다. 이 예제에서는 데모용으로 편리 하 게 데이터 원본으로 정수 배열이 사용합니다. 그러나 동일한 개념은 다른 데이터 소스에도 적용 됩니다.  
  
> [!NOTE]
>  에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 되도록 **Option infer** 로 설정 된 **에**합니다.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 출력:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>데이터 소스  
 제네릭 데이터 소스는 앞의 예에서 배열 이기 때문에 암시적으로 지원 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스입니다. 배열에 대 한 데이터 원본으로 사용할 수 있도록이 팩트는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. <xref:System.Collections.Generic.IEnumerable%601> 또는 제네릭 <xref:System.Linq.IQueryable%601> 같은 파생된 인터페이스를 지원하는 형식을 *쿼리 가능 형식*이라고 합니다.  
  
 으로 암시적으로 쿼리 가능 형식의 배열은을 토대로 특수 처리 나 수정 없이 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 원본입니다. 지 원하는 모든 컬렉션 형식에도 마찬가지입니다 <xref:System.Collections.Generic.IEnumerable%601>, 제네릭을 포함 하 여 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, 및.NET Framework 클래스 라이브러리의 다른 클래스입니다.  
  
 원본 데이터가 아직 구현 하지 않는 경우 <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자의 기능을 구현 해야 하는 *표준 쿼리 연산자* 해당 데이터 원본에 대 한 합니다. 예를 들어 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 를 쿼리 가능한 XML 문서를 로드 하는 작업 처리 <xref:System.Xml.Linq.XElement> 다음 예제와 같이 입력 합니다. 표준 쿼리 연산자에 대 한 자세한 내용은 참조 [표준 쿼리 연산자 개요 (Visual Basic)](standard-query-operators-overview.md)합니다.  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 와 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]는 개체-관계형 매핑 디자인 타임에 수동 또는 사용 하 여 먼저 만듭니다는 [LINQ to SQL 도구 Visual Studio에서](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) Visual Studio에서. 개체에 대해 쿼리를 작성하면 런타임에 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 데이터베이스와의 통신을 처리합니다. 다음 예에서 `customers` 는 데이터베이스의 특정 테이블을 나타내는 및 <xref:System.Data.Linq.Table%601> 지원 제네릭 <xref:System.Linq.IQueryable%601>합니다.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 특정 형식의 데이터 소스를 만드는 방법에 대한 자세한 내용은 다양한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 대한 설명서를 참조하세요. (이러한 공급자의 목록을 보려면 참조 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) 기본 규칙은 간단:는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 원본이 지 원하는 제네릭 개체 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 여기에서 상속 하는 인터페이스입니다.  
  
> [!NOTE]
>  와 같은 형식은 <xref:System.Collections.ArrayList> 제네릭이 아닌를 지 원하는 <xref:System.Collections.IEnumerable> 인터페이스도 사용할 수도 있습니다 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 원본입니다. 사용 하는 예제는 <xref:System.Collections.ArrayList>, 참조 [하는 방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리](how-to-query-an-arraylist-with-linq.md)합니다.  
  
## <a name="the-query"></a>쿼리  
 쿼리에서 데이터 원본 또는 소스에서 검색 하려는 정보를 지정 합니다. 방법 정보를 정렬, 그룹화, 반환 하기 전에 구조를 지정할 수를 수도 있습니다. 쿼리를 만들 수 있도록, Visual Basic 언어에 새 쿼리 구문에 통합 되었습니다.  
  
 다음 예에서 쿼리는 정수 배열에서 모든 짝수 반환 실행 될 때 `numbers`합니다.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 세 개의 절을 포함 하는 쿼리 식: `From`, `Where`, 및 `Select`합니다. 각 쿼리 식 절의 목적 및 특정 함수에 대해서는 설명 [기본 쿼리 작업 (Visual Basic)](basic-query-operations.md)합니다. 자세한 내용은 참조 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)합니다. 에 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 쿼리 정의 종종 변수에 저장 되며 나중에 실행 합니다. 쿼리와 같은 변수 `evensQuery` 이전 예에서 쿼리 가능 형식 이어야 합니다. 유형의 `evensQuery` 은 `IEnumerable(Of Integer)`, 지역 형식 유추를 사용 하 여 컴파일러에서 할당 합니다.  
  
 쿼리 변수 자체 아무 작업도 수행 되 고 데이터를 반환 하지 하는 것이 유용 합니다. 쿼리 정의 저장 하기만 합니다. 이전 예제는 `For Each` 쿼리를 실행 하는 루프입니다.  
  
## <a name="query-execution"></a>쿼리 실행  
 쿼리 실행은 쿼리 만들기 다릅니다. 쿼리 만들기는 쿼리를 정의 하지만 실행은 다른 메커니즘으로 트리거됩니다. 정의 된 대로 쿼리를 실행할 수 있습니다 (*즉시 실행*), 또는 정의 저장할 수 있습니다 및 쿼리는 나중에 실행할 수 있습니다 (*지연 된 실행*).  
  
### <a name="deferred-execution"></a>지연된 실행  
 일반적인 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리는 이전 예제와 유사한 `evensQuery` 정의 됩니다. 쿼리 만들지만 즉시 실행 되지 않습니다. 쿼리 정의가 쿼리 변수에 저장 됩니다는 대신, `evensQuery`합니다. 나중에 실행할 때는 쿼리 일반적으로 사용 하 여 한 `For Each` 또는 같은 표준 쿼리 연산자를 적용 하 여 값의 시퀀스를 반환 하는 루프 `Count` 또는 `Max`합니다. 이 프로세스 라고 *지연 된 실행*합니다.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 값의 시퀀스에 대 한 반복 변수를 사용 하 여 검색된 데이터에 액세스는 `For Each` 루프 (`number` 이전 예제에서). 때문에 쿼리 변수 `evensQuery`, 쿼리 결과 보다는 쿼리 정의 보유 한 번 이상 쿼리 변수를 사용 하 여 원하는 만큼 자주 쿼리를 실행할 수 있습니다. 예를 들어 별도 응용 프로그램에서 지속적으로 업데이트 되는 응용 프로그램에 데이터베이스가 있을 수 있습니다. 해당 데이터베이스에서 데이터를 검색 하는 쿼리를 만든 후 사용할 수 있습니다는 `For Each` 루프를 반복 해 서 쿼리를 실행 하려면 될 때마다 가장 최근 데이터를 검색 합니다.  
  
 다음 예제에서는 어떻게 지연 된 실행 작동 합니다. 후 `evensQuery2` 정의 하 고 실행 되는 `For Each` 데이터 원본의 일부 요소 앞의 예와 루프 `numbers` 변경 됩니다. 다음 두 번째 `For Each` 루프가 실행 되 `evensQuery2` 다시 합니다. 결과 서로 다른 두 번째로 때문에 `For Each` 루프 쿼리를 다시 실행에 새 값을 사용 하 여 `numbers`합니다.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 출력:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>즉시 실행  
 쿼리의 실행을 지연 된 쿼리 정의 나중에 실행에 대 한 쿼리 변수에 저장 됩니다. 즉시 실행 쿼리는 해당 정의의 시간에 실행 됩니다. 실행은 쿼리 결과의 개별 요소에 액세스 해야 하는 메서드를 적용 하는 경우에 트리거됩니다. 단일 값을 반환 하는 표준 쿼리 연산자 중 하나를 사용 하 여 즉시 실행 종종 forced입니다. 예로 `Count`, `Max`, `Average`, 및 `First`합니다. 이러한 표준 쿼리 연산자를 계산 하 고 단일 항목 결과 반환 하기 위해 적용 되는 즉시 쿼리를 실행 합니다. 단일 값을 반환 하는 표준 쿼리 연산자에 대 한 자세한 내용은 참조 [집계 작업](aggregation-operations.md), [요소 작업](element-operations.md), 및 [수량자 작업](quantifier-operations.md)합니다.  
  
 다음 쿼리에서 정수 배열에는 짝수의 수를 반환합니다. 쿼리 정의 저장 하지 않으면 및 `numEvens` 은 단순 `Integer`합니다.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 사용 하 여 동일한 결과 얻을 수는 `Aggregate` 메서드.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 호출 하 여 쿼리 실행을 강제할 수도 있습니다는 `ToList` 또는 `ToArray` 메서드 (즉시) 쿼리 또는 다음 코드에서와 같이 쿼리 변수 (지연)에 있습니다.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 앞의 예에서 `evensQuery3` 쿼리 변수 이지만 `evensList` 목록 및 `evensArray` 은 배열입니다.  
  
 사용 하 여 `ToList` 또는 `ToArray` 강제로 즉시 실행이 즉시 쿼리를 실행 하 고 결과 단일 컬렉션 개체에 캐시 하려는 시나리오에서 특히 유용 합니다. 이러한 메서드에 대 한 자세한 내용은 참조 [데이터 형식 변환](converting-data-types.md)합니다.  
  
 할 수도 있습니다를 사용 하 여 실행할 쿼리는 `IEnumerable` 와 같은 메서드는 <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 LINQ 시작](getting-started-with-linq.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)
