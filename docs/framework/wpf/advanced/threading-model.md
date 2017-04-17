---
title: "스레딩 모델 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "업데이트 단추 텍스트"
  - "메시지 처리를 중첩"
  - "작업 차단"
  - "Dispatcher 클래스"
  - "공용 언어 런타임 (CLR), 잠금 메커니즘"
  - "CLR(공용 언어 런타임)의 잠금 메커니즘"
  - "스레드 모델"
  - "DependencyObject 클래스"
  - "Word, 맞춤법을 검사"
  - "단추 텍스트를 업데이트"
  - "Word의 맞춤법 검사"
  - "비동기 동작을 노출"
  - "DependencyObject 클래스"
  - "중첩된 메시지 처리"
  - "Dispatcher 클래스"
  - "재입력 가능성"
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# 스레딩 모델
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]스레딩 문제에서 개발자를 저장 하도록 설계 되었습니다. 결과적으로 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개발자를 둘 이상의 스레드를 사용 하는 인터페이스를 작성할 필요가 없습니다. 다중 스레드 프로그램에는 복잡 하 고 디버그 하기가 어려워질는 이기 때문에 단일 스레드 솔루션이 있는 경우 피해 야 있습니다.  
  
 그러나 아무리 잘 설계 no [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 프레임 워크는 모든 종류의 문제에 대 한 단일 스레드 솔루션 제공 수 있습니다.              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]여러 스레드를 개선 하는 경우가 아직도 있습니다. 하지만 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응답성 또는 응용 프로그램 성능입니다. 배경 정보를 논의 한 후이 문서는 이러한 상황 중 일부를 살펴보고 하 고 마지막으로 일부 하위 수준 세부 정보에 대 한 설명을 합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
