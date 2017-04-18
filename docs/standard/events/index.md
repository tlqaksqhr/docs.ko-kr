---
title: "이벤트 처리 및 발생 | Microsoft Docs"
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
  - "응용 프로그램 개발[.NET Framework], 이벤트"
  - "이벤트의 대리자 모델"
  - "이벤트[.NET Framework]"
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# 이벤트 처리 및 발생
.NET Framework에서의 이벤트는 대리자 모델에 기반합니다.  대리자 모델은 구독자는 공급자를 등록하고 공급자로부터 알림을 수신할 수 있도록 하는 관찰자 디자인 패턴을 따릅니다.  이벤트 전송자와 이벤트가 발생했음을 알리고, 이벤트 수신자는 해당 알림을 수신하고 그에 대한 응답을 정의합니다.  이 문서에서는 대리자 모델의 주요 구성 요소, 응용 프로그램에서 이벤트를 사용 하는 방법 및 코드에서 이벤트를 구현하는 방법에 대해 설명합니다.  
  
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서 이벤트 처리에 대한 자세한 내용을 보려면 [이벤트 및 라우트된 이벤트 개요 \(Windows 스토어 응용 프로그램\)](http://go.microsoft.com/fwlink/p/?LinkId=261485) 을 참조하십시오.  
  
## 이벤트  
 이벤트는 동작의 발생을 알리기 위해 개체에서 보내는 메시지입니다.  작업은 속성의 값을 변경하는 등 일부 다른 프로그램 논리에 의해 발생할 수도 있고, 단추 클릭 같은 사용자 상호 작용에 의한 것일 수도 있습니다.  이벤트를 발생시키는 개체를 *이벤트 전송자* 라고 합니다.  이벤트 전송자는 어떤 개체 또는 메서드가 발생시키는 이벤트를 수신 \(처리\) 할지 모릅니다.  이벤트는 일반적으로 이벤트 전송자의 멤버입니다. 예를 들어 <xref:System.Web.UI.WebControls.Button.Click> 이벤트는 <xref:System.Web.UI.WebControls.Button> 클래스의 멤버이고, <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현 하는 클래스의 멤버입니다.  
  
 이벤트를 정의하기 위해서는 `event` \(C\#\) 또는 `Event` \(Visual Basic\)키워드를 이벤트 클래스의 시그니처에서 사용하고 이벤트 대리자의 형식을 지정합니다.  대리자는 다음 섹션에 설명되어 있습니다.  
  
 일반적으로 이벤트를 발생 시키려면 `protected` 및 `virtual` \(C\#\) 또는 `Protected` 및 `Overridable` \(Visual Basic\) 라고 표시된 메서드를 추가합니다.  이 `On`*EventName* 메소드의 이름을 짓습니다. 예 : `OnDataReceived` .  메서드는 이벤트 데이터 개체를 지정하는 매개 변수를 취해야 합니다.  이 메서드를 사용하면 파생된 클래스를 이용해 이벤트를 발생시키는 논리를 재정의할 수 있습니다.  파생된 클래스는 등록된 대리자가 이벤트를 수신할 수 있도록 해주는 기본 클래스의 `On`*EventName* 메서드를 항상 호출해야 합니다.  
  
 다음 예제에서는 `ThresholdReached` 이벤트를 선언하는 방법을 보여 줍니다.  이 이벤트는 <xref:System.EventHandler> 대리자와 연결되 있고 `OnThresholdReached` 메서드에서 발생합니다.  
  
 [!code-csharp[EventsOverview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## 대리자  
 대리자는 메서드에 대한 참조를 가지는 형식입니다.  대리자는 이것이 참조하는 메서드에 대한 반환 형식 및 매개 변수를 보여주는 서명을 사용하여 선언되고, 해당 서명과 일치하는 메서드만을 참조할 수 있습니다.  그렇기 때문에 대리자는 형식이 안전한 함수 포인터나 콜백과 같습니다.  대리자 선언으로 대리자 클래스를 충분히 선언할 수 있습니다.  
  
 대리자는.NET Framework에서 여러 용도로 사용됩니다.  이벤트의 컨텍스트에서 대리자는 이벤트 소스와 이벤트를 처리 하는 코드의 중간 \(또는 포인터 같은 메커니즘\) 입니다.  대리자와 이벤트의 연결은 이전 섹션의 예제에서와 같이 이벤트 선언에서 대리자 형식을 포함하는 방식으로 수행됩니다.  대리자에 대한 자세한 내용은 <xref:System.Delegate> 클래스를 참조하십시오.  
  
 .NET Framework에서는 대부분의 이벤트 시나리오를 지원하는 <xref:System.EventHandler> 및 <xref:System.EventHandler%601> 대리자를 제공합니다.  이벤트에 대한 데이터를 포함하지 않는 모든 이벤트에 대해 <xref:System.EventHandler> 대리자를 사용합니다.  이벤트에 대한 데이터를 포함하는 모든 이벤트에 대해 <xref:System.EventHandler%601> 대리자를 사용합니다.  이러한 대리자들은 반환 값으로 형식을 반환하지 않고 두 매개 변수\(이벤트의 원본에 대한 개체 및 이벤트 데이터에 대한 개체\) 를 취합니다..  
  
 대리자는 멀티캐스트로서, 하나 이상의 이벤트 처리 메서드에 대한 참조를 가질 수 있습니다.  자세한 내용은 <xref:System.Delegate> 참조 페이지를 보십시오.  대리자는 이벤트 처리를 제어함에 있어 유연하고 정밀한 처리를 제공합니다.  대리자는 이벤트에 대해 등록된 이벤트 처리기 목록을 유지하여 이벤트를 발생시킨 클래스의 발송자 역할을 합니다.  
  
 <xref:System.EventHandler> 및 <xref:System.EventHandler%601> 대리자가 작동 하지 않는 시나리오의 경우, 대리자를 정의할 수 있습니다.  대리자를 정의해야 하는 시나리오, 예를 들어 제네릭을 인식할 수 없는 코드를 사용하여 작업 해야 하는 경우와 같은 시나리오는 매우 드뭅니다.  대리자는 선언할때 C\#에선 `delegate` 를, Visual Basic에선 `Delegate` 키워드를 사용하여 표시합니다.  다음 예제는 `ThresholdReachedEventHandler` 대리자를 정의하는 방법을 보여 줍니다.  
  
 [!code-csharp[EventsOverview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
 [!code-vb[EventsOverview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## 이벤트 데이터  
 이벤트와 관룐된 데이터는 이벤트 데이터 클래스를 통해 제공될 수 있습니다.  .NET Framework은 응용 프로그램에서 사용할 수 있는 여러 이벤트 데이터 클래스를 제공합니다.  예를 들어, <xref:System.IO.Ports.SerialDataReceivedEventArgs> 클래스는 <xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=fullName> 이벤트에 대한 이벤트 데이터 클래스에 해당합니다.  .NET Framework는 모든 이벤트 데이터 클래스에 대해 명명 패턴이 `EventArgs` 을 끝으로 하는 패턴을 따릅니다.  이벤트에 대한 대리자를 보는것 만으로 어떠한 이벤트 데리터 클래스가 어떤 이벤트에 연결되어 있는지 확인할 수 있습니다.  예를 들어, <xref:System.IO.Ports.SerialDataReceivedEventHandler> 대리자는 매개 변수 중 하나로 <xref:System.IO.Ports.SerialDataReceivedEventArgs> 클래스를 가집니다.  
  
 <xref:System.EventArgs> 클래스는 모든 이벤트 데이터 클래스의 기본 형식입니다.  <xref:System.EventArgs> 는 이벤트에 연결된 모든 데이터가 없을때 사용하는 클래스 이기도 합니다.  다른 클래스에게 어떠한 데이터도 전달하지 않거나 뭔가 발생했다는 것을 알리는 이벤트를 만들고 싶은 경우, 대리자에서 두번째 변수로 <xref:System.EventArgs> 클래스를 사용합니다.  어떠한 데이터도 제공되지 않은 경우 <xref:System.EventArgs.Empty?displayProperty=fullName> 값을 전달할 수 있습니다.  <xref:System.EventHandler> 대리자는 매개변수로 <xref:System.EventArgs> 클래스를 포함합니다.  
  
 사용자 지정된 이벤트 데이터 클래스를 만들려면, <xref:System.EventArgs> 으로부터 파생된 클래스를 만든 후, 이벤트 관련 데이터를 전달하는데 필요한 멤버를 제공합니다.  일반적으로 .NET Framework 같은 명명 패턴을 사용하고 이벤트 데이터 클래스의 이름의 끝을 `EventArgs` 로 해야 합니다.  
  
 다음 예제에서는 `ThresholdReachedEventArgs`.엔터티 클래스에 대해 보여줍니다.  이것은 발생한 이벤트에 관련된 속성도 포함합니다.  
  
 [!code-csharp[EventsOverview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
 [!code-vb[EventsOverview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## 이벤트 처리기  
 이벤트에 응답하려면, 이벤트 수신기에서 이벤트 처리기 메서드를 정의합니다.  이 메서드는 해당 이벤트의 대리자의 시그니처와 일치 해야 합니다.  이벤트 처리기는 사용자가 단추를 클릭한 후 사용자 입력 정보를 수집하는 등의 이벤트가 발생하는 경우 필요한 작업들을 수행합니다.  이벤트가 발생할 때 알림을 받기 위해서는 이벤트에 이벤트 처리기 메서드를 신청해야 합니다.  
  
 다음 예제에서는 <xref:System.EventHandler> 대리인에 대한 서명과 일치하는 `c_ThresholdReached` 이벤트 처리기 메서드에 대해 보여줍니다.  메서드는 `ThresholdReached` 이벤트를 구독합니다.  
  
 [!code-csharp[EventsOverview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
 [!code-vb[EventsOverview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## 정적 및 동적 이벤트 처리기  
 .NET Framework에서는 구독자가 정적이나 동적으로 이벤트 알림을 등록할 수 있습니다.  정적 이벤트 처리기는 해당 이벤트가 처리되는 클래스의 전체 수명 동안 적용됩니다.  동적 이벤트 처리기는 프로그램 실행 도중 일반적으로 특정 조건부 프로그램 논리에 따라 명시적으로 활성화 및 비활성화됩니다.  예를 들어 특정 조건에서만 이벤트 알림이 필요하거나 응용 프로그램에서 여러 이벤트 처리기를 제공하고 런타임 조건에 따라 사용할 이벤트 처리기를 정의하는 경우 동적 이벤트 처리기를 사용할 수 있습니다.  이전 섹션의 예제에서는 이벤트 처리기를 동적으로 추가하는 방법을 보여줍니다.  자세한 내용은 [Events](../Topic/Events%20\(Visual%20Basic\).md) 및 [이벤트](../Topic/Events%20\(C%23%20Programming%20Guide\).md)를 참조하십시오.  
  
## 여러 이벤트 발생시키기  
 클래스에서 여러 이벤트를 발생시키는 경우, 컴파일러가 각 이벤트 대리자 인스턴스에 대해 하나의 필드를 생성합니다.  이벤트 수가 많은 경우에는 각 대리자에 대한 필드의 저장 공간이 부족할 수도 있습니다.  이러한 경우, .NET Framework에서는 사용자가 이벤트 대리자를 저장하기 위해 선택한 다른 데이터 구조체와 함께 사용할 수 있는 이벤트 속성을 제공합니다.  
  
 이벤트 속성은 이벤트 선언과 이벤트 접근자로 구성됩니다.  이벤트 접근자는 사용자가 정의하는 메서드로서, 저장 데이터 구조에서 이벤트 대리자 인스턴스를 추가하거나 제거할 수 있게 해줍니다.  각 이벤트 대리자는 호출되기 전에 검색되어야 하기 때문에 이벤트 속성은 이벤트 필드보다 속도가 느리다는 것을 알아두시기 바랍니다.  이벤트 속성을 사용하면 사용 가능한 메모리는 큰 대신 속도는 그만큼 느립니다.  클래스에서 자주 발생되지 않는 이벤트를 정의하는 경우에는 이벤트 속성을 구현하는 것이 좋습니다.  자세한 내용은 [방법: 이벤트 속성을 사용하여 여러 이벤트 처리](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[방법: 이벤트 발생 및 사용](../../../docs/standard/events/how-to-raise-and-consume-events.md)|이벤트의 발생 및 사용에 대한 예제가 들어 있습니다.|  
|[방법: 이벤트 속성을 사용하여 여러 이벤트 처리](../../../docs/standard/events/how-to-handle-multiple-events-using-event-properties.md)|여러 이벤트를 처리하기 위해 이벤트 속성을 사용하는 방법을 보여줍니다.|  
|[관찰자 디자인 패턴](../../../docs/standard/events/observer-design-pattern.md)|구독자에게 공급자를 등록하고 공급자로부터 알림을 수신할 수 있도록 해주는 디자인 패턴에 대해 보여줍니다.|  
|[방법: Web Forms 응용 프로그램에서 이벤트 사용](../../../docs/standard/events/how-to-consume-events-in-a-web-forms-application.md)|Web Forms 컨트롤에서 발생한 이벤트를 처리하는 방법을 보여 줍니다.|  
  
## 참고 항목  
 <xref:System.EventHandler>   
 <xref:System.EventHandler%601>   
 <xref:System.EventArgs>   
 <xref:System.Delegate>   
 [이벤트 및 라우트된 이벤트 개요 \(Windows 스토어 앱\)](http://go.microsoft.com/fwlink/?LinkId=261485)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)   
 [이벤트](../Topic/Events%20\(C%23%20Programming%20Guide\).md)