---
title: "개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
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
ms.openlocfilehash: c4144f383d539129b4e03d5cad262e5a7b9e6b34
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="object-and-collection-initializers-c-programming-guide"></a>개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)
개체 이니셜라이저를 사용하면 명시적으로 생성자를 호출한 다음 할당문 줄을 추가하지 않고도 생성 시 개체의 모든 액세스 가능한 필드나 속성에 값을 할당할 수 있습니다. 개체 이니셜라이저 구문을 사용하면 생성자의 인수를 지정하거나 인수(및 괄호 구문)를 생략할 수 있습니다.  다음 예제는 명명된 형식인 `Cat`의 개체 이니셜라이저를 사용하는 방법과 기본 생성자를 호출하는 방법을 보여 줍니다. `Cat` 클래스의 자동 구현된 속성 사용을 확인합니다. 자세한 내용은 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.  
  
 [!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]  
  
## <a name="object-initializers-with-anonymous-types"></a>익명 형식의 개체 이니셜라이저  
 개체 이니셜라이저는 모든 컨텍스트에서 사용할 수 있지만 특히 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식에 유용합니다. 쿼리 식은 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 자주 사용합니다. 이 형식은 다음 선언에 표시된 바와 같이 개체 이니셜라이저를 사용하는 경우에만 초기화될 수 있습니다.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 무명 형식을 사용하면 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식의 `select` 절에서 원래 시퀀스의 개체를 값과 모양이 원본과 다를 수 있는 개체로 변환할 수 있습니다. 이 기능은 각 개체의 일부 정보만 시퀀스에 저장하려는 경우에 유용합니다. 다음 예제에서 제품 개체(`p`)는 많은 필드와 메서드를 포함하며, 제품 이름과 단위 가격이 들어 있는 개체 시퀀스만 만들려 한다고 가정합니다.  
  
 [!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 이 쿼리를 실행하면 다음 예제와 같이 `productInfos` 문에서 액세스할 수 있는 개체 시퀀스가 `foreach` 변수에 포함됩니다.  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 새 익명 형식의 각 개체에는 원래 개체의 속성이나 필드와 동일한 이름을 받는 두 개의 public 속성이 있습니다. 익명 형식을 만들 때 필드 이름을 바꿀 수도 있습니다. 다음 예제에서는 `UnitPrice` 필드의 이름을 `Price`로 바꿉니다.  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a>nullable 형식의 개체 이니셜라이저  
 개체 이니셜라이저에 nullable 구조체를 사용하는 것은 컴파일 시간 오류입니다.  
  
## <a name="collection-initializers"></a>컬렉션 이니셜라이저  
 컬렉션 이니셜라이저를 사용하면 <xref:System.Collections.IEnumerable>을 구현하고 적절한 시그니처가 있는 `Add`를 인스턴스 메서드 또는 확장 메서드로 포함하는 컬렉션 형식을 초기화할 때 하나 이상의 요소 이니셜라이저를 지정할 수 있습니다. 요소 이니셜라이저는 단순한 값, 식 또는 개체 이니셜라이저일 수 있습니다. 컬렉션 이니셜라이저를 사용하면 소스 코드에서 클래스의 `Add` 메서드에 대한 호출을 여러 번 지정할 필요가 없습니다. 컴파일러가 호출을 추가합니다.  
  
 다음 예제에서는 두 개의 단순한 컬렉션 이니셜라이저를 보여 줍니다.  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 다음 컬렉션 이니셜라이저는 개체 이니셜라이저를 사용하여 앞의 예제에서 정의된 `Cat` 클래스의 개체를 초기화합니다. 개별 개체 이니셜라이저는 괄호로 묶이고 쉼표로 구분됩니다.  
  
 [!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 컬렉션의 `Add` 메서드에서 허용하는 경우 [null](../../../csharp/language-reference/keywords/null.md)을 컬렉션 이니셜라이저의 요소로 지정할 수 있습니다.  
  
 [!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 컬렉션이 인덱싱을 지원하는 경우 인덱싱된 요소를 지정할 수 있습니다.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

