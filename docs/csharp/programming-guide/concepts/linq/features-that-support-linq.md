---
title: "LINQ를 지원하는 C# 기능"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2f5accb188e54e0d3e2b941832637ec33afc26b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="c-features-that-support-linq"></a>LINQ를 지원하는 C# 기능
다음 섹션에서는 C# 3.0에 도입된 새로운 언어 구문을 소개합니다. 이러한 새 기능은 모두 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서 어느 정도 사용되지만 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]로 제한되지 않고 유용한 모든 컨텍스트에서 사용할 수 있습니다.  
  
## <a name="query-expressions"></a>쿼리 식  
 쿼리 식은 SQL이나 XQuery와 유사한 선언적 구문을 사용하여 IEnumerable 컬렉션을 쿼리합니다. 컴파일 시간에 쿼리 구문은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자의 표준 쿼리 연산자 확장 메서드 구현에 대한 메서드 호출로 변환됩니다. 응용 프로그램은 `using` 지시문으로 적절한 네임스페이스를 지정하여 범위 내에 있는 표준 쿼리 연산자를 제어합니다. 다음 쿼리 식은 문자열의 배열을 사용하고 문자열의 첫 번째 문자에 따라 그룹화하며 그룹의 순서를 지정합니다.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 자세한 내용은 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)을 참조하세요.  
  
## <a name="implicitly-typed-variables-var"></a>암시적으로 형식화된 변수(var)  
 변수를 선언하고 초기화할 때 명시적으로 형식을 지정하는 대신 다음과 같이 [var](../../../../csharp/language-reference/keywords/var.md) 한정자를 사용하여 형식을 유추하고 할당하도록 컴파일러에 지시할 수 있습니다.  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 `var`로 선언된 변수는 형식을 명시적으로 지정한 변수만큼 강력한 형식입니다. `var`을 사용하면 무명 형식을 만들 수 있지만 모든 지역 변수에 사용할 수 있습니다. 배열은 암시적 형식 지정을 사용하여 선언할 수도 있습니다.  
  
 자세한 내용은 [암시적으로 형식화된 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.  
  
## <a name="object-and-collection-initializers"></a>개체 및 컬렉션 이니셜라이저  
 개체 및 컬렉션 이니셜라이저를 사용하면 개체에 대한 생성자를 명시적으로 호출하지 않고 개체를 초기화할 수 있습니다. 일반적으로 이니셜라이저는 소스 데이터를 새 데이터 형식으로 프로젝션할 때 쿼리 식에서 사용됩니다. public `Name` 및 `Phone` 속성이 있는 `Customer`라는 클래스를 가정할 경우 다음 코드에서처럼 개체 이니셜라이저를 사용할 수 있습니다.  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하세요.  
  
## <a name="anonymous-types"></a>익명 형식  
 무명 형식은 컴파일러에서 생성되며 형식 이름은 컴파일러에서만 사용할 수 있습니다. 무명 형식은 별도의 명명된 형식을 정의하지 않고 쿼리 결과에서 일시적으로 속성 집합을 그룹화하는 편리한 방법을 제공합니다. 무명 형식은 다음과 같이 새로운 식과 개체 이니셜라이저를 사용하여 초기화됩니다.  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 자세한 내용은 [무명 형식](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요.  
  
## <a name="extension-methods"></a>확장명 메서드  
 확장 메서드는 형식과 연결하여 형식에 대한 인스턴스 메서드인 것처럼 호출할 수 있는 정적 메서드입니다. 이 기능을 사용하면 실제로 수정하지 않고도 기존 형식에 새 메서드를 "추가"할 수 있습니다. 표준 쿼리 연산자는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 모든 형식에 대해 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 기능을 제공하는 확장 메서드 집합입니다.  
  
 자세한 내용은 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.  
  
## <a name="lambda-expressions"></a>람다 식  
 람다 식은 => 연산자를 사용하여 함수 본문에서 입력 매개 변수를 구분하는 인라인 함수이며 컴파일 시간에 대리자나 식 트리로 변환할 수 있습니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 프로그래밍에서는 표준 쿼리 연산자에 대한 메서드를 직접 호출할 때 람다 식이 나타납니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [익명 함수](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [람다 식](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [식 트리(C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>자동으로 구현된 속성  
 자동으로 구현된 속성을 통해 속성을 보다 간단하게 선언할 수 있습니다. 다음 예제와 같이 속성을 선언할 때 컴파일러는 getter 및 setter 속성을 통해서만 액세스할 수 있는 전용 무명 지원 필드를 만듭니다.  
  
```  
public string Name {get; set;}  
```  
  
 자세한 내용은 [자동으로 구현된 속성](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ(Language-Integrated Query)(C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
