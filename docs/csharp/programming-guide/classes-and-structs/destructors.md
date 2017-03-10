---
title: "소멸자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~[C#], 소멸자"
  - "C# 언어, 소멸자"
  - "소멸자[C#]"
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 소멸자(C# 프로그래밍 가이드)
소멸자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.  
  
## 설명  
  
-   소멸자는 구조체에 정의할 수 없습니다.  이것은 클래스와만 사용할 수 있습니다.  
  
-   클래스는 하나의 소멸자만 가질 수 있습니다.  
  
-   소멸자는 상속되거나 오버로드될 수 없습니다.  
  
-   소멸자는 사용자가 호출할 수 없으며,  자동으로 호출됩니다.  
  
-   소멸자는 한정자를 사용하거나 매개 변수를 갖지 않습니다.  
  
 예를 들어, `Car` 클래스에 대한 소멸자 선언은 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/destructors_1.cs)]  
  
 소멸자는 개체의 기본 클래스에서 암시적으로 <xref:System.Object.Finalize%2A>를 호출합니다.  따라서 위의 소멸자 코드는 암시적으로 다음과 같은 코드로 변환됩니다.  
  
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
  
 즉, `Finalize` 메서드는 최대 파생 인스턴스부터 최소 파생 인스턴스까지 상속 체인에 있는 모든 인스턴스에 대해 재귀적으로 호출됩니다.  
  
> [!NOTE]
>  빈 소멸자는 사용하지 않는 것이 좋습니다.  클래스에 소멸자가 포함된 경우 `Finalize` 큐에 엔트리가 만들어집니다.  소멸자가 호출되면 큐 처리를 위해 가비지 수집기가 호출됩니다.  그러므로 빈 소멸자는 성능 저하를 가져올 뿐입니다.  
  
 소멸자가 호출되는 시기는 가비지 수집기에서 결정하므로 프로그래머는 이 시기를 제어할 수 없습니다.  가비지 수집기는 응용 프로그램에서 더 이상 사용하지 않는 개체를 확인합니다.  개체를 소멸할 수 있는 것으로 판단된 경우 소멸자가 있으면 이를 호출하고 개체를 저장하는 데 사용된 메모리를 회수합니다.  소멸자는 프로그램을 종료할 때도 호출됩니다.  
  
 <xref:System.GC.Collect%2A>를 호출하여 가비지 수집을 강제로 실행할 수 있지만, 이렇게 하면 성능 문제가 발생할 수 있으므로 피하는 것이 좋습니다.  
  
## 소멸자를 사용하여 리소스 해제  
 일반적으로 C\#에는 가비지 수집 기능이 있는 런타임을 대상으로 하지 않는 언어로 개발할 때 필요한 것과 같은 메모리 관리가 필요하지 않습니다.  왜냐하면, .NET Framework 가비지 수집기에서 개체에 대한 메모리 할당과 해제를 암시적으로 관리하기 때문입니다.  그러나 창, 파일 및 네트워크 연결처럼 관리되지 않는 리소스를 응용 프로그램에서 캡슐화할 경우, 소멸자를 사용하여 이 리소스를 해제해야 합니다.  개체가 소멸 대상이 되면 가비지 수집기는 해당 개체의 `Finalize` 메서드를 실행합니다.  
  
## 리소스의 명시적 해제  
 응용 프로그램에서 부담이 큰 외부 리소스를 사용하는 경우에는 가비지 수집기에서 개체를 정리하기 전에 리소스를 명시적으로 해제하는 것도 좋은 방법입니다.  이렇게 하려면 개체에 필요한 정리를 수행하는 <xref:System.IDisposable> 인터페이스의 `Dispose` 메서드를 구현합니다.  이로 인해 응용 프로그램 성능이 대폭 향상될 수 있습니다.  이러한 명시적 리소스 제어와 함께, 소멸자는 `Dispose` 메서드 호출이 실패할 경우 리소스를 정리하는 보호 수단이 됩니다.  
  
 리소스 정리에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [Cleaning Up Unmanaged Resources](../Topic/Cleaning%20Up%20Unmanaged%20Resources.md)  
  
-   [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)  
  
-   [using 문](../../../csharp/language-reference/keywords/using-statement.md)  
  
## 예제  
 다음 예제에서는 상속 체인을 만드는 세 개의 클래스를 생성합니다.  `First` 클래스가 기본 클래스이고 `Second` 클래스는 `First`에서 파생되며 `Third`는 `Second`에서 파생됩니다.  세 클래스에는 모두 소멸자가 있습니다.  `Main()`에서 최대 파생 클래스의 인스턴스가 만들어집니다.  프로그램을 실행하면 세 클래스의 소멸자가 최대 파생 클래스부터 최소 파생 클래스까지 순서대로 자동 호출됩니다.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/destructors_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.IDisposable>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)