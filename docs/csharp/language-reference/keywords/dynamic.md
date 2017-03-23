---
title: "dynamic(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "dynamic_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "동적[C#]"
  - "동적 키워드[C#]"
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# dynamic(C# 참조)
`dynamic` 형식을 사용하면 컴파일 타임 형식 검사를 무시하는 작업을 수행할 수 있습니다.  대신, 이러한 작업은 런타임에 확인됩니다.  `dynamic` 형식은 Office Automation API와 같은 COM API, IronPython 라이브러리와 같은 동적 API 및 HTML DOM\(문서 개체 모델\)에 대한 액세스를 간소화합니다.  
  
 형식 `dynamic`은 대부분의 환경에서 형식 `object` 같이 동작합니다.  그러나 형식 `dynamic`의 식이 포함된 작업은 컴파일러에서 형식이 확인되지 않습니다.  컴파일러는 작업에 대한 정보를 함께 패키지하고 해당 정보는 나중에 런타임에서 작업을 평가하는 데 사용됩니다.  프로세스의 일부로 변수 형식 `dynamic`이 `object` 형식 변수에 컴파일됩니다.  따라서 형식 `dynamic`은 런타임이 아닌 컴파일 타임에만  존재합니다.  
  
 다음 예제는 형식 `dynamic`의 변수를 형식 `object`의 변수와 대조합니다.  컴파일 시간에 각 변수 형식을 확인하려면 `WriteLine` 문에서 `dyn` 또는 `obj` 위에 마우스 포인터를 올려 놓습니다.  IntelliSense는 `dyn`에 대해 **동적**을, `obj`에 대해 **개체**를 보여줍니다.  
  
 [!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 `WriteLine` 문은 `dyn` 및 `obj`의 런타임 형식을 표시합니다.  이 시점에서는 모두 동일한 형식 정수입니다.  다음 출력이 생성됩니다.  
  
 `System.Int32`  
  
 `System.Int32`  
  
 컴파일 시간에 `dyn` 및 `obj` 사이의 차이를 확인하려면 앞의 예제에서 선언과 `WriteLine` 문 사이에 다음 두 줄을 추가합니다.  
  
```c#  
dyn = dyn + 3;  
obj = obj + 3;  
  
```  
  
 식 `obj + 3`에 정수와 개체를 추가하려고 시도한 경우 컴파일러 오류가 보고됩니다.  그러나 `dyn + 3`에 대해서는 오류가 보고되지 않습니다.  `dyn`이 포함된 식은 `dyn`의 형식이 `dynamic`이기 때문에 컴파일할 때 확인되지 않습니다.  
  
## 컨텍스트  
 `dynamic` 키워드는 다음과 같은 경우에 직접 또는 생성된 형식의 구성 요소로 나타날 수 있습니다.  
  
-   선언에서 속성, 필드, 인덱서, 매개 변수, 반환 값, 지역 변수 또는 형식 제약 조건의 입력으로 사용합니다.  다음 클래스 정의는 여러 다른 선언에서 `dynamic`을 사용합니다.  
  
     [!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   명시적 형식 변환에서 변환의 대상 형식으로 사용합니다.  
  
     [!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   모든 컨텍스트에서 형식은 `is` 연산자 또는 `as` 연산자의 오른쪽에 있는 것 같은 값 또는 생성된 형식의 일부로 `typeof`에 대한 인수로 사용됩니다.  예를 들어, `dynamic`을 다음 식에 사용할 수 있습니다.  
  
     [!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## 예제  
 다음 예제의 여러 선언에서 `dynamic`을 사용합니다.  `Main` 메서드는 또한 컴파일 타임 형식 검사를 런타임 형식 검사와 대조합니다.  
  
 [!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 자세한 내용과 예제를 보려면 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Dynamic.ExpandoObject?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [방법: AS 및 IS 연산자를 사용한 안전한 캐스팅](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)   
 [연습: 동적 개체 만들기 및 사용](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)