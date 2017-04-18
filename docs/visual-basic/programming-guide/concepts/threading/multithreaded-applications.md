---
title: "다중 스레드 응용 프로그램 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5bde7f49a2f2bc8a2e6c1eeab3722428b8a37a95
ms.lasthandoff: 03/13/2017

---
# <a name="multithreaded-applications-visual-basic"></a>다중 스레드 응용 프로그램 (Visual Basic)
Visual basic에서 동시에 여러 작업을 수행 하는 응용 프로그램을 작성할 수 있습니다. 가능성이 있는 작업은 다른 작업을 지연 시킬 프로세스 라고 별도 스레드에서 실행 *다중 스레딩* 또는 *자유 스레딩*합니다.  
  
 다중 스레딩을 사용은 사용자 인터페이스의 별도 스레드에서 실행 하는 프로세서 집약적인 작업 들이 활성 상태로 유지 때문에 사용자 입력에 빠르게 응답 하는 응용 프로그램입니다. 또한 다중 스레딩을 사용 작업 부하가 증가 함에 따라 스레드를 추가할 수 있으므로 확장 가능한 응용 프로그램을 만들 때에 유용 합니다.  
  
## <a name="creating-and-using-threads"></a>스레드 만들기 및 사용  
 응용 프로그램의 스레드의 동작에 대해 더 많은 제어가 필요한 경우에 사용자가 직접 스레드 관리할 수 있습니다. 그러나 올바른 다중 스레드 응용 프로그램을 작성 어려울 수를 채택한: 응용 프로그램 응답 하지 않거나 경쟁 조건으로 인해 발생 하는 일시적인 오류가 발생할 수 있습니다. 자세한 내용은 참조 [스레드로부터 안전한 구성 요소](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)합니다.  
  
 형식의 변수를 선언 하 여 새 스레드를 만들 <xref:System.Threading.Thread>프로시저 또는 새 스레드에서 실행 하려는 메서드의 이름을 제공 하는 생성자를 호출 하 고.</xref:System.Threading.Thread> 코드 예제는 다음과 같습니다.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>스레드 시작 및 중지  
 새 스레드의 실행을 시작 하려면 사용 된 <xref:System.Threading.Thread.Start%2A>메서드를 다음 코드에 나와 있는 것 처럼.</xref:System.Threading.Thread.Start%2A>  
  
```vb  
newThread.Start()  
```  
  
 스레드 실행을 중지 하려면 사용 된 <xref:System.Threading.Thread.Abort%2A>메서드를 다음 코드에 나와 있는 것 처럼.</xref:System.Threading.Thread.Abort%2A>  
  
```vb  
newThread.Abort()  
```  
  
 스레드 시작 및 중지, 외에도 또한 일시 중지할 수 있습니다 스레드를 호출 하 여는 <xref:System.Threading.Thread.Sleep%2A>또는 <xref:System.Threading.Thread.Suspend%2A>메서드를 사용 하 여 일시 중단 된 스레드 재개는 <xref:System.Threading.Thread.Resume%2A>메서드를 <xref:System.Threading.Thread.Abort%2A>메서드</xref:System.Threading.Thread.Abort%2A> 를 사용 하 여 스레드를 제거 하 고</xref:System.Threading.Thread.Resume%2A> </xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Sleep%2A>  
  
### <a name="thread-methods"></a>스레드 메서드  
 다음 표에서 각 스레드를 제어 하는 데 사용할 수 있는 방법 중 일부를 보여 줍니다.  
  
|메서드|작업|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>|스레드의 실행을 시작 합니다.|  
|<xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>|지정된 된 시간에 대 한 스레드를 일시 중지 합니다.|  
|<xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A>|안전한 시점에 도달 하면 스레드를 일시 중지 합니다.|  
|<xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A>|안전한 시점에 도달 하면 스레드를 중지 합니다.|  
|<xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A>|일시 중지 된 스레드를 다시 시작|  
|<xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>|현재 스레드를 다른 스레드가 끝나기를 기다리는 하면 됩니다. 이 메서드가 반환 하는 시간 제한 값을 사용 하는 경우 `True` 스레드가 할당된 된 시간 안에 완료 된 경우.|  
  
### <a name="safe-points"></a>안전한 시점  
 이러한 메서드의 대부분은 새로울 하지만의 개념은 *안전 지점* 게 될 수 있습니다. 안전 지점 있는 것은 안전 공용 언어 런타임에서 자동으로 수행 하는 코드의 위치는 *가비지 수집*, 사용 되지 않은 변수를 해제 하 고 메모리를 회수 하는 데는 프로세스입니다. 호출 하는 경우는 <xref:System.Threading.Thread.Abort%2A>또는 <xref:System.Threading.Thread.Suspend%2A>공용 언어 런타임 스레드 메서드 코드를 분석 하 고 실행을 중지 하려면 스레드에 대 한 적절 한 위치의 위치를 결정 합니다.</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A>  
  
### <a name="thread-properties"></a>스레드 속성  
 스레드는 다음 표에 나와 있는 것 처럼 여러 가지 유용한 속성을 포함 될.  
  
|속성|값|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A>|값이 포함 된 `True` 스레드가 실행 중인 경우.|  
|<xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A>|스레드는 또는 백그라운드 스레드에서 해야 하는 경우를 나타내는 부울 값을 가져오거나 설정 합니다. 백그라운드 스레드는 포그라운드 스레드 유사 하지만 백그라운드 스레드에서 않습니다 막지 프로세스를 중지 합니다. 공용 언어 런타임에서 호출 하 여 프로세스를 종료 하는 프로세스에 속하는 모든 포그라운드 스레드가 중지 되 면는 <xref:System.Threading.Thread.Abort%2A>메서드는 아직 활성화 되어 백그라운드 스레드를.</xref:System.Threading.Thread.Abort%2A>|  
|<xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A>|스레드의 이름을 가져오거나 설정 합니다. 디버깅할 때 개별 스레드를 찾는 가장 자주 사용 됩니다.|  
|<xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A>|스레드의 예약 우선 순위를 지정 하는 운영 체제에서 사용 되는 값을 가져오거나 설정 합니다.|  
|<xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A>|스레드 상태 또는 상태를 설명 하는 값을 포함 합니다.|  
  
## <a name="thread-priorities"></a>스레드 우선 순위  
 모든 스레드는 실행 하는 프로세서 시간을 결정 하는 priority 속성이 있습니다. 운영 체제에는 우선 순위가 높은 스레드 더 긴 시간 간격 및 우선 순위가 낮은 스레드 짧은 시간 조각 할당합니다. 새 스레드 값을 사용 하 여 만들어집니다 `Normal`, 변경할 수 있지만 <xref:System.Threading.Thread.Priority%2A>속성의 값을는 <xref:System.Threading.ThreadPriority>열거형.</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A>  
  
 참조 <xref:System.Threading.ThreadPriority>에 대 한 자세한 설명은 다양 한 스레드 우선 순위.</xref:System.Threading.ThreadPriority>  
  
## <a name="foreground-and-background-threads"></a>포그라운드 및 백그라운드 스레드  
 A *포그라운드 스레드* 무기한 실행 되는 반면는 *백그라운드 스레드* 마지막 포그라운드 스레드가 중지 되는 즉시 중지 합니다. 사용할 수는 <xref:System.Threading.Thread.IsBackground%2A>속성을 확인 하거나 스레드 백그라운드 상태를 변경 합니다.</xref:System.Threading.Thread.IsBackground%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 [스레드 동기화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)   
 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
