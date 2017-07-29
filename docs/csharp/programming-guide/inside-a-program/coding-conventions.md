---
title: "C# 코딩 규칙(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a>C# 코딩 규칙(C# 프로그래밍 가이드)
[C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552)(C# 언어 사양)에서는 코딩 표준을 정의하지 않습니다. 그러나 이 항목의 지침은 Microsoft에서 샘플과 설명서를 개발하는 데 사용됩니다.  
  
 코딩 규칙은 다음과 같은 용도로 사용됩니다.  
  
-   코드를 확인하는 사용자들이 레이아웃이 아닌 내용에 집중할 수 있도록 일관성 있게 표시되는 코드를 만듭니다.  
  
-   코드를 확인하는 사용자들이 이전 경험을 토대로 한 가정을 통해 코드를 보다 빠르게 이해할 수 있도록 합니다.  
  
-   코드를 보다 쉽게 복사, 변경 및 유지 관리할 수 있도록 합니다.  
  
-   C# 모범 사례를 제시합니다.  
  
## <a name="naming-conventions"></a>명명 규칙  
  
-   [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)이 포함되지 않는 간단한 예제에서 네임스페이스 한정자를 사용합니다. 프로젝트에서 네임스페이스를 기본적으로 가져오는 경우에는 해당 네임스페이스의 이름을 정규화하지 않아도 됩니다. 정규화된 이름은 한 줄에 표시하기가 너무 길면 다음 예제에 나와 있는 것처럼 점(.)으로 분할할 수 있습니다.  
  
     [!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]  
  
-   다른 지침에 맞도록 조정하기 위해 Visual Studio 디자이너 도구를 사용하여 만든 개체 이름을 변경할 필요는 없습니다.  
  
## <a name="layout-conventions"></a>레이아웃 규칙  
 효율적인 레이아웃에서는 서식을 사용하여 코드 구조를 강조하고 코드를 보다 쉽게 읽을 수 있도록 생성합니다. Microsoft 예제 및 샘플은 다음 규칙을 따릅니다.  
  
-   기본 코드 편집기 설정(스마트 들여쓰기, 4자 들여쓰기, 탭을 공백으로 저장)을 사용합니다. 자세한 내용은 [옵션, 텍스트 편집기, C#, 서식](/visualstudio/ide/reference/options-text-editor-csharp-formatting)을 참조하세요.  
  
-   문을 한 줄에 하나씩만 작성합니다.  
  
-   선언을 한 줄에 하나씩만 작성합니다.  
  
-   연속 줄이 자동으로 들여쓰기되지 않으면 탭 정지 하나(공백 4개)만큼 들여씁니다.  
  
-   메서드 정의와 속성 정의 간에는 빈 줄을 하나 이상 추가합니다.  
  
-   다음 코드에 나와 있는 것처럼 괄호를 사용하여 식의 절을 명확하게 구분합니다.  
  
     [!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]  
  
## <a name="commenting-conventions"></a>주석 규칙  
  
-   코드 줄의 끝이 아닌 별도의 줄에 주석을 배치합니다.  
  
-   주석 텍스트는 대문자로 시작합니다.  
  
-   주석 텍스트 끝에는 마침표를 붙입니다.  
  
-   다음 코드에 나와 있는 것처럼 주석 구분 기호(//)와 주석 텍스트 사이에 공백을 하나 삽입합니다.  
  
     [!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]  
  
-   서식이 지정된 별표 블록으로 주석을 묶지 않습니다.  
  
## <a name="language-guidelines"></a>언어 지침  
 다음 섹션에서는 C# 팀이 코드 예제와 샘플을 준비할 때 따르는 방식에 대해 설명합니다.  
  
### <a name="string-data-type"></a>문자열 데이터 형식  
  
-   다음 코드에 나와 있는 것처럼 `+` 연산자를 사용하여 짧은 문자열을 연결합니다.  
  
     [!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]  
  
-   특히 많은 양의 텍스트를 사용할 때 문자열을 루프에 추가하려면 <xref:System.Text.StringBuilder> 개체를 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]  
  
### <a name="implicitly-typed-local-variables"></a>암시적으로 형식화한 지역 변수  
  
-   할당 오른쪽에서 변수 형식이 명확하거나 정확한 형식이 중요하지 않으면 지역 변수에 대해 [암시적 형식](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]  
  
-   할당 오른쪽에서 변수 형식이 명확하지 않으면 [var](../../../csharp/language-reference/keywords/var.md)를 사용하지 않습니다.  
  
     [!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]  
  
-   변수 이름을 사용하여 변수 형식을 지정하지 않습니다. 이렇게 하면 형식이 올바르게 지정되지 않을 수 있습니다.  
  
     [!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]  
  
-   [dynamic](../../../csharp/language-reference/keywords/dynamic.md) 대신 `var`를 사용하지 않습니다.  
  
-   [for](../../../csharp/language-reference/keywords/for.md) 및 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 루프의 루프 변수 형식을 결정하려면 암시적 형식을 사용합니다.  
  
     다음 예제에서는 `for` 문에서 암시적 형식을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]  
  
     다음 예제에서는 `foreach` 문에서 암시적 형식을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]  
  
