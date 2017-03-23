---
title: "명명된 인수와 선택적 인수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "namedParameter_CSharpKeyword"
  - "cs_namedParameter"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인수[C#], 명명됨"
  - "인수[C#], 선택적"
  - "명명된 인수 및 선택적 인수[C#]"
  - "명명된 인수[C#]"
  - "선택적 인수[C#]"
  - "매개 변수[C#], 명명됨"
  - "매개 변수[C#], 선택적"
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# 명명된 인수와 선택적 인수(C# 프로그래밍 가이드)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)]에는 명명된 인수 및 선택적 인수가 도입되어 있습니다.  *명명된 인수*를 사용하면 매개 변수 목록에서의 매개 변수 위치 대신 매개 변수의 이름과 인수를 연결하여 특정 매개 변수에 대한 인수를 지정할 수 있습니다.  *선택적 인수*는 일부 매개 변수에 대한 인수를 생략할 수 있도록 합니다.  이 두 가지 인수는 메서드, 인덱서, 생성자 및 대리자와 함께 사용할 수 있습니다.  
  
 명명된 인수 및 선택적 인수를 사용할 경우 인수가 계산되는 순서는 매개 변수 목록이 아닌 인수 목록에서 인수가 나타나는 순서에 의해 결정됩니다.  
  
 명명된 인수 및 선택적 인수가 함께 사용되면 선택적 매개 변수 목록의 일부 매개 변수에 대해서만 인수를 제공할 수 있습니다.  이 기능 덕분에 Microsoft Office 자동화 API 같은 COM 인터페이스를 매우 쉽게 호출할 수 있습니다.  
  
## 명명된 인수  
 명명된 인수를 사용하면 호출되는 메서드의 매개 변수 목록에 있는 매개 변수의 순서를 기억하거나 확인할 필요가 없게 됩니다.  각 인수에 대한 매개 변수를 지정하려면 매개 변수 이름을 사용하면 됩니다.  예를 들어, BMI\(체질량 지수\)를 계산하는 함수의 경우 해당 함수에 정의된 순서에 따라 체중 및 높이에 대한 인수를 차례로 지정하여 전달하는 표준적인 방법으로 호출될 수 있습니다.  
  
 `CalculateBMI(123, 64);`  
  
 매개 변수 순서를 기억하지 못하거나 매개 변수 이름을 모르면 체중 및 높이에 대한 인수를 순서와 상관없이 보낼 수 있습니다.  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 명명된 인수를 사용하면 각 인수가 무엇을 나타내는지 확인할 수 있으므로 코드 가독성도 향상됩니다.  
  
 명명된 인수는 다음과 같이 위치 인수 뒤에 올 수 있습니다.  
  
 `CalculateBMI(123, height: 64);`  
  
 그러나 위치 인수가 명명된 인수 다음에 올 수는 없습니다.  다음 문은 컴파일러 오류를 발생시킵니다.  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## 예제  
 다음 코드에는 이 단원의 예제가 구현되어 있습니다.  
  
 [!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## 선택적 인수  
 메서드, 생성자, 인덱서 또는 대리자의 정의에서 해당 매개 변수가 필수적인지 선택적인지 지정할 수 있습니다.  호출할 경우 모든 필수적 매개 변수에 대한 인수는 항상 제공해야 하지만 선택적 매개 변수에 대한 인수는 생략할 수 있습니다.  
  
 각 선택적 매개 변수에는 정의의 일부로서 기본값이 있습니다.  해당 매개 변수에 대해 인수를 전달하지 않으면 기본값이 사용됩니다.  기본값 식의 다음 형식 중 하나 여야 합니다.  
  
-   상수 식입니다.  
  
-   폼의 식 `new ValType()`, 어디 `ValType` 값 형식에는  [열거형](../../../csharp/language-reference/keywords/enum.md) 또는  [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md);  
  
-   폼의 식  [default\(ValType\)](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), 어디 `ValType` 는 값 형식입니다.  
  
 선택적 매개 변수는 매개 변수 목록의 끝에, 즉 모든 필수적 매개 변수 뒤에 정의됩니다.  호출자가 첫 번째 선택적 매개 변수 뒤에 있는 선택적 매개 변수에 대해 인수를 제공한 경우 이 매개 변수 앞에 있는 모든 선택적 매개 변수에 대해서도 인수를 제공해야 합니다.  인수 목록에서 쉼표와 쉼표 사이에 공백만 남겨 두는 방법은 지원되지 않습니다.  예를 들어, 다음 코드에서 `ExampleMethod` 인스턴스 메서드는 필수 매개 변수 1개와 선택적 매개 변수 2개를 갖도록 정의됩니다.  
  
 [!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 `ExampleMethod`에 대한 다음 코드에서는 두 번째 매개 변수가 아니라 세 번째 매개 변수에 인수가 제공되기 때문에 컴파일러 오류가 발생합니다.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 그러나 세 번째 매개 변수의 이름을 알고 있으면 명명된 인수를 사용하여 원하는 작업을 수행할 수 있습니다.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 다음 그림과 같이 IntelliSense에서는 괄호를 사용하여 선택적 매개 변수를 표시합니다.  
  
 ![ExampleMethod 메서드에 대한 IntelliSense 요약 정보](../../../csharp/programming-guide/classes-and-structs/media/optional-parameters.png "Optional\_Parameters")  
ExampleMethod의 선택적 매개 변수  
  
> [!NOTE]
>  선택적 매개 변수는 .NET <xref:System.Runtime.InteropServices.OptionalAttribute> 클래스를 사용하여 선언할 수도 있습니다.  `OptionalAttribute` 매개 변수에는 기본값이 필요하지 않습니다.  
  
## 예제  
 다음 예제에서 `ExampleClass`의 생성자에는 하나의 매개 변수가 있고 이 매개 변수는 선택적입니다.  인스턴스 메서드 `ExampleMethod`에는 필수적 매개 변수로 `required` 하나가 있고, 선택적 매개 변수로 `optionalstr` 및 `optionalint` 두 개가 있습니다.  `Main`의 코드에서는 생성자 및 메서드를 호출할 수 있는 여러 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## COM 인터페이스  
 명명된 인수 및 선택적 인수 외에 동적 개체에 대한 지원 및 기타 개선 기능을 사용하면 Office Automation API 같은 COM API와의 상호 운용성이 대폭 향상됩니다.  
  
 예를 들어, Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) 인터페이스의 Microsoft Office Excel [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) 메서드에는 매개 변수가 7개 있고 이들 매개 변수는 모두 선택적입니다.  다음 그림에서는 이러한 매개 변수를 보여 줍니다.  
  
 ![AutoFormat 메서드에 대한 IntelliSense 요약 정보](../../../csharp/programming-guide/classes-and-structs/media/autoformat-parameters.png "AutoFormat\_Parameters")  
AutoFormat 매개 변수  
  
 C\# 3.0 및 이전 버전에서 인수는 다음 예제와 같이 각 매개 변수에 대해 필요합니다.  
  
 [!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 그러나 C\# 4.0에 도입된 명명된 인수 및 선택적 인수를 사용하면 `AutoFormat` 호출을 대폭 단순화할 수 있습니다.  명명된 인수 및 선택적 인수를 사용할 경우 기본값을 변경하지 않을 선택적 매개 변수에 대해서는 인수를 생략할 수 있습니다.  다음 호출에서는 매개 변수 7개 중 하나에 대해서만 값이 지정됩니다.  
  
 [!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 자세한 내용 및 예제를 보려면 [방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) 및 [방법: Visual C\# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)를 참조하십시오.  
  
## 오버로드 확인  
 명명된 인수 및 선택적 인수의 사용은 다음과 같이 오버로드 확인에 영향을 줍니다.  
  
-   메서드, 인덱서 또는 생성자는 각 매개 변수가 모두 선택적인 경우이거나 각 매개 변수가 이름 또는 위치를 기준으로 호출문의 단일 인수와 대응되고 이 인수를 해당 매개 변수의 형식으로 변환할 수 있는 경우에 실행 후보가 됩니다.  
  
-   둘 이상의 후보가 발견되면 기본 설정 변환에 대한 오버로드 확인 규칙은 명시적으로 지정된 인수에 적용됩니다.  선택적 매개 변수의 생략된 인수는 무시됩니다.  
  
-   두 후보 모두 동등한 것으로 평가될 경우에는 호출에서 인수가 생략된 선택적 매개 변수가 없는 후보를 실행합니다.  이는 오버로드 확인에서 매개 변수가 적은 후보를 우선시하는 일반적인 규칙이 적용되기 때문입니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [인덱서 사용](../../../csharp/programming-guide/indexers/using-indexers.md)