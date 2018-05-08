---
title: LINQ를 지원하는 Visual Basic 기능
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="visual-basic-features-that-support-linq"></a>LINQ를 지원하는 Visual Basic 기능
이름 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 기술을 지 원하는 쿼리 구문 및 기타 언어 구문이 도입 되면서 언어로 직접 Visual Basic의 나타냅니다. 와 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 외부 데이터 원본에 대 한 쿼리는 새 언어를 배울 필요가 없습니다. Visual Basic을 사용 하 여 데이터 관계형 데이터베이스, XML 저장소 또는 개체에 대해 쿼리할 수 있습니다. 언어에 대 한 쿼리 기능이 통합이 컴파일 타임 구문 오류 및 형식 안전성 확인 수 있습니다. 이 통합에서는 또한 대부분의 Visual Basic의 다양 한 서식 있는 쿼리를 작성할 수 있는 이미 알고 있다고 보장 합니다.  
  
 다음 섹션에서는 읽기 소개 문서, 코드 예제 및 예제 응용 프로그램에서 시작할 수 있도록 자세히 LINQ를 지 원하는 언어 구문에 설명 합니다. 언어 기능 함께 일 하 언어 통합 쿼리를 사용 하도록 설정 하는 방법의 더 자세한 설명을 보려면 링크를 클릭할 수도 있습니다. 시작 하는 것이 좋습니다 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)합니다.  
  
## <a name="query-expressions"></a>쿼리 식  
 쿼리 식은 Visual Basic에서 SQL 또는 XQuery와 유사한 선언적 구문으로 표현할 수 있습니다. 컴파일 타임에 쿼리 구문은 표준 쿼리 연산자 확장 메서드는 LINQ 공급자의 구현에 대 한 메서드 호출으로 변환 됩니다. 표준 쿼리 연산자 범위에 있는 적절 한 네임 스페이스를 지정 하 여 응용 프로그램 제어는 `Imports` 문. Visual Basic 쿼리 식 구문은 다음과 같습니다.  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 자세한 내용은 참조 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.  
  
## <a name="implicitly-typed-variables"></a>암시적으로 형식화 된 변수  
 대신 명시적으로 지정 하는 형식을 선언 하 고 변수를 초기화할 때 컴파일러 유추 하 고 유형을 할당에 사용할 수 있습니다. 이 라고 *지역 형식 유추*합니다.  
  
 변수 형식이 유추 되는 강력한 마찬가지로 형식 변수 형식을 명시적으로 지정 합니다. 지역 형식 유추 메서드 본문 내에서 지역 변수를 정의 하는 경우에 작동 합니다. 자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.  
  
 다음 예제에서는 지역 형식 유추를 보여 줍니다. 이 예제를 사용 하려면 설정 해야 `Option Infer` 를 `On`합니다.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 지역 형식 유추를 하면이 섹션의 뒷부분에서 설명 되 고 LINQ 쿼리에 필요한 있는 익명 형식을 만들 수 있습니다.  
  
 다음 LINQ 예제의 경우 형식 유추가 발생 `Option Infer` 있거나 `On` 또는 `Off`합니다. 컴파일 타임 오류가 발생 하는 경우 `Option Infer` 은 `Off` 및 `Option Strict` 은 `On`합니다.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>개체 이니셜라이저  
 개체 이니셜라이저는 쿼리 결과를 저장할 익명 형식을 만들어야 하는 경우 쿼리 식에 사용 됩니다. 또한 사용할 수 쿼리 외부에서 명명 된 형식의 개체를 초기화 합니다. 개체 이니셜라이저를 사용 하 여 명시적으로 생성자를 호출 하지 않고 한 줄에 개체를 초기화할 수 있습니다. 라는 클래스가 있는 경우 `Customer` 공개 된 `Name` 및 `Phone` 속성을 다른 속성과 함께 개체 이니셜라이저가이 방식으로 사용할 수 있습니다.  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 자세한 내용은 참조 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.  
  
## <a name="anonymous-types"></a>익명 형식  
 익명 형식은 일시적으로 쿼리 결과에 포함 시킬 요소로 속성 집합을 그룹화 하는 편리한 방법을 제공 합니다. 이 요소에 대 한 명명 된 데이터 형식을 정의 하지 않고 어떤 순서로 든 쿼리에서 사용할 수 있는 필드의 조합을 선택할 수 있습니다.  
  
 *익명 형식* 은 컴파일러에 의해 동적으로 생성 합니다. 컴파일러에 의해 할당 된 형식의 이름 및 새로 컴파일할 때마다 변경 될 수 있습니다. 따라서 이름은 직접 사용할 수 없습니다. 익명 형식은 다음과 같은 방식으로 초기화 됩니다.  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
## <a name="extension-methods"></a>확장명 메서드  
 확장 메서드를 사용 하 여 데이터 형식 또는 정의 외부에서 인터페이스에 메서드를 추가할 수 있습니다. 이 기능을 사용 하면 실제로 실제로 형식을 수정 하지 않고 기존 형식에 새 메서드를 추가할 수 있습니다. 표준 쿼리 연산자 확장 메서드를 제공 하는 집합 자체는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 구현 하는 형식에 대 한 쿼리 기능 <xref:System.Collections.Generic.IEnumerable%601>합니다. 다른 확장으로 <xref:System.Collections.Generic.IEnumerable%601> 포함 <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, 및 <xref:System.Linq.Enumerable.Intersect%2A>합니다.  
  
 인쇄 메서드를 추가 하는 다음 확장 메서드는 <xref:System.String> 클래스입니다.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 일반적인 인스턴스 메서드와 같은 메서드는 <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 자세한 내용은 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.  
  
## <a name="lambda-expressions"></a>람다 식  
 람다 식은 계산 하 고 단일 값을 반환 하는 이름이 없는 함수입니다. 명명 된 함수와 달리 람다 식은 정의 하 고 실행할 수는 동시에 합니다. 다음 예에서는 4를 표시합니다.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 변수 이름에 람다 식 정의 할당할 수 있으며 다음 이름을 사용 하 여 함수 호출. 다음 예제에는 4도 표시 됩니다.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], 람다 식의 표준 쿼리 연산자 여러 기반이 됩니다. 컴파일러와 같은 기본 쿼리 메서드에 정의 된 계산을 캡처하는 람다 식을 만듭니다 `Where`, `Select`, `Order By`, `Take While`, 등입니다.  
  
 예를 들어 다음 코드에서는 학생의 목록에서 모든 수석 학생을 반환 하는 쿼리를 정의 합니다.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 쿼리 정의 대 한 인수를 지정 하려면 두 람다 식을 사용 하 여 다음 예제와 비슷한 코드로 컴파일될 `Where` 및 `Select`합니다.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 두 버전 중 하나를 사용 하 여 실행할 수 있습니다는 `For Each` 루프:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 자세한 내용은 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ(Language-Integrated Query)(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
