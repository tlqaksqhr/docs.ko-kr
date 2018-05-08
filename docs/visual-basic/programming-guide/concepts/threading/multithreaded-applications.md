---
title: 다중 스레드 응용 프로그램 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
ms.openlocfilehash: ab4b8d1c77ae75aee6f2cf459258766f88d86abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="multithreaded-applications-visual-basic"></a>다중 스레드 응용 프로그램 (Visual Basic)
Visual Basic의 경우 동시에 여러 작업을 수행 하는 응용 프로그램을 작성할 수 있습니다. 다른 작업을 지연시킬 수 있는 작업은 별도 스레드에서 실행할 수 있으며, 이 프로세스를 *다중 스레딩* 또는 *자유 스레딩*이라고 합니다.  
  
 다중 스레딩을 사용하는 응용 프로그램은 프로세서를 많이 사용하는 작업이 별도 스레드에서 실행될 때 사용자 인터페이스가 활성 상태로 유지되기 때문에 사용자 입력에 더 빠르게 응답합니다. 또한 다중 스레딩은 작업이 증가함에 따라 스레드를 추가할 수 있으므로 확장 가능한 응용 프로그램을 만들 때에도 유용합니다.  
  
## <a name="creating-and-using-threads"></a>스레드 만들기 및 사용  
 응용 프로그램 스레드의 동작을 보다 강력하게 제어해야 하는 경우 직접 스레드를 관리할 수 있습니다. 그러나 올바른 다중 스레드 응용 프로그램을 작성하는 것은 어려울 수 있습니다. 응용 프로그램이 응답하지 않거나 경합 상태로 인해 일시적인 오류가 발생할 수 있습니다. 자세한 내용은 [스레드로부터 안전한 구성 요소](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)를 참조하세요.  
  
 <xref:System.Threading.Thread> 형식의 변수를 선언하고 새 스레드에서 실행하려는 프로시저 또는 메서드의 이름을 지정해서 생성자를 호출하여 새 스레드를 만듭니다. 코드 예제는 다음과 같습니다.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>스레드 시작 및 중지  
 새 스레드의 실행을 시작하려면 다음 코드와 같이 <xref:System.Threading.Thread.Start%2A> 메서드를 사용합니다.  
  
```vb  
newThread.Start()  
```  
  
 스레드 실행을 중지하려면 다음 코드와 같이 <xref:System.Threading.Thread.Abort%2A> 메서드를 사용합니다.  
  
```vb  
newThread.Abort()  
```  
  
 스레드 시작 및 중지 외에도 <xref:System.Threading.Thread.Sleep%2A> 또는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 호출하여 스레드를 일시 중지하고, <xref:System.Threading.Thread.Resume%2A> 메서드를 사용하여 일시 중단된 스레드를 다시 시작하고, <xref:System.Threading.Thread.Abort%2A> 메서드를 사용하여 스레드를 삭제할 수도 있습니다.  
  
### <a name="thread-methods"></a>스레드 메서드  
 다음 표에서는 개별 스레드를 제어하는 데 사용할 수 있는 메서드 중 일부를 보여 줍니다.  
  
|메서드|작업|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|스레드 실행을 시작합니다.|  
|<xref:System.Threading.Thread.Sleep%2A>|지정된 시간 동안 스레드를 일시 중지합니다.|  
|<xref:System.Threading.Thread.Suspend%2A>|안전한 시점에 도달하면 스레드를 일시 중지합니다.|  
|<xref:System.Threading.Thread.Abort%2A>|안전한 시점에 도달하면 스레드를 중지합니다.|  
|<xref:System.Threading.Thread.Resume%2A>|일시 중지된 스레드를 다시 시작합니다.|  
|<xref:System.Threading.Thread.Join%2A>|현재 스레드에서 다른 스레드가 완료되기를 기다립니다. 시간 제한 값과 함께 사용할 경우 이 메서드는 스레드가 할당된 시간 내에 완료되면 `True`를 반환합니다.|  
  
### <a name="safe-points"></a>안전 지점  
 이러한 메서드의 대부분은 이해하기 쉽지만 *안전 지점*은 생소할 수 있습니다. 안전 지점은 공용 언어 런타임에서 사용되지 않은 변수를 해제하고 메모리를 회수하는 프로세스인 *가비지 수집*을 자동으로 수행해도 안전한 코드 내 위치입니다. 스레드의 <xref:System.Threading.Thread.Abort%2A> 또는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 호출하는 경우 공용 언어 런타임은 코드를 분석하고 스레드 실행을 중지할 적절한 위치를 결정합니다.  
  
### <a name="thread-properties"></a>스레드 속성  
 스레드에는 다음 표에 나와 있는 것처럼 여러 가지 유용한 속성도 포함되어 있습니다.  
  
|속성|값|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|스레드가 활성 상태인 경우 `True` 값을 포함합니다.|  
|<xref:System.Threading.Thread.IsBackground%2A>|스레드가 백그라운드 스레드인지 또는 그래야 하는지를 나타내는 부울 값을 가져오거나 설정합니다. 백그라운드 스레드는 포그라운드 스레드와 유사하지만 백그라운드 스레드의 경우 프로세스가 중지되도록 허용합니다. 프로세스에 속하는 모든 포그라운드 스레드가 중지되면 공용 언어 런타임은 여전히 활성 상태인 백그라운드 스레드에 대해 <xref:System.Threading.Thread.Abort%2A> 메서드를 호출하여 프로세스를 종료합니다.|  
|<xref:System.Threading.Thread.Name%2A>|스레드의 이름을 가져오거나 설정합니다. 대체로 디버그할 때 개별 스레드를 찾는 데 사용됩니다.|  
|<xref:System.Threading.Thread.Priority%2A>|운영 체제에서 스레드 예약의 우선 순위를 지정하는 데 사용되는 값을 가져오거나 설정합니다.|  
|<xref:System.Threading.Thread.ThreadState%2A>|스레드 상태를 설명하는 값을 포함합니다.|  
  
## <a name="thread-priorities"></a>스레드 우선 순위  
 모든 스레드에는 실행할 수 있는 프로세서 시간 조각의 크기를 결정하는 우선 순위 속성이 있습니다. 운영 체제는 우선 순위가 높은 스레드에 더 긴 시간 조각을 할당하고 우선 순위가 낮은 스레드에는 더 짧은 시간 조각을 할당합니다. 새 스레드는 `Normal` 값으로 생성되지만, <xref:System.Threading.Thread.Priority%2A> 속성을 <xref:System.Threading.ThreadPriority> 열거형의 임의 값으로 변경할 수 있습니다.  
  
 다양한 스레드 우선 순위에 대한 자세한 설명은 <xref:System.Threading.ThreadPriority>를 참조하세요.  
  
## <a name="foreground-and-background-threads"></a>포그라운드 및 백그라운드 스레드  
 *포그라운드 스레드*는 무기한 실행되는 반면, *백그라운드 스레드*는 마지막 포그라운드 스레드가 중지되는 즉시 중지됩니다. <xref:System.Threading.Thread.IsBackground%2A> 속성을 사용하여 스레드의 백그라운드 상태를 확인하거나 변경할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>  
 [스레드 동기화(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [다중 스레드 프로시저의 매개 변수 및 반환 값(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [스레딩(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
