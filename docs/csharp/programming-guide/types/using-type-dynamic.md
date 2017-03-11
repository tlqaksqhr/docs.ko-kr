---
title: "dynamic 형식 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "동적[C#], 동적 형식 정보"
  - "동적 형식[C#]"
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# dynamic 형식 사용(C# 프로그래밍 가이드)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)]에는 `dynamic`이라는 새 형식이 도입되어 있습니다.  `dynamic` 형식은 정적 형식이지만 이 형식의 개체는 정적 형식 검사에서 제외됩니다.  대부분의 경우 이 형식의 개체는 `object` 형식의 개체처럼 작동합니다.  `dynamic` 형식의 요소는 컴파일 타임에 모든 작업을 지원하는 것으로 가정됩니다.  따라서 이 형식의 개체에서 값을 가져오는 소스가 COM API, IronPython 같은 동적 언어, HTML DOM\(문서 개체 모델\), 리플렉션 또는 프로그램 내의 다른 위치인지 신경 쓰지 않아도 됩니다.  그러나 코드가 잘못된 경우에는 런타임에 오류가 catch됩니다.  
  
 예를 들어, 다음 코드의 인스턴스 메서드 `exampleMethod1`에 매개 변수가 하나뿐인 경우 이 메서드에 대한 첫 번째 호출 `ec.exampleMethod1(10, 4)`에 인수가 2개 포함되어 있기 때문에 컴파일러에서는 이 호출이 잘못된 것으로 인식합니다.  따라서 이 호출로 인해 컴파일러 오류가 발생합니다.  동일한 메서드에 대한 두 번째 호출 `dynamic_ec.exampleMethod1(10, 4)`에서는 `dynamic_ec`의 형식이 `dynamic`이기 때문에 컴파일러에서 검사를 수행하지 않습니다.  따라서 컴파일러 오류가 보고되지 않습니다.  그러나 오류가 계속 보고되지 않는 것은 아닙니다.  해당 오류는 런타임에 catch되어 런타임 예외를 발생시킵니다.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_2.cs)]  
  
 이러한 예제에서 컴파일러가 수행하는 역할은 `dynamic` 형식의 개체 또는 식에 대해 어떤 문을 실행할지에 대한 정보를 패키지하는 것입니다.  저장된 정보는 런타임에 검사되며 잘못된 문이 있으면 런타임 예외가 발생합니다.  
  
 가장 동적인 작업의 결과는 `dynamic` 자체입니다.  예를 들어, 다음 예제에서 `testSum`을 사용하여 마우스 포인터의 위치가 결정되도록 하면 IntelliSense에서는 **\(지역 변수\) dynamic testSum** 형식을 표시합니다.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_3.cs)]  
  
 결과가 `dynamic`이 아닌 작업으로는 `dynamic`에서 다른 형식으로의 변환, `dynamic` 형식의 인수를 포함하는 생성자 호출 등이 있습니다.  예를 들어, 다음 선언에서 `testInstance`의 형식은 `dynamic`이 아니라 `ExampleClass`입니다.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_4.cs)]  
  
 변환 예제는 다음 단원 "변환"에서 확인할 수 있습니다.  
  
## 변환  
 동적 개체와 다른 형식 간의 변환은 간단한 편입니다.  따라서 개발자는 동적인 동작과 비동적인 동작 사이에서 쉽게 전환할 수 있습니다.  
  
 모든 개체는 다음 예제와 같이 암시적으로 동적인 형식으로 변환될 수 있습니다.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_5.cs)]  
  
 반대로 암시적 변환이 `dynamic` 형식의 모든 식에 동적으로 적용될 수 있습니다.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_6.cs)]  
  
## 동적 형식의 인수로 오버로드 확인  
 메서드 호출의 인수 중 하나 이상이 `dynamic` 형식이거나 메서드 호출의 수신자가 `dynamic` 형식인 경우 오버로드 확인은 컴파일 타임이 아니라 런타임에 발생합니다.  다음 예제에서 액세스 가능한 유일한 메서드인 `exampleMethod2`가 문자열 인수를 받도록 정의되어 있으면 `d1`을 인수로 전달할 경우 컴파일러 오류는 발생하지 않지만 런타임 예외는 발생하게 됩니다.  `d1`의 런타임 형식은 `int`이고 `exampleMethod2`에 필요한 인수는 문자열이므로 런타임에 오버로드 확인은 실패하게 됩니다.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_7.cs)]  
  
## 동적 언어 런타임  
 DLR\(동적 언어 런타임\)은 [!INCLUDE[net_v40_short](../../../csharp/programming-guide/types/includes/net-v40-short-md.md)]의 새 API입니다.  이 API는 C\#의 `dynamic` 형식 및 IronPython과 IronRuby 같은 동적 프로그래밍 언어의 구현을 지원하는 인프라를 제공합니다.  DLR에 대한 자세한 내용은 [동적 언어 런타임 개요](../Topic/Dynamic%20Language%20Runtime%20Overview.md)를 참조하십시오.  
  
## COM Interop  
 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)]에는 COM API와의 상호 운용 환경을 개선하는 Office Automation API 등의 여러 기능이 포함되어 있습니다.  개선된 기능으로는 `dynamic` 형식 사용, [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) 사용 등이 있습니다.  
  
 여러 COM 메서드에서는 인수 형식 및 반환 형식을 `object`로 지정하여 해당 형식의 변형을 허용합니다.  C\#에서 형식을 변환하려면 강력한 형식의 변수에 맞게 값을 명시적으로 캐스팅해야 합니다.  그러나 이제는 `dynamic` 형식이 도입되었으므로 [\/link \(Link to COM Assembly\)](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 옵션을 사용하여 컴파일할 경우 COM 시그니처의 `object`를 `dynamic` 형식처럼 취급할 수 있고 캐스팅이 거의 필요하지 않습니다.  예를 들어, 다음 문에서는 Microsoft Office Excel 스프레드시트의 셀에 액세스할 때 `dynamic` 형식을 사용하는 방법과 `dynamic` 형식을 사용하지 않는 방법을 비교해 보여 줍니다.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#12)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#13)]  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[동적](../../../csharp/language-reference/keywords/dynamic.md)|`dynamic` 키워드의 사용법에 대해 설명합니다.|  
|[동적 언어 런타임 개요](../Topic/Dynamic%20Language%20Runtime%20Overview.md)|DLR, 즉 동적 언어에 대한 일련의 서비스를 CLR\(공용 언어 런타임\)에 추가하는 런타임 환경의 개요를 제공합니다.|  
|[연습: 동적 개체 만들기 및 사용](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|사용자 지정 동적 개체를 만들고 `IronPython` 라이브러리에 액세스하는 프로젝트를 만드는 방법을 단계별로 설명합니다.|  
|[방법: Visual C\# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|명명된 인수 및 선택적 인수, `dynamic` 형식, Office API 개체에 대한 액세스를 단순화하는 기타 개선 기능을 사용하는 프로젝트를 만드는 방법을 보여 줍니다.|