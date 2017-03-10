---
title: "형식(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "값 형식[C#]"
  - "참조 형식[C#]"
  - "형식[C#]"
  - "C# 언어, 데이터 형식"
  - "공용 형식 시스템[C#]"
  - "데이터 형식[C#]"
  - "C# 언어, 형식"
  - "강력한 형식화[C#]"
ms.assetid: f782d7cc-035e-4500-b1b1-36a9881130ad
caps.latest.revision: 53
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 53
---
# 형식(C# 프로그래밍 가이드)
## 형식, 변수 및 값  
 C\#은 강력한 형식의 언어입니다.  모든 변수와 상수에는 값으로 평가되는 모든 식과 마찬가지로 형식이 있습니다.  모든 메서드 시그니처에서는 각 입력 매개 변수와 반환 값의 형식을 지정합니다.  .NET Framework 클래스 라이브러리는 기본 제공 숫자 형식 집합을 정의할 뿐 아니라 파일 시스템, 네트워크 연결, 개체 컬렉션 및 배열, 날짜 등의 다양한 논리 구조체를 나타내는 복잡한 형식도 정의합니다.  일반적인 C\# 프로그램에서는 클래스 라이브러리의 형식뿐 아니라 프로그램의 문제 도메인과 관련된 개념을 모델링하는 사용자 정의 형식을 사용합니다.  
  
 형식에는 다음과 같은 정보가 포함될 수 있습니다.  
  
-   형식의 변수에 필요한 저장 공간  
  
-   나타낼 수 있는 최대값 및 최소값  
  
-   포함하는 멤버\(메서드, 필드, 이벤트 등\)  
  
-   상속하는 기본 형식  
  
-   변수에 대한 메모리가 런타임에 할당되는 위치  
  
-   허용되는 작업 유형  
  
 컴파일러는 형식 정보를 사용하여 코드에서 수행되는 모든 작업이 *형식 안전성*을 가지도록 합니다.  예를 들어 [int](../../../csharp/language-reference/keywords/int.md) 형식의 변수를 선언한 경우 컴파일러는 더하기 및 빼기 작업에 해당 변수를 사용하도록 허용합니다.  하지만 다음 예제와 같이 [bool](../../../csharp/language-reference/keywords/bool.md) 형식의 변수에 대해 동일한 작업을 수행하려고 하면 컴파일러에서 오류를 생성합니다.  
  
 [!code-cs[csProgGuideTypes#42](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_1.cs)]  
  
> [!NOTE]
>  C 및 C\+\+ 개발자의 경우 C\#에서는 [bool](../../../csharp/language-reference/keywords/bool.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 변환할 수 없다는 점에 주의해야 합니다.  
  
 컴파일러는 형식 정보를 실행 파일에 메타데이터로 포함합니다.  CLR\(공용 언어 런타임\)에서는 런타임에 메타데이터를 사용하여 메모리를 할당하고 회수할 때 형식 안전성을 보장합니다.  
  
### 변수 선언에서 형식 지정  
 프로그램에서 변수나 상수를 선언하려면 변수나 상수의 형식을 지정하거나 [var](../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 컴파일러가 형식을 유추하도록 해야 합니다.  다음 예제에서는 기본 제공 숫자 형식과 복합 사용자 정의 형식을 모두 사용하는 몇 가지 변수 선언을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#36](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_2.cs)]  
  
 메서드 매개 변수와 반환 값의 형식은 메서드 시그니처에 지정됩니다.  다음 시그니처에서는 입력 인수로 [int](../../../csharp/language-reference/keywords/int.md)를 사용하여 문자열을 반환하는 메서드를 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#35](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_3.cs)]  
  
 변수를 선언한 후에는 새 형식으로 다시 선언할 수 없으며 선언된 형식과 호환되지 않는 값을 변수에 할당할 수 없습니다.  예를 들어, [int](../../../csharp/language-reference/keywords/int.md)를 선언한 다음 여기에 부울 값 [true](../../../csharp/language-reference/keywords/true-literal.md)를 할당할 수 없습니다.  하지만 값을 새 변수에 할당하거나 메서드 인수로 전달하는 경우에는 다른 형식으로 변환할 수 있습니다.  데이터 손실이 발생하지 않는 *형식 변환*은 컴파일러에서 자동으로 수행됩니다.  데이터 손실이 발생할 수 있는 변환을 수행하려면 소스 코드에서 *캐스팅*을 수행해야 합니다.  
  
 자세한 내용은 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)을\(를\) 참조하십시오.  
  
## 기본 제공 형식  
 C\#은 정수, 부동 소수점 값, 부울 식, 텍스트 문자, 10진수 값 및 기타 데이터 형식을 나타내는 기본 제공 숫자 형식의 표준 집합을 제공합니다.  또한 `string` 및 `object` 형식도 기본 제공 형식입니다.  이러한 기본 제공 형식은 모든 C\# 프로그램에서 사용할 수 있습니다.  기본 제공 형식에 대한 자세한 내용은 [형식 참조 테이블](../../../csharp/language-reference/keywords/reference-tables-for-types.md)를 참조하십시오.  
  
## 사용자 지정 형식  
 [struct](../../../csharp/language-reference/keywords/struct.md), [class](../../../csharp/language-reference/keywords/class.md), [interface](../../../csharp/language-reference/keywords/interface.md) 및 [enum](../../../csharp/language-reference/keywords/enum.md) 구문을 사용하여 고유한 사용자 지정 형식을 만들 수 있습니다.  .NET Framework 클래스 라이브러리 자체는 Microsoft에서 제공한 사용자 지정 형식의 컬렉션으로, 사용자 고유의 응용 프로그램에 사용할 수 있습니다.  기본적으로 클래스 라이브러리에서 가장 자주 사용되는 형식은 모든 C\# 프로그램에서 사용할 수 있습니다.  나머지 형식은 형식이 정의된 어셈블리에 프로젝트 참조를 명시적으로 추가한 경우에만 사용할 수 있습니다.  컴파일러에 어셈블리에 대한 참조가 있으면 소스 코드에서 해당 어셈블리에 선언된 형식의 변수 및 상수를 선언할 수 있습니다.  자세한 내용은 [.NET Framework 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=217856)를 참조하십시오.  
  
## 공용 형식 시스템  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 형식 시스템에 대한 두 가지 기본적인 사항을 알고 있어야 합니다.  
  
-   상속의 원칙이 지원됩니다.  형식은 *기본 형식*이라는 다른 형식에서 파생될 수 있습니다.  약간의 제한이 따르지만 파생 형식은 기본 형식의 메서드, 속성 및 기타 멤버를 상속합니다.  파생 형식이 상속 계층 구조의 두 기본 형식의 멤버를 상속하는 경우 기본 형식은 일부 다른 형식에서 파생될 수 있습니다.  <xref:System.Int32?displayProperty=fullName>\(C\# 키워드: [int](../../../csharp/language-reference/keywords/int.md)\)와 같은 기본 제공 숫자 형식을 비롯한 모든 형식은 궁극적으로 <xref:System.Object?displayProperty=fullName>\(C\# 키워드: [object](../../../csharp/language-reference/keywords/object.md)\)라는 단일 기본 형식에서 파생됩니다.  이 통합 형식 계층 구조를 CTS\([공용 형식 시스템](../../../standard/base-types/common-type-system.md)\)라고 합니다.  C\#의 상속에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하십시오.  
  
-   CTS의 각 형식은 *값 형식*이나 *참조 형식*으로 정의되어 있습니다.  여기에는 .NET Framework 클래스 라이브러리의 모든 사용자 지정 형식과 사용자 고유의 사용자 정의 형식이 포함됩니다.  [struct](../../../csharp/language-reference/keywords/struct.md) 키워드를 사용하여 정의한 형식은 값 형식이며 모든 기본 제공 숫자 형식은 `structs`입니다.  [class](../../../csharp/language-reference/keywords/class.md) 키워드를 사용하여 정의한 형식은 참조 형식입니다.  참조 형식과 값 형식의 컴파일 타임 규칙은 서로 다르며 런타임 동작도 서로 다릅니다.  
  
 다음 그림에서는 CTS에서 값 형식과 참조 형식 간의 관계를 보여 줍니다.  
  
 ![값 형식과 참조 형식](../../../csharp/programming-guide/types/media/valuetypescts.png "ValueTypesCTS")  
CTS의 값 형식과 참조 형식  
  
> [!NOTE]
>  가장 일반적으로 사용되는 형식은 <xref:System> 네임스페이스에 구성되어 있다는 것을 알 수 있습니다.  하지만 형식이 포함된 네임스페이스는 값 형식인지 참조 형식인지와는 관계가 없습니다.  
  
### 값 형식  
 값 형식은 <xref:System.Object?displayProperty=fullName>에서 파생된 <xref:System.ValueType?displayProperty=fullName>에서 파생됩니다.  <xref:System.ValueType?displayProperty=fullName>에서 파생된 형식은 CLR에서 특수하게 동작합니다.  값 형식 변수는 값을 직접 가지고 있습니다. 즉, 값이 선언된 컨텍스트와 상관없이 메모리가 인라인으로 할당됩니다.  값 형식 변수의 경우 별도의 힙 할당이나 가비지 수집 오버헤드가 없습니다.  
  
 값 형식에는 [구조체](../../../csharp/language-reference/keywords/struct.md)와 [열거형](../../../csharp/language-reference/keywords/enum.md)이라는 두 가지 범주가 있습니다.  
  
 기본 제공 숫자 형식은 struct이며 다음과 같이 액세스할 수 있는 속성과 메서드를 가집니다.  
  
```c#  
// Static method on type Byte.  
byte b = Byte.MaxValue;  
```  
  
 그러나 간단한 비집계 형식처럼 형식을 선언하고 값을 형식에 할당할 수 있습니다.  
  
```c#  
byte num = 0xA;  
int i = 5;  
char c = 'Z';  
```  
  
 값 형식은 *봉인*됩니다. 즉, 구조체는 <xref:System.ValueType?displayProperty=fullName>에서만 상속할 수 있으므로 <xref:System.Int32?displayProperty=fullName>에서 특정 형식을 파생할 수 없으며 다른 사용자 정의 클래스나 구조체에서 상속하는 구조체를 정의할 수 없습니다.  그러나 구조체는 하나 이상의 인터페이스를 구현할 수 있습니다.  구조체 형식을 인터페이스 형식으로 캐스팅할 수 있지만 이 경우 관리되는 힙에서 참조 형식 개체 내부에 구조체를 래핑하는 *boxing* 작업이 수행됩니다.  boxing 작업은 <xref:System.Object?displayProperty=fullName>를 입력 매개 변수로 사용하는 메서드에 값 형식을 전달할 때 발생합니다.  자세한 내용은 [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)을\(를\) 참조하십시오.  
  
 [struct](../../../csharp/language-reference/keywords/struct.md) 키워드를 사용하여 고유한 사용자 지정 값 형식을 만들 수 있습니다.  구조체는 일반적으로 다음 예제에서와 같이 관련 변수의 작은 집합에 대한 컨테이너로 사용됩니다.  
  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/index_4.cs)]  
  
 구조체에 대한 자세한 내용은 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)를 참조하십시오.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 값 형식에 대한 자세한 내용은 [공용 형식 시스템](../../../standard/base-types/common-type-system.md)을 참조하십시오.  
  
 값 형식의 다른 범주는 [열거형](../../../csharp/language-reference/keywords/enum.md)입니다.  열거형은 명명된 정수 상수 집합을 정의합니다.  예를 들어, .NET Framework 클래스 라이브러리의 <xref:System.IO.FileMode?displayProperty=fullName> 열거형에는 파일을 여는 방법이 지정된 명명된 상수 정수의 집합이 포함되어 있습니다.  이 열거형은 다음 예제와 같이 정의되어 있습니다.  
  
 [!code-cs[csProgGuideTypes#44](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_5.cs)]  
  
 `System.IO.FileMode.Create` 상수 값은 2입니다.  하지만 소스 코드를 읽는 사람에게는 이름이 훨씬 의미가 있으므로 상수 리터럴 숫자 대신 열거형을 사용하는 것이 좋습니다.  자세한 내용은 <xref:System.IO.FileMode?displayProperty=fullName>을\(를\) 참조하십시오.  
  
 모든 열거형은 <xref:System.ValueType?displayProperty=fullName>에서 상속하는 <xref:System.Enum?displayProperty=fullName>에서 상속됩니다.  구조체에 적용되는 모든 규칙이 열거형에도 적용됩니다.  열거형에 대한 자세한 내용은 [열거형](../../../csharp/programming-guide/enumeration-types.md)을 참조하십시오.  
  
### 참조 형식  
 [class](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md) 또는 [interface](../../../csharp/language-reference/keywords/interface.md)로 정의된 형식은 *참조 형식*입니다.  참조 형식의 변수를 선언한 경우 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 개체의 인스턴스를 명시적으로 만들거나 `new, as shown in the following example:`을 사용하여 다른 곳에서 만들어진 개체를 변수에 할당할 때까지 해당 변수는 런타임에 [null](../../../csharp/language-reference/keywords/null.md) 값을 갖게 됩니다.  
  
```c#  
MyClass mc = new MyClass();  
MyClass mc2 = mc;  
```  
  
 인터페이스는 인터페이스를 구현하는 클래스 개체와 함께 초기화해야 합니다.  `MyClass`가 `IMyInterface`를 구현하는 경우 다음 예제에서와 같이 `IMyInterface`의 인스턴스를 만듭니다.  
  
```c#  
IMyInterface iface = new MyClass();  
```  
  
 개체를 생성하면 관리되는 힙에 메모리가 할당되고 변수는 개체 위치에 대한 참조만 유지합니다.  관리되는 힙의 형식은 할당될 때와 *가비지 수집*으로 알려진 CLR의 자동 메모리 관리 기능에 의해 메모리가 회수될 때 모두 오버헤드가 발생합니다.  하지만 가비지 수집 역시 상당히 최적화되어 있으므로 대부분의 시나리오에서 성능 문제를 일으키지 않습니다.  가비지 수집에 대한 자세한 내용은 [자동 메모리 관리](../Topic/Automatic%20Memory%20Management.md)를 참조하십시오.  
  
 모든 배열은 참조 형식입니다. 배열의 요소가 값 형식인 경우에도 마찬가지입니다.  배열은 <xref:System.Array?displayProperty=fullName> 클래스에서 암시적으로 파생되지만 다음 예제와 같이 C\#에서 제공하는 단순 구문을 통해 선언되고 사용됩니다.  
  
 [!code-cs[csProgGuideTypes#45](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_6.cs)]  
  
 참조 형식은 상속을 완전하게 지원합니다.  클래스를 만들 때 [sealed](../../../csharp/language-reference/keywords/sealed.md)로 정의되지 않은 다른 인터페이스나 클래스에서 상속할 수 있으며 다른 클래스가 사용자 클래스를 상속하고 사용자 가상 메서드를 재정의할 수 있습니다.  사용자 고유 클래스를 만드는 방법에 대한 자세한 내용은 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)를 참조하십시오.  상속 및 가상 메서드에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하십시오.  
  
## 리터럴 값 형식  
 C\#에서 리터럴 값은 컴파일러에서 형식을 받습니다.  숫자 끝에 문자를 추가하면 숫자 리터럴의 형식이 지정되는 방식을 지정할 수 있습니다.  예를 들어 4.56이라는 값이 float로 처리되도록 지정하려면 `4.56f`와 같이 숫자 끝에 "f" 또는 "F"를 추가합니다.  문자를 추가하지 않으면 컴파일러가 리터럴의 형식을 유추합니다.  문자 접미사를 사용하여 지정할 수 있는 형식에 대한 자세한 내용은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)에서 개별 형식에 대한 참조 페이지를 참조하십시오.  
  
 리터럴에 형식이 지정되고 모든 형식은 궁극적으로 <xref:System.Object?displayProperty=fullName>에서 파생되므로 다음과 같은 코드를 작성하고 컴파일할 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#37](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/index_7.cs)]  
  
## 제네릭 형식  
 클라이언트 코드에서 형식의 인스턴스를 만들 때 제공하는 실제 형식\(*구체적 형식*\)의 자리 표시자로 사용되는 하나 이상의 *형식 매개 변수*를 사용하여 형식을 선언할 수 있습니다.  이러한 형식을 *제네릭 형식*이라고 합니다.  예를 들어, .NET Framework 형식 <xref:System.Collections.Generic.List%601?displayProperty=fullName>에는 규칙에 따라 이름 *T*가 지정되는 형식 매개 변수 한 개가 있습니다.  형식의 인스턴스를 만들 경우 목록에 포함될 개체의 형식을 지정합니다. 문자열을 예로 들면 다음과 같습니다.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 형식 매개 변수를 사용하면 각 요소를 [개체](../../../csharp/language-reference/keywords/object.md)로 변환하지 않고도 동일한 클래스를 다시 사용하여 요소의 형식을 저장할 수 있습니다.  예를 들어, 이전 예제의 `strings` 개체에 정수를 추가하려는 경우 컴파일러가 컬렉션 요소의 특정 형식을 알고 있고 컴파일 타임에 오류가 발생할 수 있으므로 제네릭 컬렉션 클래스는 *강력한 형식의 컬렉션*이라고 합니다.  자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을\(를\) 참조하십시오.  
  
## 암시적 형식, 익명 형식 및 Nullable 형식  
 앞서 설명한 것처럼 [var](../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 로컬 변수\(클래스 멤버는 제외\)에 암시적으로 형식을 지정할 수 있습니다.  변수의 형식은 마찬가지로 컴파일 타임에 결정되지만 컴파일러가 해당 형식을 제공합니다.  자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을\(를\) 참조하십시오.  
  
 경우에 따라서는 메서드 경계 외부에 저장하거나 전달하지 않는 관련 값의 단순 집합에 대해 명명된 형식을 만드는 것은 불편할 수 있습니다.  이러한 경우 *익명 형식*을 만들 수 있습니다.  자세한 내용은 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하십시오.  
  
 일반 값 형식은 [null](../../../csharp/language-reference/keywords/null.md) 값을 가질 수 없지만  형식 다음에 `?`를 추가하면 null 허용 값 형식을 만들 수 있습니다.  예를 들어 `int?`는 [null](../../../csharp/language-reference/keywords/null.md) 값을 가질 수 있는 `int` 형식입니다.  CTS에서 null 허용 형식은 제네릭 구조체 형식 <xref:System.Nullable%601?displayProperty=fullName>의 인스턴스입니다.  nullable 형식은 데이터베이스에서 데이터를 주고받는 경우와 같이 숫자 값이 null일 수 있는 경우에 유용하게 사용할 수 있습니다.  자세한 내용은 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)을\(를\) 참조하십시오.  
  
## 관련 단원  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
  
-   [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)  
  
-   [값 형식](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
  
-   [제네릭](../../../csharp/programming-guide/generics/index.md)  
  
-   [Visual C\# 2010 시작](http://go.microsoft.com/fwlink/?LinkId=221214)의 [변수 및 식](http://go.microsoft.com/fwlink/?LinkId=221228)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [XML 데이터 형식 변환](../Topic/Conversion%20of%20XML%20Data%20Types.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)