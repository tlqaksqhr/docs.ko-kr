---
title: "방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 841132b5181c5e17d1eabae11d3550811aa959ec
ms.contentlocale: ko-kr
ms.lasthandoff: 03/24/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a>방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드)
다음 코드 예제에서는 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)와 함께 사용할 수 있는 제네릭이 아닌 컬렉션 클래스를 작성하는 방법을 보여 줍니다. 예제에서는 문자열 토크나이저 클래스를 정의합니다.  
  
> [!NOTE]
>  이 예제는 제네릭 컬렉션 클래스를 사용할 수 없는 경우에만 권장되는 방식을 나타냅니다. <xref:System.Collections.Generic.IEnumerable%601>을 지원하는 형식이 안전한 제네릭 컬렉션 클래스를 구현하는 방법의 예는 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.  
  
 예제에서 다음 코드 세그먼트는 `Tokens` 클래스를 사용하여 "This is a sample sentence."라는 문장을 ' ' 및 '-' 구분 기호로 토큰으로 구분합니다. 그런 다음 코드에서 `foreach` 문을 사용하여 해당 토큰을 표시합니다.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a>예제  
 내부적으로 `Tokens` 클래스는 배열을 사용하여 토큰을 저장합니다. 배열이 <xref:System.Collections.IEnumerator> 및 <xref:System.Collections.IEnumerable>을 구현하기 때문에 코드 예제에서는 `Tokens` 클래스에서 정의하는 대신 배열의 열거형 메서드(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>)를 사용할 수 있었습니다. 메서드 정의는 메서드가 정의된 방식과 각 메서드의 기능을 설명하기 위해 예제에 포함되었습니다.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 C#에서 컬렉션 클래스가 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 `foreach`와 호환되도록 구현할 필요는 없습니다. 클래스에 필수 <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.Current%2A> 멤버가 있으면 `foreach`에서 작동합니다. 인터페이스를 생략하면 `Current`에 대해 <xref:System.Object>보다 더 구체적인 반환 형식을 정의할 수 있다는 장점이 있습니다. 이 경우 형식 안전성이 제공됩니다.  
  
 예를 들어 앞의 예제에서 다음 줄을 변경합니다.  
  
```csharp  
  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
  
```  
  
 `Current`는 문자열을 반환하기 때문에 컴파일러가 다음 코드와 같이 `foreach` 문에서 호환되지 않는 형식이 사용된 경우를 검색할 수 있습니다.  
  
```csharp  
  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 생략할 경우의 단점은 컬렉션 클래스가 `foreach` 문 또는 다른 공용 언어 런타임 언어의 동등한 문과 더 이상 호환되지 않는다는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
