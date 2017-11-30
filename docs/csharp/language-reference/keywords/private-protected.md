---
title: "private (C# 참조) 보호"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a>private (C# 참조) 보호
`private protected` 키워드 조합은 멤버 액세스 한정자입니다. 개인 보호 된 멤버는 포함 하는 어셈블리가 내 에서만 않고 포함 하는 클래스에서 파생 된 형식에서 액세스할 수 있습니다. `private protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요. 
   
## <a name="example"></a>예제  
 기본 클래스의 보호 된 개인 멤버는 변수의 정적 형식이 파생된 클래스 형식인 경우에 포함 하는 어셈블리가에서 파생된 형식에서 액세스할 수 있습니다. 예를 들어 다음 코드 세그먼트를 고려하세요.  
  
 ```
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
  
```  
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
 이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다. 공용 기본 클래스를 포함 하는 첫 번째 파일 `BaseClass`, 여기에서 파생 된 형식이 고 `DerivedClass1`합니다. `BaseClass`보호 된 개인 멤버를 소유 하 고 `myValue`이며 `DerivedClass1` 두 가지 방법으로 액세스 하려고 합니다. 에 액세스 하려고 하는 첫 번째 `myValue` 의 인스턴스를 통해 `BaseClass` 하면 오류가 발생 합니다. 그러나에서 상속된 된 멤버와 사용 하려는 시도가 `DerivedClass1` 성공 합니다.
두 번째 파일에 액세스 하려고에서 `myValue` 의 상속된 된 멤버와 `DerivedClass2` Assembly1에서 파생 된 형식으로 액세스 가능한 경우만 오류를 생성 합니다. 

 구조체 멤버 수 없습니다 `private protected` 되므로 구조체를 상속할 수 없습니다.  
  
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
 [Internal virtual 키워드에 대 한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
