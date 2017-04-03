---
title: "액세스 가능성 수준 사용에 대한 제한(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 51b399993008a1a3ce61679cdccc3e5e7bf25354
ms.lasthandoff: 03/13/2017

---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>액세스 가능성 수준 사용에 대한 제한(C# 참조)
선언에서 형식을 지정하는 경우, 형식의 액세스 가능성 수준이 멤버 또는 다른 형식의 액세스 가능성 수준에 따라 달라지는지를 확인합니다. 예를 들어 직접 기본 클래스는 적어도 파생 클래스 수준만큼 액세스 가능해야 합니다. 다음 선언에서는 기본 클래스 `BaseClass`가 `MyClass`보다 액세스 가능성이 낮기 때문에 컴파일러 오류가 발생합니다.  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 다음 표에는 선언된 액세스 가능성 수준에 대한 제한이 요약되어 있습니다.  
  
|컨텍스트|설명|  
|-------------|-------------|  
|[클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)|클래스 형식의 직접 기본 클래스는 적어도 클래스 형식 자체 수준만큼 액세스 가능해야 합니다.|  
|[인터페이스](../../../csharp/programming-guide/interfaces/index.md)|인터페이스 형식의 명시적 기본 인터페이스는 적어도 인터페이스 형식 자체 수준만큼 액세스 가능해야 합니다.|  
|[대리자](../../../csharp/programming-guide/delegates/index.md)|대리자 형식의 반환 형식 및 매개 변수 형식은 적어도 대리자 형식 자체 수준만큼 액세스 가능해야 합니다.|  
|[상수](../../../csharp/programming-guide/classes-and-structs/constants.md)|상수의 형식은 적어도 상수 자체 수준만큼 액세스 가능해야 합니다.|  
|[필드](../../../csharp/programming-guide/classes-and-structs/fields.md)|필드의 형식은 적어도 필드 자체 수준만큼 액세스 가능해야 합니다.|  
|[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)|메서드의 반환 형식 및 매개 변수 형식은 적어도 메서드 자체 수준만큼 액세스 가능해야 합니다.|  
|[속성](../../../csharp/programming-guide/classes-and-structs/properties.md)|속성의 형식은 적어도 속성 자체 수준만큼 액세스 가능해야 합니다.|  
|[이벤트](../../../csharp/programming-guide/events/index.md)|이벤트의 형식은 적어도 이벤트 자체 수준만큼 액세스 가능해야 합니다.|  
|[인덱서](../../../csharp/programming-guide/indexers/index.md)|인덱서의 형식 및 매개 변수 형식은 적어도 인덱서 자체 수준만큼 액세스 가능해야 합니다.|  
|[연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|연산자의 반환 형식 및 매개 변수 형식은 적어도 연산자 자체 수준만큼 액세스 가능해야 합니다.|  
|[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)|생성자의 매개 변수 형식은 적어도 생성자 자체 수준만큼 액세스 가능해야 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에는 다양한 종류의 잘못된 선언이 포함되어 있습니다. 각 선언 다음의 주석은 예상된 컴파일러 오류를 나타냅니다.  
  
```  
// Restrictions on Using Accessibility Levels  
// CS0052 expected as well as CS0053, CS0056, and CS0057  
// To make the program work, change access level of both class B  
// and MyPrivateMethod() to public.  
  
using System;  
  
// A delegate:  
delegate int MyDelegate();  
  
class B  
{  
    // A private method:  
    static int MyPrivateMethod()  
    {  
        return 0;  
    }  
}  
  
public class A  
{  
    // Error: The type B is less accessible than the field A.myField.  
    public B myField = new B();  
  
    // Error: The type B is less accessible  
    // than the constant A.myConst.  
    public readonly B myConst = new B();  
  
    public B MyMethod()  
    {  
        // Error: The type B is less accessible   
        // than the method A.MyMethod.  
        return new B();  
    }  
  
    // Error: The type B is less accessible than the property A.MyProp  
    public B MyProp  
    {  
        set  
        {  
        }  
    }  
  
    MyDelegate d = new MyDelegate(B.MyPrivateMethod);  
    // Even when B is declared public, you still get the error:   
    // "The parameter B.MyPrivateMethod is not accessible due to   
    // protection level."  
  
    public static B operator +(A m1, B m2)  
    {  
        // Error: The type B is less accessible  
        // than the operator A.operator +(A,B)  
        return new B();  
    }  
  
    static void Main()  
    {  
        Console.Write("Compiled successfully");  
    }  
}  
```  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)
