---
title: "데이터 흐름(작업 병렬 라이브러리) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "작업 병렬 라이브러리, 데이터 흐름"
  - "TPL 데이터 흐름 라이브러리"
ms.assetid: 643575d0-d26d-4c35-8de7-a9c403e97dd6
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# 데이터 흐름(작업 병렬 라이브러리)
<a name="top"></a>병렬 라이브러리 TPL (작업) 동시성 사용 응용 프로그램의 견고성을 향상 시키기 위해 데이터 흐름 구성 요소를 제공 합니다. 이러한 데이터 흐름 구성 요소는 전체적으로 라고 하는 *TPL 데이터 흐름 라이브러리*합니다. 이 데이터 흐름 모델은 정교하지 않은 데이터 흐름 및 파이프라인 작업을 위해 in-process 메시지 전달을 제공하여 행위자 기반 프로그래밍을 촉진합니다. 데이터 흐름 구성 요소는 TPL의 형식 및 예약 인프라를 바탕으로 빌드되며 비동기 프로그래밍에 대한 C#, [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 및 F# 언어 지원과 통합됩니다. 이러한 데이터 흐름 구성 요소는 비동기적으로 서로 통신해야 하는 여러 작업이 있는 경우나 데이터를 사용할 수 있게 될 때 해당 데이터를 처리하려는 경우에 유용합니다. 예를 들어 웹 카메라에서 이미지 데이터를 처리하는 응용 프로그램의 경우, 데이터 흐름 모델을 사용함으로써 응용 프로그램은 이미지 프레임을 사용할 수 있게 될 때 해당 이미지 프레임을 처리할 수 있습니다. 응용 프로그램 이미지 프레임을 개선 하는 경우 예를 들어 밝은 조정 하거나 적목 현상을 줄이는 수행 하 여 만들 수 있습니다는 *파이프라인* 데이터 흐름 구성 요소입니다. 파이프라인의 각 단계에서는 TPL이 제공하는 기능과 같은 좀더 정교하지 않은 병렬 처리 기능을 사용하여 이미지를 변환할 수도 있습니다.  
  
 이 문서에서는 TPL 데이터 흐름 라이브러리에 대한 개요를 제공합니다. 여기에서는 프로그래밍 모델, 미리 정의된 데이터 흐름 블록 형식 및 응용 프로그램의 특정 요구 사항을 충족하도록 데이터 흐름 블록을 구성하는 방법을 설명합니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 (<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스)와 함께 배포 되지 않는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]합니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에서 온라인으로 검색은 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
 이 문서는 다음 섹션으로 구성됩니다.  
  
