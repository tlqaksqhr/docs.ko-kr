---
title: "nullable 형식(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, nullable 형식"
  - "nullable 형식[C#]"
  - "형식[C#], nullable"
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 44
---
# nullable 형식(C# 프로그래밍 가이드)
nullable 형식은 <xref:System.Nullable%601?displayProperty=fullName> 구조체의 인스턴스입니다.  nullable 형식은 내부 값 형식의 올바른 값 범위뿐 아니라 `null` 값도 나타낼 수 있습니다.  예를 들어 `Nullable<Int32>`\("Int32의 nullable"이라고 읽음\)에는 \-2147483648에서 2147483647까지의 모든 값을 할당하거나 `null` 값을 할당할 수 있습니다.  `Nullable<bool>`에는 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 또는 [null](../../../csharp/language-reference/keywords/null.md) 값을 할당할 수 있습니다.  숫자 및 부울 형식에 `null` 값을 할당할 수 있는 기능은 특히 값이 할당되지 않을 수 있는 요소를 포함하는 데이터베이스 및 기타 데이터 형식을 다룰 때 유용합니다.  예를 들어 데이터베이스의 Boolean 필드는 `true` 또는 `false` 값을 저장할 수도 있고, 정의되지 않을 수도 있습니다.  
  
 [!code-cs[csProgGuideTypes#3](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_1.cs)]  
  
 이 예제는 다음 출력을 표시합니다.  
  
 `num = Null`  
  
 `Nullable object must have a value.`  
  
 추가 예제는 [Nullable 형식 사용](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)를 참조하십시오.  
  
## nullable 형식 개요  
 nullable 형식에는 다음과 같은 특징이 있습니다.  
  
-   nullable 형식은 `null` 값을 할당할 수 있는 값 형식 변수를 나타냅니다.  참조 형식을 기반으로 nullable 형식을 만들 수는 없습니다.  참조 형식에서는 이미 `null` 값을 지원합니다.  
  
-   `T?` 구문은 <xref:System.Nullable%601>의 축약형이고, 여기서 `T`는 값 형식입니다.  이러한 두 가지 형태는 서로 바꿔 사용할 수 있습니다.  
  
-   nullable 형식에는 일반 값 형식과 같은 방법으로 값을 할당합니다. 예를 들면 `int? x = 10;` 또는 `double? d = 4.108`과 같습니다.  Nullable 형식은 `null`: `int? x = null.` 값을 할당할 수도 있습니다.  
  
-   <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> 메서드를 사용하여 할당된 값을 반환하거나 값이 `null`인 경우 내부 형식의 기본값을 반환합니다. 예를 들면  `int j = x.GetValueOrDefault();`와 같습니다.  
  
-   <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 읽기 전용 속성을 사용하여 Null에 대해 테스트하고 값을 검색합니다\(예제 `if(x.HasValue) j = x.Value;` 참조\).  
  
    -   `HasValue` 속성은 변수에 값이 포함되어 있을 경우 `true`를 반환하고, 변수가 `null`이면 `false`를 반환합니다.  
  
    -   할당된 값이 있으면 `Value` 속성은 값을 반환합니다.  그렇지 않으면 <xref:System.InvalidOperationException?displayProperty=fullName>이 throw됩니다.  
  
    -   `HasValue`의 기본값은 `false`입니다.  `Value` 속성에는 기본값이 없습니다.  
  
    -   `==` and `!=` 연산자를 Nullable 형식으로 사용할 수도 있습니다\(예제 `if (x != null) y = x;` 참조\).  
  
-   `??` 연산자를 사용하여 현재 값이 `null`인 nullable 형식을 nullable이 아닌 형식에 할당할 때 적용될 기본값을 할당합니다. 예를 들면 `int? x = null; int y = x ?? -1;`과 같습니다.  
  
-   중첩된 nullable 형식은 허용되지 않습니다.  `Nullable<Nullable<int>> n;`과 같은 줄은 컴파일되지 않습니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Nullable 형식 사용](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? 연산자](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Nullable>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\#](../../../csharp/csharp.md)   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [평균 정확히 무엇입니까 '리프트'?](http://go.microsoft.com/fwlink/?LinkId=112382)