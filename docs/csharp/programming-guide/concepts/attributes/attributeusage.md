---
title: AttributeUsage(C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c008c1a696e93bc3b756a926a046aa5a6942bc10
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="attributeusage-c"></a>AttributeUsage(C#)
사용자 지정 특성 클래스를 사용하는 방법을 결정합니다. `AttributeUsage`는 새 특성 적용 방법을 제어하기 위해 사용자 지정 특성 정의에 적용할 수 있는 특성입니다. 기본 설정은 명시적으로 적용될 경우 다음과 같이 표시됩니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 이 예제에서 `NewAttribute` 클래스는 모든 특성 가능 코드 엔터티에 적용될 수 있지만 각 엔터티에 한 번만 적용될 수 있습니다. 이 특성은 기본 클래스에 적용될 때 파생 클래스가 상속합니다.  
  
 `AllowMultiple` 및 `Inherited` 인수는 선택 사항이므로 이 코드에 미치는 영향은 같습니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 첫 번째 `AttributeUsage` 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다. 다음과 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 `AllowMultiple` 인수를 `true`로 설정하면 다음과 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttr`를 반복적으로 적용할 수 있습니다. 여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.  
  
 `Inherited`를 `false`로 설정하면 특성이 지정된 클래스에서 파생된 클래스가 특성을 상속하지 않습니다. 예:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 이 경우 `Attr1`은 상속을 통해 `DClass`에 적용되지 않습니다.  
  
## <a name="remarks"></a>주의  
 `AttributeUsage` 특성은 단일 사용 특성입니다. 같은 클래스에 두 번 이상 적용될 수 없습니다. `AttributeUsage`는 <xref:System.AttributeUsageAttribute>의 별칭입니다.  
  
 자세한 내용은 [리플렉션을 사용하여 특성 액세스(C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `AttributeUsage` 특성에 대한 `Inherited` 및 `AllowMultiple`의 영향과 클래스에 적용되는 사용자 지정 특성을 열거하는 방법을 보여 줍니다.  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Attribute>   
 <xref:System.Reflection>   
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)   
 [특성](https://msdn.microsoft.com/library/5x6cd29c)   
 [리플렉션(C#)](../../../../csharp/programming-guide/concepts/reflection.md)   
 [특성](../../../../csharp/programming-guide/concepts/attributes/index.md)   
 [사용자 지정 특성 만들기(C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [리플렉션을 사용하여 특성 액세스(C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

