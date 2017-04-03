---
title: "스레드 풀링(C#) | Microsoft 문서"
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
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
caps.latest.revision: 5
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: da18d75f5d80cd7ad8a9a974bf0ffda196e7ea86
ms.lasthandoff: 03/13/2017

---
# <a name="thread-pooling-c"></a>스레드 풀링(C#)
*스레드 풀*은 백그라운드에서 몇 가지 작업을 수행하는 데 사용할 수 있는 스레드 컬렉션입니다. 배경 정보는 [스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/index.md)을 참조하세요. 이렇게 하면 기본 스레드가 자유롭게 다른 작업을 비동기적으로 수행할 수 있습니다.  
  
 스레드 풀은 서버 응용 프로그램에서 자주 사용됩니다. 기본 스레드를 구속하거나 후속 요청의 처리를 지연하지 않고 요청을 비동기적으로 처리할 수 있도록 들어오는 각 요청이 스레드 풀의 스레드에 할당됩니다.  
  
 풀의 스레드가 해당 작업을 완료하면 대기 중인 스레드 큐로 반환되어 다시 사용할 수 있습니다. 이렇게 다시 사용하면 응용 프로그램에서 각 작업에 대한 새 스레드를 만드는 비용을 방지할 수 있습니다.  
  
 일반적으로 스레드 풀에는 최대 개수의 스레드가 있습니다. 모든 스레드가 사용 중인 경우 추가 작업이 스레드를 사용할 수 있게 되면 처리될 때까지 큐에 배치됩니다.  
  
 고유한 스레드 풀을 구현할 수 있지만, <xref:System.Threading.ThreadPool> 클래스를 통해 .NET Framework에서 제공하는 스레드 풀을 사용하는 것이 더 쉽습니다.  
  
 스레드 풀링을 사용하는 경우 실행하려는 프로시저에 대한 대리자를 사용하여 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> 메서드를 호출합니다. 그러면 C#에서 스레드를 만들고 프로시저를 실행합니다.  
  
## <a name="thread-pooling-example"></a>스레드 풀링 예제  
 다음 예제에서는 스레드 풀링을 사용하여 몇 가지 작업을 시작하는 방법을 보여 줍니다.  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 스레드 풀링의 한 가지 장점은 상태 개체의 인수를 작업 프로시저에 전달할 수 있다는 것입니다. 호출하는 프로시저에 둘 이상의 인수가 필요한 경우 구조체 또는 클래스 인스턴스를 `Object` 데이터 형식으로 캐스팅할 수 있습니다.  
  
## <a name="thread-pool-parameters-and-return-values"></a>스레드 풀 매개 변수 및 반환 값  
 스레드 풀 스레드에서 값을 반환하는 것은 간단하지 않습니다. `Sub` 프로시저가 스레드 풀에 대기될 수 있는 유일한 프로시저 형식이므로 함수 호출에서 값을 반환하는 표준 방법은 허용되지 않습니다. 매개 변수 및 반환 값을 제공할 수 있는 한 가지 방법은 [다중 스레드 프로시저의 매개 변수 및 반환 값(C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)에 설명된 대로 매개 변수, 반환 값 및 메서드를 래퍼 클래스에 래핑하는 것입니다.  
  
 매개 변수 및 반환 값을 제공하는 보다 쉬운 방법은 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드의 선택적 `ByVal` 상태 개체 변수를 사용하는 것입니다. 이 변수를 사용하여 클래스 인스턴스에 대한 참조를 전달하는 경우 인스턴스 멤버가 스레드 풀 스레드에 의해 수정되고 반환 값으로 사용될 수 있습니다.  
  
 처음에는 값으로 전달된 변수가 참조하는 개체를 수정할 수 있는지 명확하지 않을 수도 있습니다. 이 작업은 개체 참조만 값으로 전달되기 때문에 가능합니다. 개체 참조에서 참조된 개체의 멤버를 변경하는 경우 변경 내용이 실제 클래스 인스턴스에 적용됩니다.  
  
 구조체를 사용하여 상태 개체 내의 값을 반환할 수 없습니다. 구조체는 값 형식이므로 비동기 프로세스를 통해 변경된 내용은 원래 구조체의 멤버를 변경하지 않습니다. 반환 값이 필요하지 않은 경우 구조체를 사용하여 매개 변수를 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading>   
 <xref:System.Threading.ThreadPool>   
 [방법: 스레드 풀 사용(C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)   
 [스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/index.md)   
 [다중 스레드 응용 프로그램(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)   
 [스레드 동기화(C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
