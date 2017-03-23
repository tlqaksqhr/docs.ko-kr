---
title: "스레드 풀링 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6037d7ea17e260d44bae571aa25d413996f5a123
ms.lasthandoff: 03/13/2017

---
# <a name="thread-pooling-visual-basic"></a>스레드 풀링 (Visual Basic)
A *스레드 풀* 백그라운드에서 몇 가지 작업을 수행 하는 데 사용할 수 있는 스레드의 컬렉션입니다. (참조 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) 배경 정보입니다.) 이런 기본 스레드를 자유롭게 다른 작업을 비동기적으로 수행할 수 있습니다.  
  
 스레드 풀 서버 응용 프로그램에서 자주 사용 됩니다. 기본 스레드까지 기다리거나의 후속 요청 처리를 연기 하지 않고는 요청을 비동기적으로 처리할 수 있도록 스레드 풀에서 들어오는 각 요청 스레드에 할당 됩니다.  
  
 스레드 풀에서 해당 작업을 완료 되 면 반환 됩니다 대기 중인 스레드의 큐에 다시 사용할 수 있습니다. 이 다시 사용이 하기에는 각 작업에 대 한 새 스레드를 만드는 비용을 방지 하려면 응용 프로그램이 있습니다.  
  
 스레드 풀에는 일반적으로 최대 스레드 수 있으며 모든 스레드를 사용 중이면 추가 작업 스레드를 사용할 수 있을 때 처리 될 때까지 큐에 배치 됩니다.  
  
 고유한 스레드 풀을 구현할 수 있지만 <xref:System.Threading.ThreadPool>클래스</xref:System.Threading.ThreadPool> 를 통해.NET Framework에서 제공 하는 스레드 풀을 사용 하 여 쉽습니다.  
  
 호출 스레드 풀링을 사용할 경우는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>프로시저에 대 한 대리자와 메서드를 실행 하려면, 및 Visual Basic에서 스레드를 만들고 프로시저를 실행 합니다.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>  
  
## <a name="thread-pooling-example"></a>스레드 풀링 예제  
 다음 예제에서는 몇 가지 작업을 시작 하려면 풀링 스레드를 사용 하는 방법을 보여 줍니다.  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 스레드 풀링의 이점은 수에 전달 하는 인수 상태 개체에는 작업 절차입니다. 또는 구조체에는 클래스의 인스턴스를 캐스팅할 수 프로시저를 호출 하는 둘 이상의 인수가 필요한 경우는 `Object` 데이터 형식입니다.  
  
## <a name="thread-pool-parameters-and-return-values"></a>스레드 풀 매개 변수 및 반환 값  
 스레드 풀 스레드가에서 값을 반환 간단 하지 않습니다. 함수 호출에서 값을 반환 하는 표준 방법 이므로 허용 되지 않습니다 `Sub` 프로시저는 프로시저는 스레드 풀에 대기할 수 있는 유일한 형식입니다. 한 가지 방법은 매개 변수를 제공 하 수 값은 반환 값 매개 변수를 사용 하 여 래퍼에 메서드가 클래스에 설명 된 대로 반환 [매개 변수 및 반환 값 (Visual Basic) 다중 스레드 프로시저에 대 한](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)합니다.  
  
 반환 값 매개 변수를 제공 하는 보다 쉽게 선택적인를 사용 하 여는 `ByVal` 의 상태 개체 변수는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>메서드.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 이 변수를 사용 하 여 클래스의 인스턴스에 대 한 참조를 전달 하는 경우 인스턴스의 멤버를 스레드 풀 스레드에 의해 수정 하 고 반환 값으로 사용 되는 수 있습니다.  
  
 처음에 하기 어려울 수 있습니다 값으로 전달 되는 변수에서 참조 하는 개체를 수정할 수 있습니다. 개체 참조만 값으로 전달 되기 때문에이 수행할 수 있습니다. 개체 참조에서 참조 하는 개체의 구성원을 변경한 경우 변경 내용을 실제 클래스 인스턴스에 적용 됩니다.  
  
 상태 개체 내 값을 반환 하려면 구조를 사용할 수 없습니다. 구조는 값 형식 이므로 비동기 프로세스를 통해 변경 된 원래 구조체의 멤버를 변경 하지 마십시오. 구조를 사용 하 여 반환 값이 필요 하지 않은 경우 매개 변수를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool>   
 [방법: 스레드 풀 (Visual Basic)를 사용 하 여](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)   
 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [스레드 동기화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
