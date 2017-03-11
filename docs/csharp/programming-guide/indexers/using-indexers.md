---
title: "인덱서 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인덱서[C#], 인덱서 정보"
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# 인덱서 사용(C# 프로그래밍 가이드)
인덱서는 클라이언트 응용 프로그램에서 배열과 마찬가지 방식으로 액세스할 수 있는 [클래스](../../../csharp/language-reference/keywords/class.md), [구조체](../../../csharp/language-reference/keywords/struct.md) 또는 [인터페이스](../../../csharp/language-reference/keywords/interface.md)를 만들 수 있게 해 주는 편리한 구문입니다.  인덱서는 주로 내부 컬렉션 또는 배열을 캡슐화하기 위한 형식에서 가장 많이 구현됩니다.  예를 들어 24시간 동안 10번 기록되는 온도를 화씨로 나타내는 TempRecord라는 클래스가 있다고 가정합니다.  클래스에는 온도를 나타내는 float 형식의 "temps"라는 배열과 온도를 기록한 날짜를 나타내는 <xref:System.DateTime>이 들어 있습니다.  이 경우 인덱서를 구현하면 클라이언트는 `float temp = tr.temps[4]` 대신 `float temp = tr[4]`로 TempRecord 인스턴스의 온도에 액세스할 수 있습니다.  인덱서 표기법은 클라이언트 응용 프로그램의 구문을 단순하게 할 뿐 아니라 클래스와 해당 클래스의 용도를 다른 개발자가 쉽게 이해할 수 있도록 합니다.  
  
 클래스나 구조체에 대한 인덱서를 선언하려면 다음 예제에서와 같이 [this](../../../csharp/language-reference/keywords/this.md) 키워드를 사용합니다.  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
  
```  
  
## 설명  
 인덱서 형식과 해당 매개 변수 형식에는 적어도 인덱서 자체와 동등한 수준으로 액세스할 수 있어야 합니다.  액세스 가능성 수준에 대한 자세한 내용은 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)를 참조하십시오.  
  
 인터페이스와 함께 인덱서를 사용하는 방법에 대한 자세한 내용은 [인터페이스 인덱서](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)를 참조하십시오.  
  
 인덱서 시그니처는 인덱서 정식 매개 변수의 수 및 형식으로 구성됩니다.  이 시그니처는 인덱서 형식 또는 정식 매개 변수 이름을 포함하지 않습니다.  같은 클래스에 두 개 이상의 인덱서를 선언한 경우, 모든 인덱서가 다른 시그니처를 가져야 합니다.  
  
 인덱서 값은 변수로 분류되지 않기 때문에 인덱서 값을 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수로 전달할 수 없습니다.  
  
 다른 언어에서 사용할 수 있는 이름을 인덱서에 부여하려면 선언에 `name` 특성을 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 이 인덱서의 이름은 `TheItem`입니다.  name 특성을 제공하지 않으면 기본 이름으로 `Item`이 사용됩니다.  
  
## 예제 1  
  
### 설명  
 다음 예제는 전용 배열 필드 `temps`와 인덱서를 선언하는 방법을 보여 줍니다.  인덱서를 사용하면 `tempRecord[i]` 인스턴스에 직접 액세스할 수 있습니다.  인덱서를 사용하지 않으려면 배열을 [public](../../../csharp/language-reference/keywords/public.md)멤버로 선언하고 해당 멤버인 `tempRecord.temps[i]`에 직접 액세스하면 됩니다.  
  
 예를 들어, `Console.Write` 문에서 인덱서의 액세스를 계산할 경우에는 [get](../../../csharp/language-reference/keywords/get.md) 접근자가 호출됩니다.  따라서 `get` 접근자가 없으면 컴파일 타임 오류가 발생합니다.  
  
### 코드  
 [!code-cs[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-indexers_1.cs)]  
  
## 다른 값을 사용한 인덱싱  
 C\#에서는 인덱스 형식이 정수로만 제한되지 않습니다.  예를 들어, 인덱서와 함께 문자열을 사용하는 것이 유용할 수 있습니다.  이러한 인덱서는 컬렉션에서 문자열을 검색하고 적절한 값을 반환하여 구현할 수 있습니다.  접근자로 오버로드할 수 있으므로 문자열과 정수 버전의 인덱스 형식은 함께 사용될 수 있습니다.  
  
## 예제 2  
  
### 설명  
 이 예제에서는 요일을 저장하는 클래스를 선언합니다.  문자열과 요일 이름을 가져오고 상응하는 정수를 반환하는 `get` 접근자를 선언합니다.  예를 들어, 일요일은 0을 반환하고 월요일은 1을 반환하는 방식입니다.  
  
### 코드  
 [!code-cs[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/using-indexers_2.cs)]  
  
## 강력한 프로그래밍  
 인덱서의 보안과 안전성을 향상시키는 데는 크게 두 가지 방법이 있습니다.  
  
-   클라이언트 코드에서 잘못된 인덱스 값을 전달할 경우를 처리하려면 몇 가지 오류 처리 방법을 통합해야 합니다.  이 항목의 앞부분에 나오는 첫 번째 예제에서 TempRecord 클래스는 클라이언트 코드에서 입력 내용을 인덱서에 전달하기 전에 해당 입력을 확인하는 데 사용할 수 있는 Length 속성을 제공합니다.  오류 처리 코드를 인덱서 내에 포함할 수도 있습니다.  인덱서 접근자 내에서 throw하는 모든 예외에 대해 사용자에게 설명해야 합니다.  
  
-   `get` 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자의 액세스 가능성을 적절한 수준에서 제한적으로 설정합니다.  이는 특히 `set` 접근자의 경우 중요한 의미를 갖습니다.  자세한 내용은 [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)