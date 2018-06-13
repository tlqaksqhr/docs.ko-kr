---
title: '방법: Nullable 형식 식별(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f3ac4ebd77fc92a133eb326919d5ba55264ced97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333185"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>방법: Nullable 형식 식별(C# 프로그래밍 가이드)
C# [typeof](../../../csharp/language-reference/keywords/typeof.md) 연산자를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 만들 수 있습니다.  
  
```  
System.Type type = typeof(int?);  
```  
  
 <xref:System.Reflection> 네임스페이스의 클래스와 메서드를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 생성할 수도 있습니다. 그러나 <xref:System.Object.GetType%2A> 메서드 또는 `is` 연산자를 사용하여 런타임에 Nullable 변수에서 형식 정보를 가져오려고 하면 그 결과로 Nullable 형식 자체가 아니라 내부 형식을 나타내는 <xref:System.Type> 개체가 생성됩니다.  
  
 Nullable 형식에서 `GetType`을 호출하면 형식이 <xref:System.Object>로 암시적으로 변환될 때 boxing 작업이 수행됩니다. 따라서 <xref:System.Object.GetType%2A>은 항상 Nullable 형식이 아니라 내부 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 C# [is](../../../csharp/language-reference/keywords/is.md) 연산자도 Nullable 내부 형식에서 작동합니다. 따라서 `is`를 사용하여 변수가 Nullable 형식인지 여부를 확인할 수 없습니다. 다음 예제에서는 `is` 연산자가 Nullable\<int> 변수를 int 형식으로 처리함을 보여 줍니다.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a>예  
 다음 코드를 사용하여 <xref:System.Type> 개체가 Nullable 형식을 나타내는지 여부를 확인할 수 있습니다. 이 항목의 앞부분에서 설명한 것처럼 이 코드는 <xref:System.Object.GetType%2A> 호출에서 `Type` 개체가 반환된 경우 항상 false를 반환합니다.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
 [Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