-   [프로그래밍 모델](#model)  
  
-   [미리 정의 된 데이터 흐름 블록 형식](#predefined_types)  
  
-   [데이터 흐름 블록 동작 구성](#behavior)  
  
-   [사용자 지정 데이터 흐름 블록](#custom)  
  
<a name="model"></a>   
## <a name="programming-model"></a>프로그래밍 모델  
 TPL 데이터 흐름 라이브러리는 처리량이 많고 대기 시간이 짧으며 CPU 및 I/O를 많이 사용하는 응용 프로그램의 메시지 전달 및 병렬화를 위한 기반을 제공합니다. 또한 데이터가 버퍼링되고 시스템에서 이동하는 방식을 명시적으로 제어할 수 있도록 합니다. 데이터 흐름 프로그래밍 모델을 보다 정확히 이해하려면 디스크에서 이미지를 비동기적으로 로드하고 해당 이미지의 합성을 만드는 응용 프로그램을 고려해 보십시오. 기존의 프로그래밍 모델에서는 대개 콜백과 동기화 개체(예: 잠금)를 사용하여 작업을 조정하고 공유 데이터에 액세스해야 합니다. 데이터 흐름 프로그래밍 모델을 사용하면 디스크에서 이미지를 읽을 때 해당 이미지를 처리하는 데이터 흐름 개체를 만들 수 있습니다. 데이터 흐름 모델에서는 데이터를 사용할 수 있게 될 때 데이터가 처리되는 방법과 데이터 간의 종속성도 선언합니다. 런타임에서 데이터 간의 종속성을 관리하기 때문에 대개 공유 데이터에 대한 액세스를 동기화할 필요가 없습니다. 또한 런타임에서 데이터의 비동기 도착을 기준으로 작업을 예약하기 때문에 데이터 흐름은 내부 스레드를 효율적으로 관리하여 응답성과 처리량을 개선할 수 있습니다. 데이터 흐름 프로그래밍 모델을 사용 하 여 Windows Forms 응용 프로그램에서 이미지 처리를 구현 하는 예제를 보려면 [연습: Windows Forms 응용 프로그램에서 사용 하 여 데이터 흐름](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)합니다.  
  
### <a name="sources-and-targets"></a>소스 및 대상  
 TPL 데이터 흐름 라이브러리는 이루어져 *데이터 흐름 블록*, 해당 버퍼 및 프로세스 데이터는 데이터 구조인 합니다. TPL 데이터 흐름 블록의 세 가지 종류를 정의: *소스 블록*, *대상 블록*, 및 *전파자 블록*합니다. 소스 블록은 데이터의 소스 역할을 하며 읽을 수 있습니다. 대상 블록은 데이터의 수신자 역할을 하며 쓸 수 있습니다. 전파자 블록은 소스 블록과 대상 블록 역할을 하며 읽고 쓸 수 있습니다. TPL 정의 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=fullName> 소스를 나타내는 인터페이스 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=fullName> , 대상을 나타내는 및 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602?displayProperty=fullName> 전파자를 나타내는.</TInput, TOutput> <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 에서 모두 상속 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>합니다.\</TInput, TOutput>  
  
 TPL 데이터 흐름 라이브러리를 구현 하는 몇 가지 미리 정의 된 데이터 흐름 블록 형식을 제공는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, 및 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 인터페이스.\</TInput, TOutput> 이러한 데이터 흐름 블록 형식은이 문서의 섹션에 설명 되어 [미리 정의 된 데이터 흐름 블록 형식](#predefined_types)합니다.  
  
### <a name="connecting-blocks"></a>블록 연결  
 폼에 데이터 흐름 블록을 연결할 수 있습니다 *파이프라인*, 데이터 흐름 블록의 선형 시퀀스인 또는 *네트워크*, 데이터 흐름 블록의 그래프는 합니다. 파이프라인은 네트워크의 한 형태입니다. 파이프라인 또는 네트워크에서 소스는 데이터를 사용할 수 있게 되면 대상에 데이터를 비동기적으로 전파합니다. <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A?displayProperty=fullName> 메서드는 소스 데이터 흐름 블록을 대상 블록에 연결 합니다. 소스는&0;개 이상의 대상에 연결될 수 있으며, 대상은&0;개 이상의 소스에서 연결될 수 있습니다. 파이프라인 또는 네트워크에서 데이터 흐름 블록을 동시에 추가하거나 제거할 수 있습니다. 미리 정의된 데이터 흐름 블록 형식은 연결 및 연결 해제의 모든 스레드로부터의 안전성 측면을 처리합니다.  
  
 기본 파이프라인을 구성 하도록 데이터 흐름 블록을 연결 하는 예제를 참조 하십시오. [연습: 데이터 흐름 파이프라인 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)합니다. 좀 더 복잡 한 네트워크를 구성 하도록 데이터 흐름 블록을 연결 하는 예제를 참조 하십시오. [연습: Windows Forms 응용 프로그램에서 사용 하 여 데이터 흐름](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)합니다. 대상에 메시지를 제공한 후 소스에서 대상의 연결을 해제 하는 예제를 보려면 [하는 방법: 데이터 흐름 블록 링크 끊기](../../../docs/standard/parallel-programming/how-to-unlink-dataflow-blocks.md)합니다.  
  
#### <a name="filtering"></a>필터링  
 호출 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A?displayProperty=fullName> 소스를 대상에 연결 하는 메서드는 대상 블록 수락 메시지의 값에 따라 메시지를 거부 하는지 여부를 결정 하는 대리자를 제공할 수 있습니다. 이 필터링 메커니즘은 데이터 흐름 블록이 특정 값만 받도록 보장하는 유용한 방법입니다. 대부분의 미리 정의된 데이터 흐름 블록 형식의 경우 소스 블록이 여러 대상 블록에 연결되어 있으면 대상 블록이 메시지를 거부할 때 소스는 그 다음 대상에 해당 메시지를 제공합니다. 소스가 대상에 메시지를 제공하는 순서는 소스에 의해 정의되며 소스의 형식에 따라 달라질 수 있습니다. 대부분의 소스 블록 형식은 한 대상이 메시지를 수락할 후 해당 메시지의 제공을 중지합니다. 이 규칙에 대 한 예외는 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 일부 대상이 메시지를 거부 하는 경우에 모든 대상에 각 메시지를 제공 하는 클래스입니다. 필터링을 사용 하 여 특정 메시지만 처리 하는 예제를 보려면 [연습: Windows Forms 응용 프로그램에서 사용 하 여 데이터 흐름](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)합니다.  
  
> [!IMPORTANT]
>  미리 정의된 각 소스 데이터 흐름 블록 형식은 메시지가 수신된 순서대로 전파되도록 보장하기 때문에 각 메시지를 소스 블록에서 읽어온 후에야 소스 블록이 다음 메시지를 처리할 수 있습니다. 따라서 필터링을 사용하여 여러 대상을 소스에 연결하는 경우 적어도 하나의 대상 블록이 각 메시지를 받는지 확인해야 합니다. 이렇게 하지 않으면 응용 프로그램에서 교착 상태가 발생할 수도 있습니다.  
  
### <a name="message-passing"></a>메시지 전달  
 데이터 흐름 프로그래밍 모델의 개념을 관련 되어 *메시지 전달*, 메시지를 전송 하 여 프로그램의 개별 구성 요소가 서로 통신 하는 위치입니다. 응용 프로그램 구성 요소 간에 메시지를 전파 하는 방법을 호출 하는 것은 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 및 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=fullName> 대상 데이터 흐름 블록 게시에 메시지를 보내는 메서드 (<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 고, 그렇지 않으면 역할 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 은 비동기적으로 동작) 및 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A>, 및 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A> 소스 블록에서 메시지를 받는 방법입니다. 입력 데이터를 헤드 노드(대상 블록)에 보내고 출력 데이터를 파이프라인의 터미널 노드나 네트워크의 터미널 노드(하나 이상의 소스 블록)에서 받는 방법으로 이러한 메서드를 데이터 흐름 파이프라인 또는 네트워크와 결합할 수 있습니다. 사용할 수도 있습니다는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Choose%2A> 메서드는 첫 번째에서 읽기를 제공 된 원본에 데이터를 사용할 수 있으며 해당 데이터에 대해 작업을 수행 합니다.  
  
 소스 블록 호출 하 여 대상 블록에 데이터를 제공 된 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601.OfferMessage%2A?displayProperty=fullName> 메서드. 대상 블록은 세 가지 방법 중 하나로 제공된 메시지에 응답합니다. 즉, 메시지를 수락하거나, 메시지를 거부하거나, 메시지를 연기할 수 있습니다. 대상에 메시지를 수락 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601.OfferMessage%2A> 메서드가 반환한 <xref:System.Threading.Tasks.Dataflow.DataflowMessageStatus>합니다. 대상에 메시지를 거부 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601.OfferMessage%2A> 메서드가 반환한 <xref:System.Threading.Tasks.Dataflow.DataflowMessageStatus>합니다. 대상 소스에서 모든 메시지를 더 이상 받지 않도록 요구 하는 경우 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601.OfferMessage%2A> 반환 <xref:System.Threading.Tasks.Dataflow.DataflowMessageStatus>합니다. 미리 정의된 소스 블록 형식은 이러한 반환 값이 수신된 후 연결된 대상에 메시지를 보내지 않으며 해당 대상의 연결을 자동으로 해제합니다.  
  
 대상 블록이 나중에 사용할 메시지를 연기 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601.OfferMessage%2A> 메서드가 반환한 <xref:System.Threading.Tasks.Dataflow.DataflowMessageStatus>합니다. 메시지를 연기 하는 대상 블록에 대 한 후속 호출 수는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.ReserveMessage%2A?displayProperty=fullName> 메서드를 제공 된 메시지를 예약 하려고 시도 합니다. 이 시점에서 해당 메시지는 여전히 사용 가능하여 대상 블록이 사용할 수 있거나, 다른 대상이 사용하고 있는 상태입니다. 대상 블록은 나중에 메시지가 필요 하거나 더 이상 필요 없는 메시지, 호출 된 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.ConsumeMessage%2A?displayProperty=fullName> 또는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.ReleaseReservation%2A> 메서드를 각각. 메시지 예약은 non-greedy 모드에서 작동하는 데이터 흐름 블록 형식에서 주로 사용됩니다. non-greedy 모드는 이 문서의 뒷부분에 설명되어 있습니다. 대상 블록은 연기 된 메시지를 예약 하는 대신 ç ï는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.ConsumeMessage%2A?displayProperty=fullName> 메서드를 직접 연기 된 메시지를 사용 하려고 합니다.  
  
### <a name="dataflow-block-completion"></a>데이터 흐름 블록 완료  
 데이터 흐름 블록의 개념도 지원 *완료*합니다. 완료된 상태에 있는 데이터 흐름 블록은 더 이상 작업을 수행하지 않습니다. 각 데이터 흐름 블록에 연결 된 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 이라고 하는 개체는 *완료 작업*, 블록의 완료 상태를 나타내는입니다. 기다릴 수는 <xref:System.Threading.Tasks.Task> 완료 작업을 사용 하 여 완료 되기를 기다릴 수 있습니다 하나 또는 끝나기를 터미널 노드는 데이터 흐름의 네트워크 개체입니다. <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스 정의 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 데이터 흐름 블록의 완료에 대 한 요청을 알리는, 메서드 및 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Completion%2A> 데이터 흐름 블록에 대 한 완료 작업을 반환 하는 속성을 합니다. 둘 다 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 상속는 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 인터페이스입니다.  
  
 데이터 흐름 블록이 오류 없이 완료되었는지, 하나 이상의 오류가 발생했는지, 아니면 취소되었는지를 확인하는 두 가지 방법이 있습니다. 첫 번째 방법은 호출 하는 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> 완료 작업에 대 한 메서드는 `try` - `catch` 블록 (`Try` - `Catch` Visual basic에서). 다음 예제에서는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체를 throw 하는 <xref:System.ArgumentOutOfRangeException> 입력된 값은&0; 보다 작은 경우. <xref:System.AggregateException> 이 예제에서는 호출 하는 경우, 예외가 <xref:System.Threading.Tasks.Task.Wait%2A> 완료 작업에 대해 합니다. <xref:System.ArgumentOutOfRangeException> 을 통해 액세스는 <xref:System.AggregateException.InnerExceptions%2A> 의 속성은 <xref:System.AggregateException> 개체입니다.  
  
 [!code-csharp[TPLDataflow_Overview#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#10)]
 [!code-vb[TPLDataflow_Overview#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#10)]  
  
 이 예제에서는 예외가 예외 데이터 흐름 블록의 대리자에서 처리되지 않는 경우를 보여 줍니다. 이러한 블록의 본문에서 예외를 처리하는 것이 좋습니다. 그러나 이렇게 할 수 없는 경우 블록은 메시지가 취소된 것처럼 동작하고 들어오는 메시지를 처리하지 않습니다.  
  
 데이터 흐름 블록이 명시적으로 취소 되는 경우는 <xref:System.AggregateException> 개체에 포함 되어 <xref:System.OperationCanceledException> 에 <xref:System.AggregateException.InnerExceptions%2A> 속성입니다. 데이터 흐름 취소에 대한 자세한 내용은 이 문서 뒷부분의 취소 사용을 참조하십시오.  
  
 데이터 흐름 블록의 완료 상태를 확인하는 두 번째 방법은 완료 작업의 연속을 사용하거나, C# 및 Visual Basic의 비동기 언어 기능을 사용하여 완료 작업을 비동기적으로 기다리는 것입니다. 에 제공 하는 대리자는 <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=fullName> 메서드는 <xref:System.Threading.Tasks.Task> 선행 작업을 나타내는 개체입니다. 경우에 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Completion%2A> 속성을 연속의 대리자는 완료 작업 자체를 사용 합니다. 다음 예제에서는 이전 예제와 유사를 사용 하 여 제외 하 고는 <xref:System.Threading.Tasks.Task.ContinueWith%2A> 방법을 전반적인 데이터 흐름 작업의 상태를 출력 하는 완료 작업을 만들 수 있습니다.  
  
 [!code-csharp[TPLDataflow_Overview#11](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#11)]
 [!code-vb[TPLDataflow_Overview#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#11)]  
  
 사용할 수도 있습니다 속성 같은 <xref:System.Threading.Tasks.Task.IsCanceled%2A> 데이터 흐름 블록의 완료 상태에 대 한 추가 정보를 확인 하는 연속 작업의 본문에 있습니다. 연속 작업 및 관계를 취소 및 오류 처리에 대 한 자세한 내용은 참조 [연속 작업을 사용 하 여 작업 연결](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md), [작업 취소](../../../docs/standard/parallel-programming/task-cancellation.md), [예외 처리](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md), 및 [NIB: 방법: 작업에서 발생 한 예외 처리](http://msdn.microsoft.com/ko-kr/d6c47ec8-9de9-4880-beb3-ff19ae51565d).  
  
 [[go to top](#top)]  
  
<a name="predefined_types"></a>   
## <a name="predefined-dataflow-block-types"></a>미리 정의된 데이터 흐름 블록 형식  
 TPL 데이터 흐름 라이브러리는 몇 가지 미리 정의된 데이터 흐름 블록 형식을 제공합니다. 이러한 형식은 세 가지 범주로 구분 됩니다: *버퍼링 블록*, *실행 블록*, 및 *그룹 블록*합니다. 다음 단원에서는 이러한 범주를 구성하는 블록 형식에 대해 설명합니다.  
  
### <a name="buffering-blocks"></a>버퍼링 블록  
 버퍼링 블록은 데이터 소비자가 사용할 데이터를 포함합니다. TPL 데이터 흐름 라이브러리는 세 가지 버퍼링 블록 형식인 제공: <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601?displayProperty=fullName>, 및 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601?displayProperty=fullName>합니다.  
  
#### <a name="bufferblockt"></a>BufferBlock(T)  
 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 일반적인 용도의 비동기 메시징 구조를 나타냅니다. 이 클래스는 여러 소스가 기록하거나 여러 대상이 읽을 수 있는 메시지의 FIFO(선입 선출) 큐를 저장합니다. 대상에서 메시지를 수신 하는 경우는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체를 해당 메시지가 메시지 큐에서 제거 됩니다. 따라서 있지만 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체에는 여러 대상이 있을 수 있습니다, 하나의 대상만 각 메시지를 받게 됩니다. <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 클래스는 다른 구성 요소에 여러 개의 메시지를 전달 하 고 해당 구성 요소는 각 메시지를 수신 해야 하는 경우 유용 합니다.  
  
 다음 기본 예제에서는 여러 가지 게시물 <xref:System.Int32> 값을 한 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체를 한 다음 해당 개체에서 다시 해당 값을 읽습니다.  
  
 [!code-csharp[TPLDataflow_Overview#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#1)]
 [!code-vb[TPLDataflow_Overview#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#1)]  
  
 메시지를 작성 하 고 메시지를 읽는 방법을 보여 주는 전체 예제는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체, 참조 [하는 방법: 메시지를 작성 하 고 데이터 흐름 블록에서 메시지 읽기](../../../docs/standard/parallel-programming/how-to-write-messages-to-and-read-messages-from-a-dataflow-block.md)합니다.  
  
#### <a name="broadcastblockt"></a>BroadcastBlock(T)  
 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 클래스는 다른 구성 요소를 여러 개의 메시지를 전달 해야 하지만 해당 구성 요소에는 가장 최근의 값만 필요한 경우에 유용 합니다. 이 클래스는 여러 구성 요소에 메시지를 브로드캐스트하려고 할 때도 유용합니다.  
  
 다음 기본 예제에서는 게시물은 <xref:System.Double> 값을 한 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 개체와 해당 값이 개체에서 여러 번 읽습니다. 값에서 제거 되지 않기 때문에 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 개체를 읽은 후 동일한 값이 제공 될 때마다 합니다.  
  
 [!code-csharp[TPLDataflow_Overview#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#2)]
 [!code-vb[TPLDataflow_Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#2)]  
  
 사용 하는 방법을 보여 주는 전체 예제 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 여러 대상 블록에 메시지를 브로드캐스트를 참조 하십시오. [하는 방법: 데이터 흐름 블록의 작업 스케줄러 지정](../../../docs/standard/parallel-programming/how-to-specify-a-task-scheduler-in-a-dataflow-block.md)합니다.  
  
#### <a name="writeonceblockt"></a>WriteOnceBlock(T)  
 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 클래스와 유사는 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 점을 제외 하 고 클래스는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 한 번만 쓸 수 있습니다. 생각할 수 있습니다 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> C# 유사한 것으로 [readonly](../Topic/readonly%20\(C%23%20Reference\).md) ([ReadOnly](../Topic/ReadOnly%20\(Visual%20Basic\).md) 에서 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 키워드를 제외 하 고는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체는 생성 시가 아니라 값을 받은 후에 변경할 수 없는 합니다. 마찬가지로 <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 대상에서 메시지를 받을 때 클래스는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체를 해당 메시지는 해당 개체에서 제거 되지 않습니다. 따라서 여러 대상이 하나의 메시지 복사본을 수신합니다. <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 클래스는 여러 메시지 중 첫 메시지만 전파 하려는 경우 유용 합니다.  
  
 다음 기본 예제에서는 여러 게시 <xref:System.String> 값을 한 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체 한 다음 해당 개체에서 값을 다시 읽습니다. 때문에 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 개체에 한 번에 쓸 수 후에,는 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 메시지를 수신 하는 개체를 후속 메시지를 삭제 합니다.  
  
 [!code-csharp[TPLDataflow_Overview#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#3)]
 [!code-vb[TPLDataflow_Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#3)]  
  
 사용 하는 방법을 보여 주는 전체 예제 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 완료 되는 첫 번째 작업의 값을 받으려면 참조 [하는 방법: 데이터 흐름 블록 링크 끊기](../../../docs/standard/parallel-programming/how-to-unlink-dataflow-blocks.md)합니다.  
  
### <a name="execution-blocks"></a>실행 블록  
 실행 블록은 수신된 데이터의 각 조각에 대해 사용자가 제공한 대리자를 호출합니다. TPL 데이터 흐름 라이브러리는 세 가지 실행 블록 형식을 제공: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName>.\</TInput, TOutput> \</TInput, TOutput>  
  
#### <a name="actionblockt"></a>ActionBlock(T)  
 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 클래스는 데이터를 받을 때 대리자를 호출 하는 대상 블록입니다. 생각 하면는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체로 데이터를 사용할 수 있게 되 면 비동기적으로 실행 하는 대리자입니다. 에 제공 하는 대리자는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체 형식이 될 수 있습니다 <xref:System.Action> 종류나 `System.Func\<TInput, Task>`합니다. 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체 <xref:System.Action>, 각 입력 요소의 처리는 대리자가 반환 될 때 완료 된 것으로 간주 됩니다. 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체 `System.Func\<TInput, Task>`, 각 입력 요소의 처리 경우에만 완료 된 것으로 간주 됩니다 반환 된 <xref:System.Threading.Tasks.Task> 개체가 완료 되 합니다. 이러한 두 가지 메커니즘을 사용 하 여 사용할 수 있습니다 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 각 입력 요소의 동기 및 비동기 처리를 위해.  
  
 다음 기본 예제에서는 여러 게시 <xref:System.Int32> 값에 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 해당 값을 콘솔에 출력 합니다. 그런 다음 이 예제에서는 블록을 완료된 상태로 설정하고 모든 데이터 흐름 작업이 완료될 때까지 대기합니다.  
  
 [!code-csharp[TPLDataflow_Overview#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#4)]
 [!code-vb[TPLDataflow_Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#4)]  
  
 와 함께 대리자를 사용 하는 방법을 보여 주는 전체 예제는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 클래스를 참조 하십시오 [하는 방법: 수행 작업 때는 데이터 흐름 블록에서 데이터를 받을](../../../docs/standard/parallel-programming/how-to-perform-action-when-a-dataflow-block-receives-data.md)합니다.  
  
#### <a name="transformblocktinput-toutput"></a>TransformBlock(TInput, TOutput)  
 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 클래스와 유사는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 클래스를 제외 하 고 소스와 대상 역할을 하며.\</TInput, TOutput> 대리자에 전달 하는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 형식의 값을 반환 하는 개체 `TOutput`.</TInput, TOutput> 에 제공 하는 대리자는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체 형식이 될 수 있습니다 `System.Func<TInput, TOutput>` 종류나 `System.Func<TInput, Task>`.\</TInput, TOutput> 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체 `System.Func\<TInput, TOutput>`, 각 입력 요소의 처리는 대리자가 반환 될 때 완료 된 것으로 간주 됩니다.</TInput, TOutput> 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 사용 되는 개체 `System.Func<TInput, Task<TOutput>>`, 각 입력 요소의 처리 경우에만 완료 된 것으로 간주 됩니다 반환 된 <xref:System.Threading.Tasks.Task> 개체가 완료 되.\</TInput, TOutput> 와 마찬가지로 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, 이러한 두 가지 메커니즘을 사용 하 여 사용할 수 있습니다 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 각 입력 요소의 동기 및 비동기 처리를 위해.\</TInput, TOutput>  
  
 다음 기본 예제에서는 한 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 입력 값의 제곱근을 계산 하는 개체입니다.</TInput, TOutput> <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 개체는 <xref:System.Int32> 값을 입력으로 생성 및 <xref:System.Double> 값을 출력으로.\</TInput, TOutput>  
  
 [!code-csharp[TPLDataflow_Overview#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#5)]
 [!code-vb[TPLDataflow_Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#5)]  
  
 사용 하는 전체 예제 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 참조는 Windows Forms 응용 프로그램에서 이미지 처리를 수행 하는 데이터 흐름 블록의 네트워크에서 [연습: Windows Forms 응용 프로그램에서 사용 하 여 데이터 흐름](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).\</TInput, TOutput>  
  
#### <a name="transformmanyblocktinput-toutput"></a>TransformManyBlock(TInput, TOutput)  
 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 클래스와 유사는 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 점을 제외 하 고 클래스 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 아니라 각 입력 값을 하나의 출력 각 입력된 값에 대 한 값에 대해&0; 개 이상의 출력 값을 생성 합니다.</TInput, TOutput> </TInput, TOutput> </TInput, TOutput> 에 제공 하는 대리자는 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체 형식이 될 수 있습니다 `System.Func<TInput, IEnumerable<TOutput>>` 또는 `type System.Func<TInput, Task<IEnumerable<TOutput>>>`.\</TInput, TOutput> 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체 `System.Func<TInput, IEnumerable<TOutput>>`, 각 입력 요소의 처리는 대리자가 반환 될 때 완료 된 것으로 간주 됩니다.</TInput, TOutput> 사용 하는 경우는 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체 `System.Func<TInput, Task<IEnumerable<TOutput>>>`, 각 입력 요소의 처리 경우에만 완료 것으로 간주 됩니다 반환 된 `System.Threading.Tasks.Task<IEnumerable<TOutput>>` 개체가 완료 되.\</TInput, TOutput>  
  
 다음 기본 예제에서는 한 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 문자열을 개별 문자 시퀀스로 분할 하는 개체입니다.</TInput, TOutput> <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체는 <xref:System.String> 값을 입력으로 생성 및 <xref:System.Char> 값을 출력으로.\</TInput, TOutput>  
  
 [!code-csharp[TPLDataflow_Overview#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#6)]
 [!code-vb[TPLDataflow_Overview#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#6)]  
  
 사용 하는 전체 예제를 보려면 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 데이터 흐름 파이프라인의에서 각 입력에 대 한 여러 독립적 출력을 생성, 참조 [연습: 데이터 흐름 파이프라인 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).\</TInput, TOutput>  
  
#### <a name="degree-of-parallelism"></a>병렬 처리 수준  
 모든 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체 버퍼 블록을 처리할 준비가 될 때까지 메시지를 입력 합니다.</TInput, TOutput> </TInput, TOutput> 기본적으로 이러한 클래스 받은 순서대로 한 번에 하나씩 메시지를 처리합니다. 사용할 수 있도록 병렬 처리 수준을 지정할 수도 있습니다 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 여러 메시지를 동시에 처리할 개체.\</TInput, TOutput> \</TInput, TOutput> 동시 실행에 대한 자세한 내용은 이 문서 뒷부분의 병렬 처리 수준 지정 단원을 참조하십시오. 실행 데이터 흐름 블록이 한 번에 둘 이상의 메시지를 처리할 수 있도록 병렬 처리 수준을 설정 하는 예제를 보려면 [하는 방법: 데이터 흐름 블록의 병렬 처리 수준 지정](../../../docs/standard/parallel-programming/how-to-specify-the-degree-of-parallelism-in-a-dataflow-block.md)합니다.  
  
#### <a name="summary-of-delegate-types"></a>대리자 형식 요약  
 다음 표에서 요약에 제공할 수 있는 대리자 형식을 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 개체.\</TInput, TOutput> \</TInput, TOutput> 또한 대리자 형식이 동기적으로 작동하는지, 아니면 비동기적으로 작동하는지를 지정합니다.  
  
|형식|동기 대리자 형식|비동기 대리자 형식|  
|----------|-------------------------------|--------------------------------|  
|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|`System.Action`|`System.Func\<TInput, Task>`|  
|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602></TInput, TOutput>|`System.Func\<TInput, TOutput>`2`|`System.Func<TInput, Task<TOutput>>`|  
|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602></TInput, TOutput>|`System.Func<TInput, IEnumerable<TOutput>>`|`System.Func<TInput, Task<IEnumerable<TOutput>>>`|  
  
 실행 블록 형식으로 작업할 때 람다 식을 사용할 수도 있습니다. 실행 블록과 함께 람다 식을 사용 하는 방법을 보여 주는 예제를 보려면 [하는 방법: 수행 작업 때는 데이터 흐름 블록에서 데이터를 받을](../../../docs/standard/parallel-programming/how-to-perform-action-when-a-dataflow-block-receives-data.md)합니다.  
  
### <a name="grouping-blocks"></a>그룹 블록  
 그룹 블록은 다양한 제약 조건에서 하나 이상의 소스로부터 데이터를 결합합니다. TPL 데이터 흐름 라이브러리는 세가지 조인 블록 형식인 제공: <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>, <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>.\</T1, T2> \</T1, T2>  
  
#### <a name="batchblockt"></a>BatchBlock(T)  
 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스는 이라고 하는 일괄 처리, 출력 데이터의 배열로 입력된 데이터 집합을 결합 합니다. 만들 때 각 배치의 크기를 지정 된 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체입니다. 경우는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체는 지정 된 수의 입력된 요소를 수신 하는 해당 요소가 포함 된 배열을 비동기적으로 전파 합니다. 경우에 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 나머지 입력된 요소가 포함 된 마지막 배열을 전파, 개체가 완료 된 상태로 설정 되었지만 배치를 형성 하는 데 충분 한 요소를 포함 하지 않습니다.  
  
 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스 작동 *greedy* 또는 *식별* 모드입니다. 기본 설정인 greedy 모드는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체가 제공 되는 지정 된 수의 요소를 받은 후 배열을 전파 하는 모든 메시지를 수락 합니다. Non-greedy 모드에서 한 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체가 충분 한 소스가 배치를 형성 하기 메시지 블록에에 제공할 때까지 들어오는 모든 메시지를 연기 합니다. 일반적으로 greedy 모드는 필요한 처리 오버헤드가 적기 때문에 non-greedy 모드보다 효율적으로 수행됩니다. 그러나 원자 방식으로 여러 소스에서 사용을 조정해야 하는 경우 non-greedy 모드를 사용할 수 있습니다. Non-greedy 모드를 설정 하 여 지정 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> 를 `False` 에 `dataflowBlockOptions` 매개 변수는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601.%23ctor%2A> 생성자입니다.  
  
 다음 기본 예제에서는 여러 가지 게시물 <xref:System.Int32> 값을 한 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 일괄 처리에&10; 개의 요소를 포함 하는 개체입니다. 모든 값이 전파 되도록 보장 하는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>,이 예제에서는 호출에서 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드. <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> 메서드는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 완료 된 상태로 개체 즉는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체가 남아 있는 요소를 마지막 배치로 전파 합니다.  
  
 [!code-csharp[TPLDataflow_Overview#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#7)]
 [!code-vb[TPLDataflow_Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#7)]  
  
 사용 하는 전체 예제에 대 한 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 데이터베이스 삽입 작업의 효율성을 향상 시키려면 참조 [연습:를 사용 하 여 BatchBlock 및 BatchedJoinBlock 효율성 향상을](../../../docs/standard/parallel-programming/walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency.md)합니다.  
  
#### <a name="joinblockt1-t2-"></a>JoinBlock(T1, T2, ...)  
 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 및 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 클래스는 입력된 요소를 수집 하 고 전파 <xref:System.Tuple%602?displayProperty=fullName> 또는 <xref:System.Tuple%603?displayProperty=fullName> 이러한 요소를 포함 하는 개체입니다.\</T1, T2, T3> \</T1, T2> \</T1, T2, T3> \</T1, T2> <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 및 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 클래스에서 상속 하지 않는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>.</T1, T2, T3> </T1, T2> 속성을 제공 하는 대신 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602.Target1%2A>, <xref:System.Threading.Tasks.Dataflow.JoinBlock%602.Target2%2A>, 및 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603.Target3%2A>를 구현 하는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>합니다.  
  
 마찬가지로 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>, <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 및 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> greedy 또는 비 greedy 모드에서 작동 합니다.</T1, T2, T3> </T1, T2> 기본 설정인 greedy 모드는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 또는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 는 제공 하 고 각 대상이 적어도 하나의 메시지를 받은 후 튜플을 전파 모든 메시지를 수락 하는 개체입니다.</T1, T2, T3> </T1, T2> Non-greedy 모드에서 한 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 또는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 개체가 모든 대상에 튜플을 만드는 데 필요한 데이터가 제공 될 때까지 모든 들어오는 메시지를 연기 합니다.\</T1, T2, T3> \</T1, T2> 이 시점에서 블록은 소스로부터 모든 필요한 항목을 원자적으로 검색하는&2;단계 커밋 프로토콜에 참여합니다. 이러한 연기를 통해 다른 엔터티가 그 동안 데이터를 사용할 수 있으므로 전반적인 시스템 작업이 진행될 수 있습니다.  
  
 다음 기본 예제에서는 경우는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 개체에는 여러 데이터 값을 계산 하는 데 필요한.</T1, T2, T3> 이 예제에서는 한 <xref:System.Threading.Tasks.Dataflow.JoinBlock%603> 개체 두 개가 필요를 <xref:System.Int32> 값 및 <xref:System.Char> 산술 연산을 수행 하는 값입니다.\</T1, T2, T3>  
  
 [!code-csharp[TPLDataflow_Overview#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#8)]
 [!code-vb[TPLDataflow_Overview#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#8)]  
  
 사용 하는 전체 예제에 대 한 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 를 협조적으로 공유 리소스에 대 한 non-greedy 모드에서 개체 참조 [하는 방법: 여러 소스에서 읽기 데이터를 사용 하 여 JoinBlock](../../../docs/standard/parallel-programming/how-to-use-joinblock-to-read-data-from-multiple-sources.md).\</T1, T2>  
  
#### <a name="batchedjoinblockt1-t2-"></a>BatchedJoinBlock(T1, T2, ...)  
 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%603> 클래스는 입력 요소의 배치를 수집 하 고 전파 `System.Tuple(IList(T1), IList(T2))` 또는 `System.Tuple(IList(T1), IList(T2), IList(T3))` 이러한 요소를 포함 하는 개체입니다.\</T1, T2, T3> \</T1, T2> 생각 하면 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 의 조합으로 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 및 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>.</T1, T2> </T1, T2> 만들 때 각 배치의 크기를 지정 된 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체.\</T1, T2> <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 속성도 제공 합니다 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602.Target1%2A> 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602.Target2%2A>를 구현 하는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>합니다.\</T1, T2> 모든 대상에서 지정 된 수의 입력된 요소를 받을 때의 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체는 비동기적으로 전파는 `System.Tuple(IList(T1), IList(T2))` 해당 요소가 포함 된 개체입니다.\</T1, T2>  
  
 다음 기본 예제에서는 한 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 결과 보유 하는 개체 <xref:System.Int32> 값 및 오류는 <xref:System.Exception> 개체.</T1, T2> 여러 작업을 수행 하 고 결과를 기록 하는이 예제는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602.Target1%2A> 속성을 오류를는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602.Target2%2A> 속성의는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체.\</T1, T2> 성공 및 실패 한 작업의 카운트 알 수 없는 사전에 때문에 <xref:System.Collections.Generic.IList%601> 개체는 각 대상이&0; 개 이상의 값을 받을 수 있도록 합니다.  
  
 [!code-csharp[TPLDataflow_Overview#9](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_overview/cs/program.cs#9)]
 [!code-vb[TPLDataflow_Overview#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_overview/vb/program.vb#9)]  
  
 사용 하는 전체 예제에 대 한 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 결과 프로그램이 데이터베이스에서 읽는 동안 발생 하는 모든 예외를 캡처하려면 참조 [연습:를 사용 하 여 BatchBlock 및 BatchedJoinBlock 효율성 향상을](../../../docs/standard/parallel-programming/walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency.md).\</T1, T2>  
  
 [[go to top](#top)]  
  
<a name="behavior"></a>   
## <a name="configuring-dataflow--block-behavior"></a>데이터 흐름 블록 동작 구성  
 제공 하 여 추가 옵션을 사용할 수 있습니다는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions?displayProperty=fullName> 개체를 데이터 흐름 블록 형식의 생성자에 있습니다. 이러한 옵션은 기본 작업과 병렬 처리 수준을 관리하는 스케줄러와 같은 동작을 제어합니다. <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions> 도 하는 파생 형식도 데이터 흐름 블록 형식과 관련 된 동작을 지정 합니다. 다음 표에서는 각 데이터 흐름 블록 형식과 관련된 옵션 형식을 요약합니다.  
  
|데이터 흐름 블록 형식|<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions> 유형|  
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Threading.Tasks.Dataflow.BufferBlock%601>|<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601>|<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>|<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>\</TInput, TOutput>|<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>\</TInput, TOutput>|<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.BatchBlock%601>|<xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\</T1, T2>|<xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>|  
|<xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602>\</T1, T2>|<xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>|  
  
 다음 섹션에서는 데이터 흐름의 중요 한 데이터에 대 한 추가 정보를 통해 사용할 수 있는 블록 옵션은 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions?displayProperty=fullName>, 및 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions?displayProperty=fullName> 클래스입니다.  
  
### <a name="specifying-the-task-scheduler"></a>작업 Scheduler 지정  
 모든 미리 정의된 데이터 흐름 블록은 TPL 작업 예약 메커니즘을 사용하여 대상에 데이터를 전파하고, 소스에서 데이터를 받고, 데이터를 사용할 수 있게 되면 사용자 정의 대리자를 실행하는 등의 작업을 수행합니다. <xref:System.Threading.Tasks.TaskScheduler> 는 작업을 스레드의 큐에 대기 시키는 작업 스케줄러를 나타내는 추상 클래스입니다. 기본 작업 스케줄러 <xref:System.Threading.Tasks.TaskScheduler.Default%2A>를 사용 하는 <xref:System.Threading.ThreadPool> 큐에 대기 시키고 작업을 실행 하는 클래스입니다. 설정 하 여 기본 작업 스케줄러를 재정의할 수는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 데이터 흐름 블록 개체를 생성할 때 속성입니다.  
  
 동일한 작업 스케줄러가 여러 데이터 흐름 블록을 관리하는 경우 해당 블록 전체에 정책을 적용할 수 있습니다. 예를 들어, 여러 데이터 흐름 블록이 각각 동일한의 단독 스케줄러를 대상으로 하도록 구성 된 경우 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 개체를 모든 작업이 해당이 블록에서 실행 serialize 됩니다. 마찬가지로 이러한 블록이 동일한의 동시 스케줄러를 대상으로 하도록 구성 된 경우 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 개체가 있고이 스케줄러가 최대 동시성 수준을 갖도록 하도록 구성 된, 이러한 블록의 모든 작업은 해당 동시 작업 수로 제한 됩니다. 사용 하는 예는 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 클래스를 사용 하는 읽기 작업은 병렬로 발생 하지만 쓰기 작업은 다른 모든 작업과 독립적으로 발생을 참조 하십시오 [하는 방법: 데이터 흐름 블록의 작업 스케줄러 지정](../../../docs/standard/parallel-programming/how-to-specify-a-task-scheduler-in-a-dataflow-block.md)합니다. TPL의 작업 스케줄러에 대 한 자세한 내용은 참조는 <xref:System.Threading.Tasks.TaskScheduler> 클래스 항목입니다.  
  
### <a name="specifying-the-degree-of-parallelism"></a>병렬 처리 수준 지정  
 기본적으로 TPL 데이터 흐름 라이브러리에서 제공 하는 세 가지 실행 블록 형식인 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>, 한 번에 하나의 메시지를 처리 합니다.\</TInput, TOutput> \</TInput, TOutput> 또한 이러한 데이터 흐름 블록 형식은 수신되는 순서대로 메시지를 처리합니다. 이러한 데이터 흐름 블록이 메시지를 동시에 처리할 수 있도록 설정 된 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=fullName> 데이터 흐름 블록 개체를 생성할 때 속성입니다.  
  
 기본값 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 는 1이 데이터 흐름 블록이 한 번에 하나의 메시지를 처리 하도록 보장 합니다. 이 속성을 1보다 큰 값으로 설정하면 데이터 흐름 블록이 여러 메시지를 동시에 처리할 수 있습니다. 이 속성을 설정 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.Unbounded?displayProperty=fullName> 는 내부 작업 스케줄러가 최대 동시성 수준을 관리할 수 있습니다.  
  
> [!IMPORTANT]
>  최대 병렬 처리 수준을 1보다 크게 지정하는 경우 여러 메시지가 동시에 처리되므로 메시지가 수신된 순서대로 처리되지 않을 수 있습니다. 그러나 메시지가 블록에서 출력되는 순서는 올바르게 정렬됩니다.  
  
 때문에 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성은 최대 병렬 처리 수준을 나타냅니다., 데이터 흐름 블록은 지정한 것 보다 낮은 병렬 처리 수준으로 실행 될 수 있습니다. 데이터 흐름 블록은 기능적 요구 사항을 충족하기 위해서나 사용 가능한 시스템 리소스가 부족하기 때문에 보다 낮은 병렬 처리 수준을 사용할 수도 있습니다. 데이터 흐름 블록은 지정한 것보다 많은 병렬 처리를 선택하지 않습니다.  
  
 값은 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성은 각 데이터 흐름 블록 개체에서 단독으로 합니다. 예를 들어 4개의 데이터 흐름 블록이 각각 최대 병렬 처리 수준으로 1을 지정하는 경우 4개의 데이터 흐름 블록 개체는 모두 잠재적으로 병렬로 실행될 수 있습니다.  
  
 긴 작업이 병렬로 발생할 수 있도록 병렬 처리의 최대 수준을 설정 하는 예제를 보려면 [하는 방법: 데이터 흐름 블록의 병렬 처리 수준 지정](../../../docs/standard/parallel-programming/how-to-specify-the-degree-of-parallelism-in-a-dataflow-block.md)합니다.  
  
### <a name="specifying-the-number-of-messages-per-task"></a>작업당 메시지 수 지정  
 미리 정의된 데이터 흐름 블록 형식은 작업을 사용하여 여러 입력 요소를 처리합니다. 이는 데이터를 처리하는 데 필요한 작업 개체의 수를 최소화하는 데 도움이 되므로 응용 프로그램이 보다 효율적으로 실행될 수 있습니다. 그러나 하나의 데이터 흐름 블록 집합에 있는 작업이 데이터를 처리하고 있는 경우 다른 데이터 흐름 블록의 작업은 메시지를 큐에 대기시켜서 처리 시간 동안 기다려야 할 수 있습니다. 데이터 흐름 작업 간의 공정성을 높이려면을 사용 하도록 설정 하려면 설정의 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.MaxMessagesPerTask%2A> 속성입니다. 때 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.MaxMessagesPerTask%2A> 로 설정 된 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.Unbounded?displayProperty=fullName>, 기본값, 데이터 흐름 블록에서 사용 되는 작업은 사용할 수 있는 만큼의 메시지를 처리 합니다. 때 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.MaxMessagesPerTask%2A> 이외의 값으로 설정 되어 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.Unbounded>, 데이터 흐름 블록이 처리 하도록이 당 메시지이 수 최대 <xref:System.Threading.Tasks.Task> 개체입니다. 설정의 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.MaxMessagesPerTask%2A> 속성 작업 간의 공정성을 높일 수, 필요한 것 보다 더 많은 작업을 만들려면 시스템 성능이 저하 될 수 있는 발생할 수 있습니다.  
  
### <a name="enabling-cancellation"></a>취소 사용  
 TPL은 작업이 협조적 방식으로 취소를 조정할 수 있도록 하는 메커니즘을 제공합니다. 데이터 흐름 블록이이 취소 메커니즘에 참여할 수 있도록 설정 된 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성입니다. 때이 <xref:System.Threading.CancellationToken> 개체가 취소 된 상태로 설정,이 토큰을 모니터링 하는 모든 데이터 흐름 블록의 현재 항목의 실행이 완료 하지만 후속 항목을 처리 하는 것을 시작 하지 않습니다. 또한 이러한 데이터 흐름 블록은 버퍼링된 메시지를 모두 지우고, 모든 소스 및 대상 블록에 대한 연결을 해제하고, 취소된 상태로 전환합니다. 취소 된 상태로 전환 함으로써는 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Completion%2A> 속성에는 <xref:System.Threading.Tasks.Task.Status%2A> 속성으로 설정 <xref:System.Threading.Tasks.TaskStatus>처리 하는 동안 예외가 발생 하지 않는 한 합니다. 이 경우 <xref:System.Threading.Tasks.Task.Status%2A> 로 설정 된 <xref:System.Threading.Tasks.TaskStatus>합니다.  
  
 Windows Forms 응용 프로그램에서 취소를 사용 하는 방법을 보여 주는 예제를 보려면 [하는 방법: 데이터 흐름 블록 취소](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md)합니다. TPL의 취소에 대 한 자세한 내용은 참조 [작업 취소](../../../docs/standard/parallel-programming/task-cancellation.md)합니다.  
  
### <a name="specifying-greedy-versus-non-greedy-behavior"></a>Greedy 및 Non-Greedy 동작 지정  
 몇 가지 그룹 데이터 흐름 블록 형식은 작동할 수 *greedy* 또는 *식별* 모드입니다. 기본적으로 미리 정의된 데이터 흐름 블록 형식은 greedy 모드로 작동합니다.  
  
 조인 블록 형식의 예: <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>, greedy 모드 블록은 해당 데이터를 조인할 아직 사용할 수 없는 경우에 즉시 데이터를 수락 함을 의미 합니다.</T1, T2> non-greedy 모드는 각 대상에서 조인을 완료하기 위해 메시지를 사용할 수 있을 때까지 블록이 들어오는 모든 메시지를 연기함을 의미합니다. 연기된 메시지 중에서 하나라도 더 이상 사용할 수 없는 경우 조인 블록은 연기된 메시지를 모두 해제하고 프로세스를 다시 시작합니다. 에 대 한는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스, greedy 및 non-greedy 동작이 유사 non-greedy 모드에서 점을 제외 하 고는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체가 일괄 처리를 완료 하려면 개별 소스 들에서 사용할 수 있는 충분 한 때까지 들어오는 모든 메시지를 연기 합니다.  
  
 데이터 흐름 블록에 대 한 non-greedy 모드를 지정 하려면 설정 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> 를 `False`합니다. Non-greedy 모드를 사용 하 여 여러 조인 블록이 데이터 소스를 보다 효율적으로 공유할 수 있도록 하는 방법을 보여 주는 예제를 보려면 [하는 방법: JoinBlock을 여러 소스에서 읽기 데이터를 사용 하 여](../../../docs/standard/parallel-programming/how-to-use-joinblock-to-read-data-from-multiple-sources.md)합니다.  
  
 [[go to top](#top)]  
  
<a name="custom"></a>   
## <a name="custom-dataflow-blocks"></a>사용자 지정 데이터 흐름 블록  
 TPL 데이터 흐름 라이브러리가 미리 정의된 블록 형식을 다양하게 제공하지만 사용자 지정 동작을 수행하는 추가 블록 형식을 만들 수 있습니다. 구현에서 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 또는 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 인터페이스를 직접 또는 사용 하 여는 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 메서드를 기존 블록 형식의 동작을 캡슐화 하는 복잡 한 블록을 작성 합니다.\</TInput, TOutput> 사용자 지정 데이터 흐름 블록 기능을 구현 하는 방법을 보여 주는 예제를 보려면 [연습: 사용자 지정 데이터 흐름 블록 형식 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-custom-dataflow-block-type.md)합니다.  
  
 [[go to top](#top)]  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: 데이터 흐름 블록에서 메시지를 읽고 메시지를 작성 합니다.](../../../docs/standard/parallel-programming/how-to-write-messages-to-and-read-messages-from-a-dataflow-block.md)|메시지를 작성 하 고 메시지를 읽는 방법을 보여 줍니다는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 개체입니다.|  
|[방법: 공급자-소비자 데이터 흐름 패턴 구현](../../../docs/standard/parallel-programming/how-to-implement-a-producer-consumer-dataflow-pattern.md)|데이터 흐름 모델을 사용하여 생산자가 메시지를 데이터 흐름 블록에 보내고 소비자가 해당 블록에서 메시지를 읽는 생산자-소비자 패턴을 구현하는 방법을 설명합니다.|  
|[방법: 데이터 흐름 블록에서 데이터를 받을 경우 작업 수행](../../../docs/standard/parallel-programming/how-to-perform-action-when-a-dataflow-block-receives-data.md)|실행 데이터 흐름 블록 형식에 대리자를 제공 하는 방법을 설명 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>.\</TInput, TOutput> \</TInput, TOutput>|  
|[연습: 데이터 흐름 파이프라인 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)|웹에서 텍스트를 다운로드하고 해당 텍스트에 대한 작업을 수행하는 데이터 흐름 파이프라인을 만드는 방법을 설명합니다.|  
|[방법: 데이터 흐름 블록 링크 끊기](../../../docs/standard/parallel-programming/how-to-unlink-dataflow-blocks.md)|사용 하는 방법을 보여 줍니다는 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 메서드를 대상에 메시지를 제공한 후 소스에서 대상 블록 연결을 해제 합니다.|  
|[연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)|Windows Forms 응용 프로그램에서 이미지 처리를 수행하는 데이터 흐름 블록의 네트워크를 만드는 방법을 보여 줍니다.|  
|[방법: 데이터 흐름 블록 취소](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md)|Windows Forms 응용 프로그램에서 취소를 사용하는 방법을 보여 줍니다.|  
|[방법: JoinBlock을 사용 하 여 여러 소스에서 데이터를 읽는](../../../docs/standard/parallel-programming/how-to-use-joinblock-to-read-data-from-multiple-sources.md)|사용 하는 방법에 설명 된 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> non-greedy 모드를 사용 하 여 여러 조인 블록이 데이터 소스를 보다 효율적으로 공유할 수 있도록 하는 방법과 여러 원본에서 데이터를 사용할 수 있는 경우 작업을 수행 하는 클래스입니다.\</T1, T2>|  
|[방법: 데이터 흐름 블록의 병렬 처리 수준 지정](../../../docs/standard/parallel-programming/how-to-specify-the-degree-of-parallelism-in-a-dataflow-block.md)|설정 하는 방법에 설명 된 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성을 사용 하 여 실행 데이터 흐름 블록이 한 번에 둘 이상의 메시지를 처리할 수 있습니다.|  
|[방법: 데이터 흐름 블록의 작업 스케줄러 지정](../../../docs/standard/parallel-programming/how-to-specify-a-task-scheduler-in-a-dataflow-block.md)|응용 프로그램에서 데이터 흐름을 사용하는 경우 특정 작업 스케줄러를 연결하는 방법을 보여 줍니다.|  
|[연습: BatchBlock 및 BatchedJoinBlock를 사용 하 여 효율성을 개선 하기](../../../docs/standard/parallel-programming/walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency.md)|사용 하는 방법에 설명는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 데이터베이스의 효율성을 개선 하기 위해 클래스 삽입 작업 및 사용 하는 방법의 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 결과 프로그램이 데이터베이스에서 읽는 동안 발생 하는 모든 예외를 캡처하는 클래스입니다.\</T1, T2>|  
|[연습: 사용자 지정 데이터 흐름 블록 형식 만들기](../../../docs/standard/parallel-programming/walkthrough-creating-a-custom-dataflow-block-type.md)|사용자 지정 동작을 구현하는 데이터 흐름 블록 형식을 만드는 두 가지 방법을 보여 줍니다.|  
|[작업 병렬 라이브러리 TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 응용 프로그램에서 병렬 및 동시 프로그래밍을 단순화하는 라이브러리인 TPL을 소개합니다.|