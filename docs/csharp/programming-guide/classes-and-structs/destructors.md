---
title: "소멸자(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in destructors
- C# language, destructors
- destructors [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
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
ms.openlocfilehash: 6940be34b6cc15f006901e6d14d2a38ebb5d012a
ms.lasthandoff: 03/13/2017

---
# <a name="destructors-c-programming-guide"></a>소멸자(C# 프로그래밍 가이드)
소멸자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.  
  
## <a name="remarks"></a>설명  
  
-   소멸자는 구조체에서 정의할 수 없으며, 클래스에서만 사용됩니다.  
  
-   클래스에는 소멸자가 하나만 있을 수 있습니다.  
  
-   소멸자는 상속하거나 오버로드할 수 없습니다.  
  
-   소멸자는 호출할 수 없으며, 자동으로 호출됩니다.  
  
-   소멸자는 한정자를 사용하거나 매개 변수를 갖지 않습니다.  
  
 예를 들어 다음은 `Car` 클래스에 대한 소멸자의 선언입니다.  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  
  
 소멸자는 개체의 기본 클래스에서 <xref:System.Object.Finalize%2A>를 암시적으로 호출합니다. 따라서 이전 소멸자 코드는 다음 코드로 암시적으로 변환됩니다.  
  
```  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 즉, `Finalize` 메서드가 상속 체인의 모든 인스턴스에 대해 최다 파생에서 최소 파생까지 재귀적으로 호출됩니다.  
  
> [!NOTE]
>  빈 소멸자는 사용할 수 없습니다. 클래스에 소멸자가 포함되어 있으면 `Finalize` 큐에서 항목이 생성됩니다. 소멸자를 호출하면 가비지 수집기가 호출되어 큐를 처리합니다. 소멸자가 비어 있으면 성능이 불필요하게 저하됩니다.  
  
 소멸자를 호출하면 가비지 수집기에 의해 결정되기 때문에 프로그래머가 제어하지 않습니다. 가비지 수집기는 응용 프로그램에서 더 이상 사용되지 않는 개체를 확인합니다. 개체를 소멸할 수 있는 것으로 판단되면 소멸자(있는 경우)를 호출하고 개체를 저장하는 데 사용된 메모리를 회수합니다. 소멸자는 프로그램이 종료될 때도 호출됩니다.  
  
 <xref:System.GC.Collect%2A>를 호출하여 강제로 가비지 수집할 수 있지만 대부분의 경우 성능 문제가 발생할 수 있으므로 방지해야 합니다.  
  
## <a name="using-destructors-to-release-resources"></a>소멸자를 사용하여 리소스 해제  
 일반적으로 C#에서는 가비지 수집을 사용하는 런타임을 대상으로 하지 않는 언어로 개발할 때 필요한 만큼 많은 메모리 관리가 필요하지 않습니다. 이는 .NET Framework 가비지 수집기에서 개체에 대한 메모리 할당 및 해제를 암시적으로 관리하기 때문입니다. 그러나 응용 프로그램에서 창, 파일 및 네트워크 연결 등의 관리되지 않는 리소스를 캡슐화하는 경우 소멸자를 사용하여 해당 리소스를 해제해야 합니다. 개체를 소멸할 수 있으면 가비지 수집기에서 개체의 `Finalize` 메서드를 실행합니다.  
  
## <a name="explicit-release-of-resources"></a>리소스의 명시적 해제  
 응용 프로그램에서 비용이 많이 드는 외부 리소스를 사용하는 경우 가비지 수집기에서 개체를 해제하기 전에 리소스를 명시적으로 해제하는 방법을 제공하는 것이 좋습니다. 이렇게 하려면 <xref:System.IDisposable> 인터페이스에서 개체에 필요한 정리를 수행하는 `Dispose` 메서드를 구현합니다. 이렇게 하면 응용 프로그램의 성능을 상당히 향상시킬 수 있습니다. 이렇게 리소스를 명시적으로 제어하는 경우에도 소멸자는 `Dispose` 메서드 호출에 실패할 경우 리소스를 정리하는 안전한 방법이 됩니다.  
  
 리소스 정리에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [관리되지 않는 리소스 정리](http://msdn.microsoft.com/library/a17b0066-71c2-4ba4-9822-8e19332fc213)  
  
-   [Dispose 메서드 구현](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)  
  
-   [using 문](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 상속 체인을 구성하는 세 가지 클래스를 만듭니다. `First` 클래스는 기본 클래스이고, `Second`는 `First`에서 파생되며, `Third`는 `Second`에서 파생됩니다. 세 클래스 모두 소멸자가 있습니다. `Main()`에서 최다 파생 클래스의 인스턴스가 만들어집니다. 프로그램이 실행되면 세 클래스에 대한 소멸자가 최다 파생부터 최소 파생까지 순서대로 자동으로 호출됩니다.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IDisposable>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [가비지 수집](../../../standard/garbagecollection/index.md)