> [!NOTE]
>  이 항목에서는 사용 하 여 스레딩는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 비동기 호출에 대 한 메서드. 호출 하 여 비동기 호출을 수행할 수도 있습니다는 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드를 사용 하는 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수로 합니다.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드가 반환 되는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>,이 (가)는 <xref:System.Windows.Threading.DispatcherOperation.Task%2A> 속성입니다. 사용할 수는 `await` 키워드를 사용 하 여는 <xref:System.Windows.Threading.DispatcherOperation> 관련 <xref:System.Threading.Tasks.Task>합니다. 동기적으로 대기 하는 경우는 <xref:System.Threading.Tasks.Task> 에서 반환 하는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>, 호출의 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 확장 메서드.  호출 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> 교착 상태가 발생 합니다. 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Threading.Tasks.Task> 비동기 작업을 수행 하려면 작업 병렬 처리를 참조 하십시오.  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드 역시 오버 로드는 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수로 합니다.  사용할 수는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 대리자를 전달 하 여 동기 아니도록 메서드를 호출 <xref:System.Action> 또는 <xref:System.Func%601>합니다.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>개요 및 디스패처  
 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 두 스레드가 있는 응용 프로그램은 시작: 렌더링 및 관리 하기 위한 다른 처리 하기 위한 하나는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 렌더링 스레드 효과적으로 실행 되는 동안 백그라운드에서 숨겨진는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드 입력을 받고, 이벤트를 처리, 화면을 그리며 및 응용 프로그램 코드를 실행 합니다. 대부분의 응용 프로그램에는 단일 사용 하 여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 상황에 따라 것이 여러 개 사용 하는 가장 좋지만 스레드입니다. 나중에 설명 하겠지만이에 대 한 예입니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드 큐에 작업 항목을 호출 하는 개체는 <xref:System.Windows.Threading.Dispatcher>합니다. <xref:System.Windows.Threading.Dispatcher> 우선 순위 단위로 작업 항목을 선택 하 고 완료 될 때까지 각각 실행 합니다.  모든 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드 하나 이상 있어야 <xref:System.Windows.Threading.Dispatcher>, 및 각 <xref:System.Windows.Threading.Dispatcher> 정확히 한 개의 스레드에서 작업 항목을 실행할 수 있습니다.  
  
 친숙 하 게 응답 응용 프로그램을 구축 하는 것이 중요 최대화 하는 것은 <xref:System.Windows.Threading.Dispatcher> 작업 항목을 작게 유지 하 여 처리량입니다. 이 방법을 사용 하면 항목으로 만들기란에 앉아 부실는 <xref:System.Windows.Threading.Dispatcher> 큐 처리를 위해 대기 합니다. 입력 및 응답 간의 지연 인지할 수 사용자를 해질 수 있습니다.  
  
 그러면 어떻게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 큰 작업을 처리 해야 하는 응용 프로그램? 경우에 어떻게 코드는 큰 계산을 포함 또는 원격 서버에 데이터베이스를 쿼리 하는 데 필요한? 별도 스레드에서 없어지기 큰 작업을 처리 하려면 대답은 일반적으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가의 항목에는 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 그 결과 보고할 수 있어 큰 작업이 완료 되 면 다시는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 디스플레이 대 한 스레드입니다.  
  
 지금까지 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 허용 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소에 자신을 만든 스레드에서 액세스할 수 있습니다. 즉, 완료 되 면 일부 장기 실행 작업을 담당 하는 백그라운드 스레드가 텍스트 상자를 업데이트할 수 없습니다.                  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]이를 통해의 무결성을 보장 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 구성 요소입니다. 목록 상자 내용이 그리기 하는 동안 백그라운드 스레드에 의해 업데이트 될 경우 이상 하 게 보일 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 이러한 조정을 적용 하는 상호 배제를 기본 제공 메커니즘이 있습니다. 대부분의 클래스에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 파생 <xref:System.Windows.Threading.DispatcherObject>합니다. 생성 시는 <xref:System.Windows.Threading.DispatcherObject> 저장에 대 한 참조는 <xref:System.Windows.Threading.Dispatcher> 현재 실행 중인 스레드에 연결 합니다. 실제로 <xref:System.Windows.Threading.DispatcherObject> 을 만든 스레드와 연결 합니다. 프로그램 실행 중 한 <xref:System.Windows.Threading.DispatcherObject> 공용을 호출할 수 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 메서드.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 검사 하는 <xref:System.Windows.Threading.Dispatcher> 현재 스레드와 연결 된 해시와 비교 하는 <xref:System.Windows.Threading.Dispatcher> 생성 시 저장 된 참조입니다. 일치 하지 않으면 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 예외를 throw 합니다.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 시간은에 속하는 모든 메서드의 시작 부분에서 호출을 한 <xref:System.Windows.Threading.DispatcherObject>합니다.  
  
 경우에 하나의 스레드를 수정할 수는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 어떻게 해당 사용자와 상호 작용 백그라운드 스레드 할까요? 백그라운드 스레드를 요청할 수는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 대신에 대 한 작업을 수행 하는 스레드입니다. 이 위해 등록 하는 작업 항목을 여는 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. <xref:System.Windows.Threading.Dispatcher> 클래스에서는 작업 항목을 등록 하기 위한 두 가지 방법: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 및 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>합니다. 두 메서드는 실행에 대 한 대리자를 예약 합니다.                  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 는 동기 호출 – 될 때까지 반환 되지 않는 즉,는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 실제로 대리자 실행을 완료 합니다.                  <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 비동기 이며 즉시 반환 합니다.  
  
 <xref:System.Windows.Threading.Dispatcher> 우선 순위에 따라 큐에는 요소를 정렬 합니다. 에 요소를 추가 하는 경우에 지정 될 수 있는&10; 개의 수준이 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 이러한 우선 순위에서 유지 관리 되는 <xref:System.Windows.Threading.DispatcherPriority> 열거 합니다. 에 대 한 자세한 정보 <xref:System.Windows.Threading.DispatcherPriority> 수준에서 찾을 수 있습니다는 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] 설명서입니다.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>스레드: 샘플  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>장기 실행 계산을 사용 하는 단일 스레드 응용 프로그램  
 대부분 [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] 시간 사용자 상호 작용에 대 한 응답으로 생성 된 이벤트를 기다리는 동안 유휴 상태로의 많은 부분을 소비 합니다. 신중 하 게 프로그래밍이 유휴 시간 없이 사용할 수 있습니다을 생산적으로의 응답성에 영향을 주지는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델에서 발생 하는 작업을 중단 하는 입력을 허용 하지 않습니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 즉, 돌아가려면 확인 해야는 <xref:System.Windows.Threading.Dispatcher> 부실 해지기 전에 입력된 이벤트 보류 중인 프로세스에 주기적으로 합니다.  
  
 다음 예제를 참조하세요.  
  
 ![소수 스크린 샷](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.PNG "ThreadingPrimeNumberScreenShot")  
  
 이 간단한 응용 프로그램 소수&3;, 검색에서 위쪽으로 계산 합니다. 사용자가는 **시작** 단추, 검색을 시작 합니다. 프로그램은 소수를 찾을 때 사용자 인터페이스를 검색 내용으로 업데이트 합니다. 언제 든 지 사용자 검색을 중지할 수 있습니다.  
  
 단순 하지만 충분히 소수 검색 forever 약간의 문제가 이동 수 있습니다.  제공 되지 않습니다, 단추의 click 이벤트 처리기 내에서 전체 검색을 처리 하는 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다른 이벤트를 처리할 기회를 스레드입니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없을 것 입력 또는 프로세스에 응답 하도록 메시지입니다. 다시 그리기를 수행 하 고 단추 클릭에 응답 하지 않을 것입니다.  
  
 별도 스레드에서 소수 검색을 수행할 수 있지만 다음 동기화 문제를 처리 해야 합니다. 단일 스레드 접근 방식을 발견 된 가장 큰 소수를 나열 하는 레이블을 직접 업데이트할 수 있습니다.  
  
 계산 작업을 관리 하기 쉬운 청크로 나누어 우리 우리 주기적으로 돌아갈 수는 <xref:System.Windows.Threading.Dispatcher> 및 이벤트를 처리 합니다. 제공할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다시 그리기 및 입력을 처리할 수 있습니다.  
  
 계산을 관리 하는 계산 및 이벤트 처리 간의 처리 시간을 분할 하는 가장 좋은 방법은 <xref:System.Windows.Threading.Dispatcher>합니다. 사용 하 여는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 메서드를에서 소수 검사를 예약할 수 있습니다 동일한 큐 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트에서 가져온 것입니다. 이 예제에서는 소수 검사를 한 번에만 예약 합니다. 소수 검사가 완료 되 면 다음 확인 즉시 예약 합니다. 보류 중인이 검사 후에 진행 됩니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트가 처리 되었습니다.  
  
 ![디스패처 큐 설명](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)]이 메커니즘을 사용 하 여 맞춤법 검사를 수행 합니다. 유휴 시간을 사용 하 여 백그라운드에서 이루어집니다 맞춤법 검사는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 코드를 살펴보겠습니다.  
  
 다음 예제에서는 사용자 인터페이스를 만드는 XAML을 보여 줍니다.  
  
 [!code-xml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 다음 예제에서는 코드 숨김을 보여 줍니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 다음 예제에서는 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 텍스트를 업데이트 외에도 <xref:System.Windows.Controls.Button>,이 처리기는 대리자를 추가 하 여 첫 번째 소수 검사를 예약 하는 데는 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 이 이벤트 처리기는 작업을 완료 된 후에 따라는 <xref:System.Windows.Threading.Dispatcher> 실행을 위해이 대리자를 선택 합니다.  
  
 앞에서 설명한 것 처럼 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 는 <xref:System.Windows.Threading.Dispatcher> 실행에 대 한 대리자를 예약 하는 데 사용 되는 멤버입니다. 선택한 경우에 <xref:System.Windows.Threading.DispatcherPriority> 우선 순위입니다. <xref:System.Windows.Threading.Dispatcher> 없는 중요 한 이벤트를 처리할 경우에이 대리자를 실행 합니다.                          [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]응답성이 숫자 검사 보다 더 중요 합니다. 또한 숫자 검사 루틴을 나타내는 새 대리자를 전달 합니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 이 메서드는 다음 홀수 소수 인지 확인 합니다. 메서드를 직접 업데이트 프라임 인 경우는 `bigPrime` <xref:System.Windows.Controls.TextBlock> 에서 검색을 반영 하도록 합니다. 구성 요소를 만드는 데 사용한 것과 동일한 스레드에서 계산이 수행 되기 때문에이 수행할 수 있습니다. 계산에 대 한 별도 스레드를 사용 하도록 선택 했습니다, 해야 더 복잡 한 동기화 메커니즘을 사용 하 고 업데이트를 실행은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 그런 다음 이러한 상황 설명 하겠습니다.  
  
 이 샘플의 전체 소스 코드에 대 한 참조는 [장기 실행 계산 샘플을 단일 응용 프로그램](http://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>백그라운드 스레드를 차단 작업 처리  
 그래픽 응용 프로그램에서 차단 작업을 처리 하는 것은 어려울 수 있습니다. 응용 프로그램 고정 하려면 나타나지 않기 때문에 이벤트 처리기에서 차단 메서드를 호출 하지 않으려고 합니다. 이러한 작업을 처리 하는 별도 스레드 사용할 수 있지만와 동기화 해야 작업이 끝났을 때는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 직접 수정할 수 없으므로 스레드는 [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] 작업자 스레드에서 합니다. 사용 하 여 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 에 대리자를 삽입 하는 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 이러한 대리자를 실행 하는 수정할 수 있는 권한을 가진는 결국 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다.  
  
 이 예제에서는 일기 예보 하는 원격 프로시저 호출을 모방 합니다. 이 호출을 실행 하는 별도 작업자 스레드가 사용 하 고 예약에서 업데이트 메서드는 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 과정이 완료 되 면 스레드입니다.  
  
 ![날씨 UI 스크린 샷을](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.png "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 다음은 몇 가지 주의 해야 할 세부 정보입니다.  
  
-   단추 처리기 만들기  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 단추를 클릭할 때 시계 그리기가 표시 되 고 애니메이션 효과가 시작 합니다. 단추를 비활성화 합니다. 호출 된 `FetchWeatherFromServer` 메서드는 새 스레드를 제거한 다음에 돌아옵니다는 <xref:System.Windows.Threading.Dispatcher> 일기 예보를 수집 하도록 기다리는 동안에 이벤트를 처리 하 합니다.  
  
-   날씨 페칭 (fetching)  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 단순화 하기 위해 실제로 않아도 네트워킹 코드이 예제에서입니다. 대신,&4; 초 동안 일시 중지 되는 새 스레드를 배치 하 여 네트워크 액세스의 지연을 시뮬레이션 합니다. 원래가이 시간 내에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 여전히 실행 중 이며 이벤트에 응답 합니다. 이 실행 하 고, 애니메이션 및 최소화 두었으며 표시 하 고 극대화 하려면 단추 계속 작동 합니다.  
  
 지연 끝나고 일기 예보 임의로 선택 했으며, 경우에 시간에 보고 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 에 대 한 호출을 예약 하 여이 작업을 수행 `UpdateUserInterface` 에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 해당 스레드를 사용 하 여 스레드 <xref:System.Windows.Threading.Dispatcher>합니다. 이 예약 된 메서드 호출에 대 한 날씨를 설명 하는 문자열을 전달 합니다.  
  
-   업데이트는[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 경우는 <xref:System.Windows.Threading.Dispatcher> 에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에 시간에 예약 된 호출을 실행 합니다 `UpdateUserInterface`합니다. 이 메서드는 시계 애니메이션을 중지 하 고 날씨를 설명 하기 위해 이미지를 선택 합니다. 이 이미지를 표시 하 고 "인출 예측" 단추를 복원 합니다.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>여러 창, 여러 스레드  
 일부 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에는 최상위 창이 여러 개 필요 합니다. 한 스레드에서 완벽 하 게 되어도 / <xref:System.Windows.Threading.Dispatcher> 더 나은 작업을 수행 하는 여러 개의 창을 하지만 때로는 여러 스레드를 관리 하는 조합 합니다. 이 windows 중 하나는 스레드가 독점할 가능성이 있을 경우 특히 그렇습니다.  
  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]탐색기는 이러한 방식으로 작동합니다. 각 새 탐색기 창을 원래 프로세스에 속하지만 독립적인 스레드의 컨트롤 아래에 만들어집니다.  
  
 사용 하 여 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> 컨트롤을 웹 페이지를 표시할 수 있습니다. 간단한 쉽게 만들 수 있습니다 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 대체 합니다. 시작 하는 중요 한 기능: 새 탐색기 창을 열 수 있습니다. "새 창"를 클릭 하면 단추는 별도의 스레드에서 창 사본을 시작 합니다. 이러한 방식으로 창 중 하나에 있는 장기 실행 또는 차단 작업이 다른 모든 창과 잠그지 않습니다.  
  
 실제로 웹 브라우저 모델을는 복잡 한 자체 스레딩 모델이 있습니다. 대부분의 독자에 잘 알고 있어야 하기 때문에 선택 했습니다 했습니다.  
  
 다음 예제에서는 코드를 보여 줍니다.  
  
 [!code-xml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 이 코드의 다음 스레딩 세그먼트는 가장 흥미로운 우리에 게이 컨텍스트에서  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 이 메서드를 호출한 경우 "새 창" 단추를 클릭 합니다. 새 스레드를 생성 하 고 비동기적으로 시작 합니다.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 이 메서드는 새 스레드 시작 지점입니다. 이 스레드의 제어 새 창을 만듭니다.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 자동으로 새 <xref:System.Windows.Threading.Dispatcher> 새 스레드를 관리할 수 있습니다. 창 작동할 수 있도록 수행 해야 하는 시작 된 <xref:System.Windows.Threading.Dispatcher>합니다.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>기술 세부 정보 및 장애 요소  
  
### <a name="writing-components-using-threading"></a>스레딩 사용 하 여 구성 요소 작성  
 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] 구성 요소 수를 클라이언트에 비동기 동작을 노출 하는 방법에 대 한 패턴을 설명 하는 개발자 가이드 (참조 [이벤트 기반 비동기 패턴 개요](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). 예를 들어, 패키지를 `FetchWeatherFromServer` 메서드를 다시 사용할 수 있는, 비그래픽 구성 요소에 있습니다. 표준 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] 패턴을 다음과 같이이 같습니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync`사용 합니다 백그라운드 스레드를 만드는 것과 같은 앞에서 설명한 방법 중 하나는 작업을 비동기적으로 수행 호출 스레드를 차단 하지 않습니다.  
  
 호출 하는이 패턴의 가장 중요 한 부분 중 하나는 *MethodName* `Completed` 메서드를 호출한 스레드와 동일한 스레드에서 *MethodName* `Async` 메서드를 시작 합니다. 사용 하 여 수행할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 저장 하 여 쉽게 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>-다음 비그래픽 구성 요소 에서만 사용할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 없는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] 프로그램입니다.  
  
 <xref:System.Windows.Threading.DispatcherSynchronizationContext> 클래스에는이 요구 사항을 해결-의 단순화 된 버전으로 한다는 점만 <xref:System.Windows.Threading.Dispatcher> 는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 프레임 워크에도 있습니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>중첩 된 펌프  
 때로는 적합 하지 않다고를 완전히 잠그는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 살펴보겠습니다는 <xref:System.Windows.MessageBox.Show%2A> 의 메서드는 <xref:System.Windows.MessageBox> 클래스입니다.                          <xref:System.Windows.MessageBox.Show%2A> 확인 단추를 클릭할 때까지 반환 하지 않습니다. 그러나이 메서드는 메시지 루프를 위해 대화형 있어야 하는 창을 만듭니다. 확인을 클릭 하 여 사용자에 대 한 대기 중인 동안에 원래 응용 프로그램 창은 사용자 입력에 응답 하지 않습니다. 하지만 그리기 메시지를 처리, 계속 해 서입니다. 원본 창 졌다가 표시 될 때 다시 그려집니다.  
  
 !["확인" 단추가 있는 MessageBox](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 일부 스레드는 메시지 상자 창 담당 해야 합니다.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]메시지 상자 창에 대해서만 새 스레드를 만들 수 있지만이 스레드는 원래 창에서 사용할 수 없는 요소를 그릴 수 없습니다 (이전 설명은 상호 배제를 기억). 대신, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리 시스템 중첩 된 메시지를 사용 합니다. <xref:System.Windows.Threading.Dispatcher> 라는 특수 메서드를 포함 하는 클래스 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, 그런 다음 응용 프로그램의 현재 실행 위치를 저장 하는 새 메시지 루프를 시작 합니다. 중첩된 메시지 루프가 완료 되 면 실행이 다시 시작 후 원래 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 를 호출 합니다.  
  
 이 경우 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 호출 될 때 프로그램 컨텍스트를 유지 관리 <xref:System.Windows.MessageBox>합니다.                         <xref:System.Windows.MessageBox.Show%2A>, 배경 그리기 및 메시지 상자 창에 대 한 입력을 처리 하는 새 메시지 루프를 시작 합니다. 사용자가 확인을 클릭 하 고 팝업 창을 지웁니다, 중첩 된 루프 종료 되 고 제어를 다시 시작에 대 한 호출 <xref:System.Windows.MessageBox.Show%2A>합니다.  
  
### <a name="stale-routed-events"></a>유효 하지 않은 라우트된 이벤트  
 라우트된 이벤트 시스템 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트가 발생 하면 전체 트리를 알립니다.  
  
 [!code-xml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 타원 위로 마우스 왼쪽된 단추를 누를 때 `handler2` 실행 됩니다. 후 `handler2` 완료 되 면 이벤트에 전달 됩니다는 <xref:System.Windows.Controls.Canvas> 개체를 사용 하 여 `handler1` 처리 합니다. 이런 경우에 `handler2` 가 명시적으로 표시 이벤트 개체를 처리 합니다.  
  
 수 있는 `handler2` 이 이벤트를 처리 하는 시간이 많이 걸립니다.                          `handler2`사용할 수 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 시간에 대 한 반환 하지 않는 중첩된 메시지 루프를 시작 합니다. 경우 `handler2` 는 매우 오래 된 경우에 트리 위로 이벤트가 전달 되기, 이벤트 처리 되므로이 메시지 루프가 되었을 때 완료 하는 표시 되지 않습니다.  
  
### <a name="reentrancy-and-locking"></a>재진입 및 잠금  
 잠금 메커니즘은는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 와 동일 하 게 동작 하지는 않습니다 예상한 것, 하나는 스레드는 잠금을 요청할 때 작업을 완전히 중단할를 예상 합니다. 실제로 스레드는 계속 수신 하 고 우선 순위가 높은 메시지를 처리 합니다. 교착 상태와 인터페이스를 최소한으로 응답 하도록 확인 되지만 미묘한 버그가 발생할 가능성이 있습니다.  이 있지만 드문 알아야 할 없어도 시간의 대부분 (일반적으로 관련 된 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 메시지 또는 STA COM 구성 요소)이 있다는 사실을 알고 수 있습니다.  
  
 개발자가 작업 가정 하기 때문에 대부분의 인터페이스 스레드 안전을 고려 빌드되지 않는 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 둘 이상의 스레드가 액세스 하지 않습니다. 예기치 않은 시간에 단일 스레드 환경 변화를 만들 수 있는지,이 경우에서에 영향 시켜는 <xref:System.Windows.Threading.DispatcherObject> 상호 배제 메커니즘은 해결 해야 합니다. 다음 의사 코드를 고려 합니다.  
  
 ![스레딩 재입력 가능성 다이어그램](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 문제가 되지 않지만 대부분의 경우에는 이것이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이러한 예상치 않은 재진입 문제가 발생할 실제로 수 있습니다. 따라서 특정 주요 시간 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호출 <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, 잠금 명령을 사용 하 여 해당 스레드에 대 한 변경 내용을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 일반적인 대신 재진입 없는 잠금 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 잠금.  
  
 보십시오 않았습니다는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 팀이이 동작을 선택한? 단일 스레드 COM 개체 및 종료 스레드 했습니다. 개체가 가비지 수집 해야 하는 경우 해당 `Finalize` 메서드 전용된 종료자 스레드에서 실행 되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 및 여기에 문제가, COM STA 개체를 생성 된에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에만 삭제할 수는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 해당 하는 작업을 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (이 경우 w i n&32;의를 사용 하 여 `SendMessage`). 하지만 경우에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 종료자 스레드는 중단 하 고 COM STA 개체를 삭제할 수 없으므로, 심각한 메모리 누수가 발생 합니다. 따라서 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 팀을 내린 하는 방식으로 작동 하는 잠금을 수행 합니다.  
  
 에 대 한 작업 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예기치 않은 다시 표시 되는 모든 위치에서 다시 표시를 차단 하지 않도록 우리 이유 메모리 누수를 다시 초래 하지 않고 방지 하는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [장기 실행 계산 샘플을 단일 스레드 응용 프로그램](http://go.microsoft.com/fwlink/?LinkID=160038)