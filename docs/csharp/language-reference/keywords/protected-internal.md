---
title: "내부 (C# 참조)를 보호합니다."
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a>내부 (C# 참조)를 보호합니다.
`protected internal` 키워드 조합은 멤버 액세스 한정자입니다. 보호 된 내부 멤버는 현재 어셈블리 또는 포함 하는 클래스에서 파생 된 형식에서 액세스할 수 있습니다. `protected internal` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요. 
   
## <a name="example"></a>예제  
 기본 클래스의 보호 된 내부 멤버는 모든 형식을 포함 하는 어셈블리가 내에서 액세스할 수 있습니다. 파생된 클래스 형식의 변수를 통해 액세스 발생 하는 경우에 다른 어셈블리에 있는 파생된 클래스에서 액세스할 수 이기도 합니다. 예를 들어 다음 코드 세그먼트를 고려하세요.  

```
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다. 공용 기본 클래스를 포함 하는 첫 번째 파일 `BaseClass`, 및 다른 클래스 `TestAccess`합니다. `BaseClass`보호 된 내부 멤버를 소유 하 고 `myValue`, 액세스는 `TestAccess` 유형입니다. 두 번째 파일에 액세스 하려고에서 `myValue` 의 인스턴스를 통해 `BaseClass` 에서는 파생된 클래스의 인스턴스를 통해이 멤버에 대 한 액세스 하는 동안 오류가 발생 `DerivedClass` 성공 합니다. 

 구조체 멤버 수 없습니다 `protected internal` 되므로 구조체를 상속할 수 없습니다.  
  
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
