---
title: private protected (C# Reference)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 0d511f55f44511590fbe92a98cef118e0cb482e2
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961134"
---
# <a name="private-protected-c-reference"></a>private protected (C# Reference)
`private protected` 키워드 조합은 멤버 액세스 한정자입니다. private protected 멤버는 포함하는 클래스에서 파생된 형식으로 액세스할 수 있지만 포함하는 어셈블리 내에서만 가능합니다. `private protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요. 

> [!NOTE]
> `private protected` 액세스 한정자는 C# 7.2 버전에서 유효합니다.
   
## <a name="example"></a>예  
 기본 클래스의 private protected 멤버는 변수의 정적 형식이 파생 클래스 형식인 경우에만 포함 어셈블리의 파생된 형식에서 액세스할 수 있습니다. 예를 들어 다음 코드 세그먼트를 고려하세요.  
  
 ```csharp
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```csharp  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다. 첫 번째 파일은 공용 기본 클래스인 `BaseClass`를 포함하고 여기에서 파생된 형식인 `DerivedClass1`을 포함합니다. `BaseClass`는 `DerivedClass1`이 두 가지 방법으로 액세스를 시도하는 private protected 멤버인 `myValue`를 소유합니다. `BaseClass`의 인스턴스를 통한 `myValue` 액세스의 첫 번째 시도는 오류를 생성합니다. 그러나 `DerivedClass1`에서 상속된 멤버로 사용하려는 시도는 성공합니다.
두 번째 파일에서 `DerivedClass2`의 상속된 멤버로 `myValue`에 액세스하는 시도는 Assembly1에서 파생된 형식으로만 액세스할 수 있으므로 오류를 생성합니다. 

 구조체를 상속할 수 없기 때문에 구조체 멤버는 `private protected`일 수 없습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [internal virtual 키워드에 대한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
