---
title: "정적 클래스 및 정적 클래스 멤버(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 정적 클래스"
  - "C# 언어, 정적 멤버"
  - "정적 클래스 멤버[C#]"
  - "정적 클래스[C#]"
  - "정적 멤버[C#]"
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 49
---
# 정적 클래스 및 정적 클래스 멤버(C# 프로그래밍 가이드)
[static](../../../csharp/language-reference/keywords/static.md) 클래스는 기본적으로 static이 아닌 클래스와 동일하지만 인스턴스화할 수 없다는 한 가지 차이점이 있습니다.  즉 [new](../../../csharp/language-reference/keywords/new.md) 키워드를 사용하여 이 클래스 형식의 변수를 만들 수 없습니다.  인스턴스 변수가 없으므로 정적 클래스 멤버는 클래스 이름 자체를 사용하여 액세스합니다.  예를 들어 `MethodA`라는 public 메서드가 있는 `UtilityClass`라는 정적 클래스가 있으면 다음 예제와 같이 이 메서드를 호출합니다.  
  
```c#  
UtilityClass.MethodA();  
```  
  
 입력 매개 변수에 따라 동작할 뿐 내부 인스턴스 필드를 가져오거나 설정할 필요가 없는 일련의 메서드에 대한 편리한 컨테이너로 정적 클래스를 사용할 수 있습니다.  예를 들어 .NET Framework 클래스 라이브러리의 정적 <xref:System.Math?displayProperty=fullName> 클래스에는 특정 <xref:System.Math> 클래스 인스턴스에 고유한 데이터를 저장하거나 검색할 필요 없이 수학 연산을 수행하는 메서드가 포함되어 있습니다.  즉, 다음 예제와 같이 클래스 이름 및 메서드 이름을 지정하여 클래스의 멤버를 적용합니다.  
  
```  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
  
```  
  
 모든 클래스 형식의 경우와 같이 정적 클래스의 형식 정보는 이 클래스를 참조하는 프로그램이 로드될 때 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] CLR\(공용 언어 런타임\)에 의해 로드됩니다. 프로그램에서는 클래스가 로드되는 정확한 시점을 지정할 수 없습니다.  하지만 프로그램에서 클래스를 처음 참조하기 전에 이 클래스는 반드시 로드되고 해당 필드가 초기화되고 정적 생성자가 호출됩니다.  정적 생성자는 한 번만 호출되며 정적 클래스는 프로그램이 속한 응용 프로그램 도메인의 수명 기간 동안 메모리에 유지됩니다.  
  
> [!NOTE]
>  하나의 인스턴스만 만들 수 있는 비정적 클래스를 만들려면 [Implementing Singleton in C\#](http://go.microsoft.com/fwlink/?LinkID=100567)을 참조하십시오.  
  
 다음 목록에서는 정적 클래스의 주요 특징에 대해 설명합니다.  
  
-   정적 멤버만 포함합니다.  
  
-   인스턴스화할 수 없습니다.  
  
-   봉인되어 있습니다.  
  
-   [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 포함할 수 없습니다.  
  
 따라서 정적 클래스를 만드는 과정은 정적 멤버와 전용 생성자만 들어 있는 클래스를 만드는 과정과 기본적으로 비슷합니다.  전용 생성자는 클래스가 인스턴스화되지 않도록 합니다.  정적 클래스를 사용하면 인스턴스 멤버가 실수로 추가되지 않았는지 컴파일러에서 검사할 수 있다는 이점이 있습니다.  컴파일러에서는 이 클래스의 인스턴스가 생성되지 않도록 보장합니다.  
  
 정적 클래스는 봉인 클래스이므로 상속될 수 없습니다.  정적 클래스는 <xref:System.Object>에서만 상속될 수 있습니다.  정적 클래스는 인스턴스 생성자를 포함할 수 없지만 정적 생성자는 포함할 수 있습니다.  특수한 초기화가 필요한 정적 멤버가 있는 비정적 클래스에서는 정적 생성자도 정의해야 합니다.  자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하십시오.  
  
## 예제  
 다음은 온도를 섭씨에서 화씨로 또는 화씨에서 섭씨로 변환하는 메서드 두 개가 들어 있는 정적 클래스의 예제입니다.  
  
 [!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-classes-and-stati_1.cs)]  
  
## 정적 멤버  
 비정적 클래스는 정적 메서드, 필드, 속성 또는 이벤트를 포함할 수 있습니다.  클래스의 인스턴스를 만들지 않은 경우에도 클래스의 정적 멤버를 호출할 수 있습니다.  정적 멤버는 언제나 인스턴스 이름이 아니라 클래스 이름을 사용하여 액세스됩니다.  클래스의 인스턴스가 몇 개 만들어졌는지에 관계없이 정적 멤버는 하나만 존재합니다.  정적 메서드 및 속성은 포함하는 형식의 비정적 필드 및 이벤트에 액세스할 수 없으며 메서드 매개 변수로 명시적으로 전달되지 않는 한 어떤 개체의 인스턴스 변수에도 액세스할 수 없습니다.  
  
 전체 클래스를 static으로 선언하는 것보다 정적 멤버가 일부 포함된 비정적 클래스를 선언하는 것이 더 일반적입니다.  정적 필드를 사용하는 두 가지 일반적인 경우는 인스턴스화된 개체 수를 보관하는 경우와 모든 인스턴스에서 공유해야 하는 변수를 저장하는 경우입니다.  
  
 정적 메서드는 클래스에 속해 있지 클래스의 인스턴스에 속해 있지 않기 때문에 오버로드할 수는 있지만 재정의할 수는 없습니다.  
  
 필드를 `static const`로 선언할 수는 없지만 [const](../../../csharp/language-reference/keywords/const.md) 필드가 보여 주는 동작은 본질적으로 정적입니다.  const 필드는 형식에 속해 있지 형식의 인스턴스에 속해 있지 않습니다.  따라서 const 필드는 정적 필드에 사용하는 것과 동일한 `ClassName.MemberName` 표기법을 사용하여 액세스할 수 있습니다.  개체 인스턴스는 필요하지 않습니다.  
  
 C\#은 정적 지역 변수\(메서드 범위 내에서 선언되는 변수\)를 지원하지 않습니다.  
  
 정적 클래스 멤버는 다음과 같이 멤버의 반환 형식 앞에 `static` 키워드를 사용하여 선언합니다.  
  
 [!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-classes-and-stati_2.cs)]  
  
 정적 멤버는 처음 액세스되기 전에 초기화되고 정적 생성자가 있으면 이 생성자를 호출하기 전에 초기화됩니다.  정적 클래스 멤버에 액세스하려면 다음 예제에서와 같이 변수 이름 대신 클래스 이름을 사용하여 멤버의 위치를 지정해야 합니다.  
  
 [!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-classes-and-stati_3.cs)]  
  
 클래스에 정적 필드가 있으면 클래스가 로드될 때 해당 필드를 초기화하는 정적 생성자를 제공하십시오.  
  
 정적 메서드를 호출하면 MSIL\(Microsoft Intermediate Language\)로 호출 명령이 생성되는 반면 인스턴스 메서드를 호출하면 역시 null 개체 참조를 확인하는 `callvirt` 명령이 생성됩니다.  하지만 대부분의 경우 이 둘 사이의 성능 차이는 크지 않습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)   
 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)