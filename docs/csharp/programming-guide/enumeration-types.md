---
title: "열거형 형식(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "비트 플래그[C#]"
  - "C# 언어, 열거형"
  - "열거형[C#]"
  - "열거형[C#]"
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 열거형 형식(C# 프로그래밍 가이드)
열거형 형식\(enum이라고도 함\)은 변수에 할당할 수 있는 명명된 정수 상수 집합을 정의하는 효율적인 방법을 제공합니다.  예를 들어, 값이 요일을 나타내는 변수를 정의한다고 가정합니다.  변수에 저장할 수 있는 의미 있는 값은 7개뿐입니다.  이러한 값을 정의하려면 [enum](../../csharp/language-reference/keywords/enum.md) 키워드를 사용하여 선언하는 열거형 형식을 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_1.cs)]  
  
 기본적으로 열거형에서 각 요소의 내부 형식은 [int](../../csharp/language-reference/keywords/int.md)입니다.  이전 예제와 같이 콜론을 사용하여 또 다른 정수 숫자 형식을 지정할 수 있습니다.  사용할 수 있는 모든 형식 목록은 [enum \(C\# Reference\)](../../csharp/language-reference/keywords/enum.md)을 참조하십시오.  
  
 다음 예제 에서처럼 기본 형식으로 캐스팅 하 여 기본 숫자 값을 확인할 수 있습니다.  
  
```c#  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 숫자 형식 대신 열거형을 사용하면 다음과 같은 장점이 있습니다.  
  
-   클라이언트 코드에서 변수에 유효한 값을 명확하게 지정할 수 있습니다.  
  
-   [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)]의 IntelliSense에 정의된 값이 표시됩니다.  
  
 열거자 목록의 요소에 대해 값을 지정하지 않으면 자동으로 값이 1씩 증가합니다.  위 예제에서 `Days.Sunday`는 값 0을 갖고 `Days.Monday`는 값 1을 갖게 되며, 나머지 요소도 이와 같이 값을 갖습니다.  새 `Days` 개체를 만들 때 값을 명시적으로 할당하지 않으면 기본값인 `Days.Sunday`\(0\)를 갖게 됩니다.  열거형을 만들 때 가장 논리적인 기본값을 선택하고 0의 값을 지정하십시오.  그러면 열거형을 생성할 때 명시적으로 값을 할당하지 않은 경우에도 모든 열거형이 해당 기본값을 갖게 됩니다.  
  
 `meetingDay` 변수가 `Days` 형식인 경우 명시적 캐스트를 사용하지 않으면 `Days`로 정의된 값 중 하나만 변수에 할당할 수 있습니다.  모임 날짜가 변경된 경우에는 `Days`에 속하는 새 값을 `meetingDay`에 할당할 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_2.cs)]  
  
> [!NOTE]
>  `meetingDay`에 임의의 정수 값을 할당할 수도 있습니다.  예를 들어, `meetingDay = (Days) 42` 코드 줄은 오류를 생성하지 않습니다.  하지만 암시적인 의도는 열거형 변수에 해당 열거형에 정의된 값 중 하나만 유지하는 것이므로 이렇게 하지 않는 것이 좋습니다.  열거형 형식의 변수에 임의의 값을 할당하면 오류가 발생할 위험이 커집니다.  
  
 열거형 형식의 열거자 목록에 있는 요소에 임의의 값을 할당할 수 있으며 계산된 값을 사용할 수도 있습니다.  
  
 [!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_3.cs)]  
  
## 비트 플래그로 사용하는 열거형 형식  
 열거형 형식을 사용하여 비트 플래그를 정의할 수 있습니다. 이렇게 하면 열거형 형식의 인스턴스를 사용하여 열거자 목록에 정의되어 있는 값의 조합을 저장할 수 있습니다.  물론, 이 경우에도 일부 조합은 의미가 없거나 프로그램 코드에서 허용되지 않을 수 있습니다.  
  
 <xref:System.FlagsAttribute?displayProperty=fullName> 특성을 적용하고 `AND`, `OR`, `NOT` 및 `XOR` 비트 연산을 수행할 수 있는 적절한 값을 정의하여 비트 플래그 열거형을 만듭니다.  비트 플래그 열거형에는 "플래그가 설정되어 있지 않음"을 의미하는 0 값을 갖는 명명된 상수가 포함됩니다. "플래그가 설정되어 있지 않음"을 의미하지 않는 경우에는 플래그에 0 값을 할당하지 마십시오.  
  
 다음 예제에서는 `Days` 열거형의 다른 버전인 `Days2`가 정의되어 있습니다.  `Days2`에는 `Flags` 특성이 있고 각 값에는 지수가 1씩 증가하며 2의 제곱이 할당됩니다.  따라서 사용자는 값이 `Days2.Tuesday` 및 `Days2.Thursday`인 `Days2` 변수를 만들 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_4.cs)]  
  
 열거형에 플래그를 설정하려면 다음 예제와 같이 비트 `OR` 연산자를 사용합니다.  
  
 [!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_5.cs)]  
  
 특정 플래그가 설정되어 있는지 여부를 확인하려면 다음 예제와 같이 비트 `AND` 연산을 사용합니다.  
  
 [!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_6.cs)]  
  
 <xref:System.FlagsAttribute?displayProperty=fullName> 특성이 있는 열거형 형식을 정의할 때 주의해야 할 사항에 대한 자세한 내용은 <xref:System.Enum?displayProperty=fullName>을 참조하십시오.  
  
## System.Enum 메서드를 사용하여 열거형 값 검색 및 조작  
 모든 열거형은 <xref:System.Enum?displayProperty=fullName> 형식의 인스턴스입니다.  <xref:System.Enum?displayProperty=fullName>에서 새 클래스를 파생시킬 수 없지만 해당 메서드를 사용하면 열거형 인스턴스에 대한 정보를 검색하고 값을 조작할 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/csharp/enumeration-types_7.cs)]  
  
 자세한 내용은 <xref:System.Enum?displayProperty=fullName>을 참조하십시오.  
  
 확장 메서드를 사용하여 열거형에 대한 새 메서드를 만들 수도 있습니다.  자세한 내용은 [방법: 새 열거형 메서드 만들기](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)을 참조하십시오.  
  
## 중요 설명서 장  
 [변수에 대 한 자세한](http://go.microsoft.com/fwlink/?LinkId=221230) 에서 [C\# 2010 Visual 시작](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## 참고 항목  
 <xref:System.Enum?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)