### <a name="unsigned-data-type"></a>부호 없는 데이터 형식  
  
-   일반적으로는 부호 없는 형식 대신 `int`를 사용합니다. `int`는 C# 전체에서 일반적으로 사용되며, `int`를 사용하는 경우 다른 라이브러리와 보다 쉽게 상호 작용할 수 있습니다.  
  
### <a name="arrays"></a>배열  
  
-   선언 줄에서 배열을 초기화할 때는 간결한 구문을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]  
  
### <a name="delegates"></a>대리자  
  
-   대리자 형식의 인스턴스를 만들려면 간결한 구문을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>예외 처리의 try-catch 및 using 문  
  
-   대부분의 예외 처리에서는 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 문을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]  
  
-   C# [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 사용하면 코드를 간소화할 수 있습니다. `finally` 블록의 코드가 <xref:System.IDisposable.Dispose%2A> 메서드 호출뿐인 [try-finally](../../../csharp/language-reference/keywords/try-finally.md) 문이 있는 경우에는 `using` 문을 대신 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]  
  
### <a name="-and-124124-operators"></a>&& 및 &#124;&#124; 연산자  
  
-   예외를 방지하고 불필요한 비교를 건너뛰어 성능을 개선하려면 비교를 수행할 때 다음 예제에 나와 있는 것처럼 [&](../../../csharp/language-reference/operators/and-operator.md) 대신 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)를 사용하고 [&#124;](../../../csharp/language-reference/operators/or-operator.md) 대신 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)를 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]  
  
### <a name="new-operator"></a>New 연산자  
  
-   다음 선언에 나와 있는 것처럼 암시적 형식이 포함된 간결한 형태의 개체 인스턴스화를 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]  
  
     위의 줄은 다음 선언과 동일합니다.  
  
     [!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]  
  
-   개체를 간편하게 만들려면 개체 이니셜라이저를 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]  
  
### <a name="event-handling"></a>이벤트 처리  
  
-   나중에 제거할 필요가 없는 이벤트 처리기를 정의하는 경우 람다 식을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]  
  
### <a name="static-members"></a>정적 멤버  
  
-   *ClassName.StaticMember*와 같이 클래스 이름을 사용하여 [static](../../../csharp/language-reference/keywords/static.md) 멤버를 호출합니다. 이렇게 하면 정적 액세스가 명확하게 표시되므로 코드를 보다 쉽게 읽을 수 있습니다.  파생 클래스 이름을 사용하여 기본 클래스에 정의된 정적 멤버를 정규화해서는 안 됩니다.  이 코드는 컴파일되기는 하지만 가독성이 떨어지며 나중에 파생 클래스와 이름이 같은 정적 멤버를 추가하면 코드가 손상될 수도 있습니다.  
  
### <a name="linq-queries"></a>LINQ 쿼리  
  
-   쿼리 변수에 의미 있는 이름을 사용합니다. 다음 예제에서는 Seattle 거주 고객에 대해 `seattleCustomers`를 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   별칭을 사용하여 익명 형식의 속성 이름 대/소문자를 올바르게 표시합니다(파스칼식 대/소문자 사용).  
  
     [!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]  
  
-   결과의 속성 이름이 모호하면 속성 이름을 바꿉니다. 예를 들어 쿼리에서 고객 이름과 배포자 ID를 반환하는 경우 결과에서 이러한 정보를 `Name` 및 `ID`로 유지하는 대신 `Name`은 고객의 이름이고 `ID`는 배포자의 ID임을 명확하게 나타내도록 이름을 바꿉니다.  
  
     [!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]  
  
-   쿼리 변수 및 범위 변수의 선언에서 암시적 형식을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   위의 예제에 나와 있는 것처럼 [from](../../../csharp/language-reference/keywords/from-clause.md) 절 아래의 쿼리 절을 정렬합니다.  
  
-   뒷부분의 쿼리 절이 필터링을 통해 범위가 좁아진 데이터 집합에 대해 작동하도록 다른 쿼리 절 앞에 [where](../../../csharp/language-reference/keywords/where-clause.md) 절을 사용합니다.  
  
     [!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]  
  
-   내부 컬렉션에 액세스하려면 [join](../../../csharp/language-reference/keywords/join-clause.md) 절 대신 여러 `from` 절을 사용합니다. 예를 들어 `Student` 개체 컬렉션이 각각 테스트 점수 컬렉션을 포함하는 경우 다음 쿼리를 실행하면 90점보다 높은 각 점수와 해당 점수를 받은 학생의 성이 반환됩니다.  
  
     [!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]  
  
## <a name="security"></a>보안  
 [보안 코딩 지침](../../../standard/security/secure-coding-guidelines.md)의 지침을 따르세요.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 코딩 규칙](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [보안 코딩 지침](../../../standard/security/secure-coding-guidelines.md)

