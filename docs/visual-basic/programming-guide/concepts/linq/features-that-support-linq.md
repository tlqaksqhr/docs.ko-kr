---
title: "Visual Basic Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, LINQ features"
  - "LINQ [Visual Basic], features supporting LINQ"
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
caps.handback.revision: 49
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Visual Basic Features That Support LINQ
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]라는 이름은 언어에서 직접 쿼리 구문과 다른 새 언어 생성자를 지원하는 Visual Basic 기술을 나타냅니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]를 사용하면 외부 데이터 소스를 쿼리하는 새 언어를 배울 필요가 없습니다.  즉, Visual Basic을 사용하여 관계형 데이터베이스, XML 저장소 또는 개체의 데이터를 쿼리할 수 있습니다.  이러한 쿼리 기능과 언어의 통합으로 컴파일 타임에 구문 오류와 형식 안정성을 검사할 수 있습니다.  또한 이 통합 덕분에 이제는 Visual Basic에서 기능이 풍부한 다양한 쿼리를 작성하기 위해 사용자가 알아야 하는 사항을 대부분 미리 알 수 있도록 보장할 수 있습니다.  
  
 다음 단원에서는 소개 문서, 코드 예제 및 샘플 응용 프로그램 사용할 수 있도록 LINQ를 지원하는 언어 구조에 대해 충분히 자세하게 설명합니다.  또한 링크를 클릭하면 언어 기능을 어떻게 조합하여 통합 언어 쿼리를 활성화하는지 자세히 알아 볼 수 있습니다.  이 학습은 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)에서 시작하는 것이 좋습니다.  
  
## 쿼리 식  
 Visual Basic의 쿼리 식은 SQL 또는 XQuery의 쿼리 식과 유사한 선언 구문으로 표현할 수 있습니다.  컴파일 타임에 쿼리 구문은 표준 쿼리 연산자 확장 메서드의 LINQ 공급자 구현에 대한 메서드 호출로 변환됩니다.  응용 프로그램은 `Imports` 문으로 적절한 네임스페이스를 지정하여 범위에 포함할 표준 쿼리 연산자를 제어합니다.  Visual Basic 쿼리 식에 대한 구문은 다음과 같습니다.  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 자세한 내용은 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조하십시오.  
  
## 암시적으로 형식화된 변수  
 변수를 선언하고 초기화할 때 명시적으로 형식을 지정하는 대신 컴파일러가 형식을 유추하여 할당하도록 할 수 있습니다.  이를 *지역 형식 유추*라고 합니다.  
  
 형식이 유추되는 변수는 명시적으로 형식을 지정하는 변수와 마찬가지로 강력한 형식입니다.  지역 형식 유추는 메서드 본문 내에서 지역 변수를 정의할 때만 작동합니다.  자세한 내용은 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조하십시오.  
  
 다음 예제에서는 지역 형식 유추를 사용하는 방법을 보여 줍니다.  이 예제를 사용하려면 `Option Infer`를 `On`으로 설정해야 합니다.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 또한 로컬 형식 유추는 나중에이 절에서 설명 하 고 LINQ 쿼리에 필요한 익명 형식을 만들 수 있습니다.  
  
 다음 LINQ 예제에서는 `Option Infer`가 `On` 또는 `Off`인 경우 형식 유추가 발생합니다.  `Option Infer`가 `Off`이고 `Option Strict`가 `On`이면 컴파일 타임 오류가 발생합니다.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## 개체 이니셜라이저  
 쿼리 결과를 보관해 둘 익명 형식을 만들어야 할 때는 쿼리 식에서 개체 이니셜라이저가 사용됩니다.  또한 쿼리 외부에 있는 명명된 형식의 개체를 초기화하는 데에도 개체 이니셜라이저가 사용될 수 있습니다.  개체 이니셜라이저를 사용하면 생성자를 명시적으로 호출하지 않고도 한 줄로 개체를 초기화할 수 있습니다.  공개 `Name` 및 `Phone` 속성과 다른 속성을 가진 `Customer`라는 클래스가 있다고 가정할 경우 개체 이니셜라이저를 이러한 방식으로 사용할 수 있습니다.  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 자세한 내용은 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)을 참조하십시오.  
  
## 익명 형식  
 익명 형식은 쿼리 결과에 포함시키려는 요소에 속성 집합을 일시적으로 그룹화하는 편리한 방법을 제공합니다.  익명 형식을 사용하면 요소의 명명된 데이터 형식을 정의하지 않고도 쿼리에서 사용할 수 있는 필드의 임의 조합을 원하는 순서로 선택할 수 있습니다.  
  
 *익명 형식*은 컴파일러에서 동적으로 생성됩니다.  형식 이름은 컴파일러에 의해 할당되며 새로 컴파일할 때마다 변경될 수 있습니다.  따라서 이름은 직접 사용할 수 없습니다.  익명 형식은 다음과 같은 방식으로 초기화됩니다.  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  
  
## 확장 메서드  
 확장 메서드를 사용하면 정의 외부에서 데이터 형식이나 인터페이스에 메서드를 추가할 수 있습니다.  이 기능을 사용하면 실제로 형식을 수정하지 않고도 기존 형식에 새 메서드를 추가할 수 있습니다.  표준 쿼리 연산자는 그 자체가 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 모든 형식에 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 기능을 제공하는 확장 메서드 집합입니다. <xref:System.Collections.Generic.IEnumerable%601>에 대한 다른 확장으로는 <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A> 및 <xref:System.Linq.Enumerable.Intersect%2A>가 있습니다.  
  
 다음 확장 메서드는 <xref:System.String> 클래스에 인쇄 메서드를 추가합니다.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 이 메서드는 <xref:System.String>의 일반적인 인스턴스 메서드처럼 호출됩니다.  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 자세한 내용은 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하십시오.  
  
## 람다 식  
 람다 식은 단일 값을 계산하고 반환하는 이름이 없는 함수입니다.  명명된 함수와 달리 람다 식은 동시에 정의하고 실행할 수 있습니다.  다음 예제는 4를 표시합니다.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 변수 이름에 람다 식 정의를 할당한 다음 해당 이름을 사용하여 함수를 호출할 수 있습니다.  다음 예제에서도 4를 표시합니다.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]에서 람다 식은 여러 표준 쿼리 연산자의 기반이 됩니다.  컴파일러는 람다 식을 만들어서 `Where`, `Select`, `Order By`, `Take While` 등의 기본 쿼리 메서드에 정의된 계산을 캡처합니다.  
  
 예를 들어 다음 코드에서는 학생 목록에서 모든 상급반 학생을 반환하는 쿼리를 정의합니다.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 쿼리 정의는 다음 예제와 유사한 코드로 컴파일됩니다. 예제의 코드에서는 두 개의 람다 식을 사용하여 `Where` 및 `Select`에 대한 인수를 지정합니다.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 두 버전 모두 `For Each` 루프를 사용하여 실행할 수 있습니다.  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 자세한 내용은 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하십시오.  
  
## 참고 항목  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ 및 문자열](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [C\# Features That Support LINQ](../../../../csharp/programming-guide/concepts/linq/features-that-support-linq.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)