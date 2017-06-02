---
title: "사용자 지정 특성 만들기(C#) | Microsoft 문서"
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
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 346a5311a100e75adacea6100d6e5f1f893812ff
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="creating-custom-attributes-c"></a>사용자 지정 특성 만들기(C#)
메타데이터에서 특성 정의를 빠르고 쉽게 식별할 수 있도록 하는 <xref:System.Attribute>에서 직접 또는 간접적으로 파생되는 특성 클래스를 정의하여 자체 사용자 지정 특성을 만들 수 있습니다. 형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정합니다. 사용자 지정 `Author` 특성 클래스를 정의할 수 있습니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 클래스 이름은 특성의 이름인 `Author`입니다. 이 클래스는 `System.Attribute`에서 파생되므로 사용자 지정 특성 클래스입니다. 생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다. 이 예제에서는 `name`이 위치 매개 변수입니다. 모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다. 이 경우에는 `version`이 유일한 명명된 매개 변수입니다. 클래스 및 `struct` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.  
  
 이 새로운 특성은 다음과 같이 사용할 수 있습니다.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 `AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하는 데 이용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다. 다음 코드 예제에서는 다중 사용 특성이 만들어집니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
> [!NOTE]
>  특성 클래스에 속성이 포함되면 해당 속성은 읽기-쓰기여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection>   
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)   
 [사용자 지정 특성 작성](../../../../standard/attributes/writing-custom-attributes.md)   
 [리플렉션(C#)](../../../../csharp/programming-guide/concepts/reflection.md)   
 [특성(C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)   
 [리플렉션을 사용하여 특성 액세스(C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage(C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)
