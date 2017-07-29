---
title: "열거형 형식(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a>열거형 형식(C# 프로그래밍 가이드)
열거형 형식(열거형이라고도 함)은 변수에 할당할 수 있는 명명된 정수 계열 상수 집합을 정의하는 효율적인 방법을 제공합니다. 예를 들어 값이 요일을 나타내는 변수를 정의해야 한다고 가정합니다. 해당 변수에 저장할 수 있는 의미 있는 값이 7개만 있습니다. 이러한 값을 정의하려면 [enum](../../csharp/language-reference/keywords/enum.md) 키워드를 사용하여 선언되는 열거형 형식을 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]  
  
 기본적으로 열거형에서 각 요소의 기본 형식은 [int](../../csharp/language-reference/keywords/int.md)입니다. 이전 예제와 같이 콜론을 사용하여 다른 정수 계열 숫자 형식을 지정할 수 있습니다. 가능한 형식의 전체 목록은 [enum(C# 참조)](../../csharp/language-reference/keywords/enum.md)을 참조하세요.  
  
 다음 예제와 같이 기본 형식으로 캐스트하여 기본 숫자 값을 확인할 수 있습니다.  
  
```csharp  
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
  
 다음은 숫자 형식 대신 열거형을 사용할 경우의 장점입니다.  
  
-   클라이언트 코드에 대해 변수에 유효한 값을 명확하게 지정합니다.  
  
-   [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에서 IntelliSense는 정의된 값 목록을 표시합니다.  
  
 열거자 목록의 요소에 대해 값을 지정하지 않으면 값이 자동으로 1씩 증가합니다. 이전 예제에서 `Days.Sunday`의 값은 0이고, `Days.Monday`의 값은 1이 되는 식입니다. 새 `Days` 개체를 만드는 경우 값을 명시적으로 지정하지 않으면 기본값 `Days.Sunday`(0)가 됩니다. 열거형을 만들 때 가장 논리적인 기본값을 선택하고 0 값을 지정합니다. 그러면 열거형을 만들 때 값을 명시적으로 지정하지 않은 경우 모든 열거형에 해당 기본값이 지정됩니다.  
  
 `meetingDay` 변수가 `Days` 형식이면 명시적 캐스트 없이 `Days`에 정의된 값 중 하나만 할당할 수 있습니다. 또한 모임 날짜가 변경될 경우 `Days`에서 `meetingDay` 사이의 새 값을 할당할 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]  
  
> [!NOTE]
>  임의의 정수 값을 `meetingDay`에 할당할 수 있습니다. 예를 들어 `meetingDay = (Days) 42` 코드 줄은 오류를 생성하지 않습니다. 그러나 열거형 변수는 enum에 정의된 값 중 하나만 포함한다는 암시적 기대로 인해 이렇게 하면 안 됩니다. 열거형 형식의 변수에 임의의 값을 할당하면 오류가 발생할 위험이 높아집니다.  
  
 열거형 형식의 열거자 목록에 있는 요소에 값을 할당하고 계산된 값을 사용할 수도 있습니다.  
  
 [!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]  
  
## <a name="enumeration-types-as-bit-flags"></a>비트 플래그로서 열거형 형식  
 열거형 형식을 사용하여 비트 플래그를 정의할 수 있으며, 그러면 열거형 형식의 인스턴스에서 열거자 목록에 정의된 값의 조합을 저장할 수 있습니다. 물론, 일부 조합은 의미가 없거나 프로그램 코드에서 허용되지 않을 수 있습니다.  
  
 `AND`, `OR`, `NOT` 및 `XOR` 비트 연산을 수행할 수 있도록 <xref:System.FlagsAttribute?displayProperty=fullName> 특성을 적용하고 적절히 값을 정의하여 비트 플래그 열거형을 만듭니다. 비트 플래그 열거형에서 "플래그가 설정되지 않음"을 의미하는 0 값을 갖는 명명된 상수를 포함합니다. 0 값이 "플래그가 설정되지 않음"을 의미하지 않는 경우 이 값을 플래그에 지정하지 마세요.  
  
 다음 예제에서는 `Days2`라는 다른 버전의 `Days` 열거형을 정의합니다. `Days2`에는 `Flags` 특성이 있고 각 값에는 다음으로 큰 2의 거듭제곱이 할당됩니다. 따라서 값이 `Days2.Tuesday` 및 `Days2.Thursday`인 `Days2` 변수를 만들 수 있습니다.  
  
 [!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]  
  
 열거형에서 플래그를 설정하려면 다음 예제와 같이 비트 `OR` 연산자를 사용합니다.  
  
 [!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]  
  
 특정 플래그가 설정되어 있는지 확인하려면 다음 예제와 같이 비트 `AND` 연산을 사용합니다.  
  
 [!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]  
  
 <xref:System.FlagsAttribute?displayProperty=fullName> 특성을 사용하여 열거형 형식을 정의할 때 고려할 사항에 대한 자세한 내용은 <xref:System.Enum?displayProperty=fullName>을 참조하세요.  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>System.Enum 메서드를 사용하여 열거형 값 검색 및 조작  
 모든 열거형은 <xref:System.Enum?displayProperty=fullName> 형식의 인스턴스입니다. <xref:System.Enum?displayProperty=fullName>에서 새 클래스를 파생시킬 수는 없지만 해당 메서드를 사용하여 열거형 인스턴스에서 값에 대한 정보를 검색하고 값을 조작할 수는 있습니다.  
  
 [!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]  
  
 자세한 내용은 <xref:System.Enum?displayProperty=fullName>을 참조하십시오.  
  
 또한 확장 메서드를 사용하여 열거형에 대한 새 메서드를 만들 수 있습니다. 자세한 내용은 [방법: 새 열거형 메서드 만들기](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)를 참조하세요.  

## <a name="see-also"></a>참고 항목  
 <xref:System.Enum?displayProperty=fullName>   
 [C# 프로그래밍 가이드](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)

