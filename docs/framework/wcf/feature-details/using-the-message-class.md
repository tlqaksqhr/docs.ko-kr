---
title: "Message 클래스 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Message 클래스 사용
<xref:System.ServiceModel.Channels.Message> 기본 클래스입니다 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]합니다. 클라이언트와 서비스 간의 모든 통신에서 결국 <xref:System.ServiceModel.Channels.Message> 인스턴스의 전송과 수신 합니다.  
  
 일반적으로 상호 작용 하지는 <xref:System.ServiceModel.Channels.Message> 클래스를 직접. 대신 데이터 계약, 메시지 계약, 작업 계약 등의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모델 생성자가 사용되어 들어오는 메시지와 보내는 메시지를 설명합니다. 그러나 일부 고급 시나리오를 사용 하 여 프로그래밍할 수는 <xref:System.ServiceModel.Channels.Message> 클래스를 직접. 예를 들어 사용 하려면 수는 <xref:System.ServiceModel.Channels.Message> 클래스:  
  
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체를 serialize하는 대신 보내는 메시지 내용을 만드는 대체 방법이 필요한 경우(예: 디스크의 파일에서 직접 메시지 생성).  
  
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체로 deserialize하는 대신 들어오는 메시지 내용을 사용하는 대체 방법이 필요한 경우(예: 원시 XML 콘텐츠에 XSLT 변환을 적용하려는 경우)  
  
-   메시지 내용에 관계없이 일반적인 방법으로 메시지를 처리해야 하는 경우(예: 라우터, 부하 분산 장치 또는 게시-구독 시스템을 구축할 때 메시지를 라우팅 또는 전달하는 경우)  
  
 사용 하기 전에 <xref:System.ServiceModel.Channels.Message> 클래스를 숙지는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 데이터 전송 아키텍처에 [데이터 전송 아키텍처 개요](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)합니다.  
  
 A <xref:System.ServiceModel.Channels.Message> 데이터에 대 한 범용 컨테이너 이지만 그 밀접 하 게 디자인과 SOAP 프로토콜의 메시지입니다. SOAP와 마찬가지로 메시지에는 메시지 본문과 헤더가 있습니다. 메시지 본문에는 실제 페이로드 데이터가 들어 있고 헤더에는 명명된 추가 데이터 컨테이너가 들어 있습니다. 본문과 헤더를 읽고 쓰는 규칙은 서로 다릅니다. 예를 들어 헤더는 항상 메모리에 버퍼링되고 순서와 횟수에 관계없이 액세스할 수 있지만 본문은 한 번만 읽을 수 있고 스트리밍할 수 있습니다. 일반적으로 SOAP를 사용하는 경우 메시지 본문은 SOAP 본문에 매핑되고 메시지 헤더는 SOAP 헤더에 매핑됩니다.  
  
## <a name="using-the-message-class-in-operations"></a>작업에서 메시지 클래스 사용  
 사용할 수는 <xref:System.ServiceModel.Channels.Message> 작업, 작업 또는 둘 다의 반환 값의 입력된 매개 변수로 클래스입니다. 경우 <xref:System.ServiceModel.Channels.Message> 사용 되는 작업에는 다음 제한 사항이 적용 합니다.  
  
-   작업에 `out` 또는 `ref` 매개 변수를 사용할 수 없습니다.  
  
-   `input` 매개 변수를 둘 이상 사용할 수 없습니다. 매개 변수가 있는 경우 메시지 또는 메시지 계약 형식이어야 합니다.  
  
-   반환 형식은 `void`, `Message` 또는 메시지 계약 형식이어야 합니다.  
  
 다음 코드 예제에는 올바른 작업 계약이 포함되어 있습니다.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>기본 메시지 만들기  
 <xref:System.ServiceModel.Channels.Message> 클래스는 정적 제공 `CreateMessage` 기본 메시지를 만드는 데 사용할 수 있는 팩터리 메서드.  
  
 모든 `CreateMessage` 형식의 버전 매개 변수를 사용 하는 오버 로드 <xref:System.ServiceModel.Channels.MessageVersion> 메시지에 사용할 SOAP 및 Ws-addressing 버전을 나타내는입니다. 들어오는 메시지와 동일한 프로토콜 버전을 사용 하려는 경우 사용할 수 있습니다는 <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> 속성에는 <xref:System.ServiceModel.OperationContext> 에서 가져온 인스턴스는 <xref:System.ServiceModel.OperationContext.Current%2A> 속성입니다. 대부분의 `CreateMessage` 오버로드에는 메시지에 사용할 SOAP 동작을 나타내는 문자열 매개 변수도 있습니다. 버전을 `None`으로 설정하여 SOAP 봉투 생성을 비활성화할 수 있습니다. 메시지가 본문으로만 구성됩니다.  
  
## <a name="creating-messages-from-objects"></a>개체에서 메시지 만들기  
 버전과 동작만 사용하는 가장 기본적인 `CreateMessage` 오버로드는 빈 본문이 있는 메시지를 만듭니다. 다른 오버 로드를 추가로 사용 <xref:System.Object> 매개 변수; 본문이 지정된 된 개체의 serialize 된 표현인 메시지 만듭니다. 사용 된 <xref:System.Runtime.Serialization.DataContractSerializer> serialization에 대 한 기본 설정을 사용 합니다. 다른 serializer를 사용하거나 `DataContractSerializer`를 다르게 구성하려면 `CreateMessage` 매개 변수도 받아들이는 `XmlObjectSerializer` 오버로드를 사용합니다.  
  
 예를 들어 메시지에 개체를 반환하려면 다음 코드를 사용할 수 있습니다.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>XML 판독기에서 메시지 만들기  
 `CreateMessage` 사용 하는 오버 로드는 <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XmlDictionaryReader> 개체 대신 본문입니다. 이 경우 메시지의 본문에는 통과한 XML 판독기 읽기에서 발생한 XML이 포함됩니다. 예를 들어 다음 코드는 XML 파일에서 읽은 본문 내용이 포함된 메시지를 반환합니다.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 또한는 `CreateMessage` 사용 하는 오버 로드는 <xref:System.Xml.XmlReader> 또는 <xref:System.Xml.XmlDictionaryReader> 전체 메시지를 본문 뿐 아니라 나타내는 합니다. 이 오버로드는 정수 `maxSizeOfHeaders` 매개 변수도 사용합니다. 헤더는 메시지를 만드는 즉시 항상 메모리에 버퍼링되며, 이 매개 변수는 발생하는 버퍼링 양을 제한합니다. 서비스 거부 공격의 가능성을 줄이기 위해 XML이 신뢰할 수 없는 소스에서 제공되는 경우 이 매개 변수를 안전한 값으로 설정하는 것이 중요합니다. XML 판독기에서 나타내는 메시지의 SOAP 및 WS-Addressing 버전은 버전 매개 변수를 사용하여 표시된 버전과 일치해야 합니다.  
  
## <a name="creating-messages-with-bodywriter"></a>BodyWriter를 사용하여 메시지 만들기  
 `CreateMessage` 오버로드는 `BodyWriter` 인스턴스를 사용하여 메시지 본문을 설명합니다. `BodyWriter`는 메시지 본문을 만드는 방법을 사용자 지정하기 위해 파생될 수 있는 추상 클래스입니다. 고유한 `BodyWriter` 파생 클래스를 만들어 사용자 지정 방식으로 메시지 본문을 설명할 수 있습니다. 재정의 해야는 `BodyWriter.OnWriteBodyContents` 를 받는 메서드에 <xref:System.Xml.XmlDictionaryWriter>;이 메서드는 본문을 쓰는 작업을 담당 합니다.  
  
 본문 작성기를 버퍼링하거나 버퍼링하지 않을(스트리밍) 수 있습니다. 버퍼링된 본문 작성기는 횟수에 관계없이 콘텐츠를 쓸 수 있지만 스트리밍된 본문 작성기는 한 번만 콘텐츠를 쓸 수 있습니다. `IsBuffered` 속성은 본문 작성기의 버퍼링 여부를 나타냅니다. `BodyWriter` 부울 매개 변수를 사용하는 보호된 `isBuffered` 생성자를 호출하여 본문 작성기에 대해 이 속성을 설정할 수 있습니다. 본문 작성기는 버퍼링되지 않은 본문 작성기에서 버퍼링된 본문 작성기를 만드는 기능을 지원합니다. `OnCreateBufferedCopy` 메서드를 재정의하여 이 프로세스를 사용자 지정할 수도 있습니다. 기본적으로, `OnWriteBodyContents`에서 반환한 XML이 들어 있는 메모리 내 버퍼가 사용됩니다. `OnCreateBufferedCopy`는 `maxBufferSize` 정수 매개 변수를 사용합니다. 이 메서드를 재정의할 경우 이 최대 크기보다 큰 버퍼를 만들면 안됩니다.  
  
 `BodyWriter` 클래스는 기본적으로 각각 `WriteBodyContents` 및 `CreateBufferedCopy` 메서드를 둘러싼 가는 래퍼인 `OnWriteBodyContents` 및 `OnCreateBufferedCopy` 메서드를 제공합니다. 이 메서드는 상태를 확인하여 버퍼링되지 않은 본문 작성기를 두 번 이상 액세스하지 않도록 합니다. 이 메서드는 `Message`에 기초한 사용자 지정 `BodyWriters` 파생 클래스를 만들 때만 직접 호출됩니다.  
  
## <a name="creating-fault-messages"></a>오류 메시지 만들기  
 특정 `CreateMessage` 오버로드를 사용하여 SOAP 오류 메시지를 만들 수 있습니다. 이러한 사용의 가장 기본적인은 <xref:System.ServiceModel.Channels.MessageFault> 오류를 설명 하는 개체입니다. 다른 오버로드는 편의상 제공됩니다. 첫 번째 오버로드는 `FaultCode` 및 원인 문자열을 사용하고 이 정보를 통해 `MessageFault`를 사용하여 `MessageFault.CreateFault`를 만듭니다. 다른 오버로드는 세부 개체를 사용하고 오류 코드 및 원인과 함께 이 개체를 `CreateFault`로 전달합니다. 예를 들어 다음 작업은 오류를 반환합니다.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>메시지 본문 데이터 추출  
 `Message` 클래스는 본문에서 정보를 추출하는 여러 방법을 지원합니다. 이러한 방법을 다음 범주로 분류할 수 있습니다.  
  
-   한 번에 전체 메시지 본문을 XML 작성기에 씁니다. 이 라고 *메시지 쓰기*합니다.  
  
-   메시지 본문에 XML 판독기를 적용합니다. 이렇게 하면 필요할 경우 나중에 부분별로 메시지 본문에 액세스할 수 있습니다. 이 라고 *메시지를 읽는*합니다.  
  
-   전체 메시지를 해당 본문을 포함 하는 메모리 내 버퍼를 복사할 수는 <xref:System.ServiceModel.Channels.MessageBuffer> 유형입니다. 이 라고 *메시지 복사*합니다.  
  
 액세스 방법에 관계없이 `Message` 본문에는 한 번만 액세스할 수 있습니다. 메시지 개체에는 처음에 Created로 설정되는 `State` 속성이 있습니다. 앞의 목록에서 설명한 세 가지 액세스 방법은 상태를 각각 Written, Read 및 Copied로 설정합니다. 또한 `Close` 메서드는 메시지 본문 내용이 더 이상 필요하지 않을 경우 상태를 Closed로 설정할 수 있습니다. 메시지 본문은 만듦 상태에서만 액세스할 수 있으며 상태가 변경된 후에는 만듦 상태로 돌아갈 수 없습니다.  
  
## <a name="writing-messages"></a>메시지 쓰기  
 <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> 메서드 본문 콘텐츠를 작성 한 주어진 `Message` 지정된 된 XML 작성기에는 인스턴스. <xref:System.ServiceModel.Channels.Message.WriteBody%2A> 메서드는 본문 내용을 적절 한 래퍼 요소에 포함 한다는 점을 제외 하면 동일한 작업을 수행 (예를 들어 `soap:body`>). 마지막으로, <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> SOAP 봉투와 헤더 한 래핑을 포함 하 여 전체 메시지를 씁니다. SOAP를 해제하면(Version이 `MessageVersion.None`임) 세 가지 방법이 모두 동일한 작업을 수행하여 메시지 본문 내용을 씁니다.  
  
 예를 들어 다음 코드는 들어오는 메시지의 본문을 파일에 씁니다.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 두 개의 추가 도우미 메서드는 특정 SOAP 시작 요소 태그를 씁니다. 이 메서드는 메시지 본문에 액세스하지 않으므로 메시지 상태를 변경하지 않습니다. 여기에는 다음이 포함됩니다.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> 예를 들어 시작 본문 요소를 씁니다 `<soap:Body>`합니다.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> 예를 들어 시작 봉투 요소를 씁니다 `<soap:Envelope>`합니다.  
  
 해당하는 끝 요소 태그를 쓰려면 해당 XML 작성기에서 `WriteEndElement`를 호출합니다. 이 메서드는 직접 호출되는 경우가 거의 없습니다.  
  
## <a name="reading-messages"></a>메시지 읽기  
 메시지 본문을 읽는 기본 방법은 호출 하는 <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>합니다. 반환 된 <xref:System.Xml.XmlDictionaryReader> 메시지 본문을 읽는 데 사용할 수 있습니다. <xref:System.ServiceModel.Channels.Message> Read 상태로 전환 되는 즉시 <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> 가 호출 되지 사용 하는 경우 반환된 된 XML 판독기 및 합니다.  
  
 <xref:System.ServiceModel.Channels.Message.GetBody%2A> 메서드 또한 형식화 된 개체로 메시지 본문에 액세스할 수 있습니다. 이 메서드는 사용 하는 내부적으로 `GetReaderAtBodyContents`, 하므로 메시지 상태를 전환 하 고는 <xref:System.ServiceModel.Channels.MessageState> 상태 (참조는 <xref:System.ServiceModel.Channels.Message.State%2A> 속성).  
  
 확인할 것이 좋습니다는 <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> 경우 메시지 본문이 비어 속성 및 <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> throw는 <xref:System.InvalidOperationException>합니다. 또한 수신된 된 메시지 (예: 회신) 인 경우 수도 확인 하려는 <xref:System.ServiceModel.Channels.Message.IsFault%2A>, 오류 메시지에 포함 되는지 여부를 나타냅니다.  
  
 가장 기본적인 오버 로드 <xref:System.ServiceModel.Channels.Message.GetBody%2A> 사용 하 여 (제네릭 매개 변수로 표시 됨) 하는 형식의 인스턴스로 메시지 본문을 역직렬화는 <xref:System.Runtime.Serialization.DataContractSerializer> 와 기본 설정으로 구성 된 <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> 할당량이 비활성화 합니다. 다른 serialization 엔진을 사용 하거나 구성 하려는 경우는 `DataContractSerializer` 기본값이 아닌 방식으로 사용 하 여는 <xref:System.ServiceModel.Channels.Message.GetBody%2A> 오버 로드를는 <xref:System.Runtime.Serialization.XmlObjectSerializer>합니다.  
  
 예를 들어 다음 코드는 serialize된 `Person` 개체를 포함하는 메시지 본문에서 데이터를 추출하고 개인의 이름을 인쇄합니다.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>메시지를 버퍼에 복사  
 경우에 따라 메시지 본문을 두 번 이상 액세스해야 할 수 있습니다. 예를 들어 게시자-구독자 시스템의 일부로 동일한 메시지를 여러 대상에 전달할 수 있습니다. 이 경우 본문을 비롯한 전체 메시지를 메모리에 버퍼링해야 합니다. 호출 하 여 이렇게 하려면 <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>합니다. 이 메서드는 최대 버퍼 크기를 나타내는 정수 매개 변수를 사용하며 이 크기보다 크지 않은 버퍼를 만듭니다. 메시지가 신뢰할 수 없는 소스에서 제공되는 경우 이 메서드를 안전한 값으로 설정하는 것이 중요합니다.  
  
 버퍼로 반환 되는 <xref:System.ServiceModel.Channels.MessageBuffer> 인스턴스. 여러 방법으로 버퍼의 데이터에 액세스할 수 있습니다. 기본 방법은 호출 하는 <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> 만들려는 `Message` 버퍼에서 인스턴스.  
  
 버퍼의 데이터에 액세스 하는 다른 방법은 구현 하는 것은 <xref:System.Xml.XPath.IXPathNavigable> 인터페이스를 <xref:System.ServiceModel.Channels.MessageBuffer> 클래스가 구현 하는 기본 XML에 직접 액세스할 수 있습니다. 일부 <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> 오버 로드는 만들 수 있도록 <xref:System.Xml.XPath> 노드 할당량으로 보호 되 기가 방문할 수 있는 XML 노드 수를 제한 합니다. 이 탐색기는 긴 처리 시간을 기반으로 서비스 거부 공격을 방지하는 데 유용합니다. 이 할당량은 기본적으로 사용되지 않습니다. 일부 `CreateNavigator` 오버 로드를 사용 하면 XML의 공백 처리 방법을 지정할 수를 사용 하는 <xref:System.Xml.XmlSpace> 기본값은 열거형 `XmlSpace.None`합니다.  
  
 메시지 버퍼의 내용에 액세스 하는 마지막 방법은 내용을 사용 하 여 스트림을에 쓰는 것 <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>합니다.  
  
 다음 예제에서는 `MessageBuffer` 작업 프로세스를 보여 줍니다. 들어오는 메시지가 여러 수신자에게 전달된 다음 파일에 기록됩니다. 버퍼링 기능이 없으면 메시지 본문에 한 번만 액세스할 수 있으므로 이 작업을 수행할 수 없습니다.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 `MessageBuffer` 클래스에는 주목할 만한 다른 멤버가 있습니다. <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> 버퍼의 내용이 더 이상 필요 없는 경우 무료 리소스에 메서드를 호출할 수 없습니다. <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> 속성 할당된 된 버퍼의 크기를 반환 합니다. <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> 속성은 메시지의 MIME 콘텐츠 형식을 반환 합니다.  
  
## <a name="accessing-the-message-body-for-debugging"></a>디버깅을 위해 메시지 본문에 액세스  
 디버깅 목적을 위해 호출할 수 있습니다는 <xref:System.ServiceModel.Channels.Message.ToString%2A> 메서드를 메시지의 문자열 표현을 가져옵니다. 이 표현은 일반적으로 XML 형식이 사람이 인식하는 데 더 적합하다는 점을 제외하고 텍스트 인코더로 인코딩된 경우 통신 중에 메시지가 표시되는 방식과 일치합니다. 단, 메시지 본문은 예외입니다. 본문은 한 번만 읽을 수 있으며 `ToString`에서 메시지 상태를 변경하지 않습니다. 따라서는 `ToString` 메서드 본문에 액세스 하지 못할 수 고 (예: "..." 자리 표시자를 대체할 수 있습니다 또는 세 개의 점)를 대체할 수 있습니다. 메시지의 본문 내용이 중요한 경우 `ToString`을 사용하여 메시지를 기록하지 마세요.  
  
## <a name="accessing-other-message-parts"></a>다른 메시지 부분에 액세스  
 본문 내용 이외의 메시지 정보에 액세스할 수 있도록 다양한 속성이 제공됩니다. 그러나 메시지가 닫힌 후에는 이러한 속성을 호출할 수 없습니다.  
  
-   <xref:System.ServiceModel.Channels.Message.Headers%2A> 속성은 메시지 헤더를 나타냅니다. 이 항목의 뒷부분에 있는 "헤더 작업" 단원을 참조하세요.  
  
-   <xref:System.ServiceModel.Channels.Message.Properties%2A> 속성은 일반적으로 내보내지 않는 메시지를 보낼 때 하는 메시지에 첨부 된 명명 된 데이터 부분인 메시지 속성을 나타냅니다. 이 항목의 뒷부분에 있는 "속성 작업" 단원을 참조하세요.  
  
-   <xref:System.ServiceModel.Channels.Message.Version%2A> 속성은 메시지와 연결 된 SOAP 및 Ws-addressing 버전을 나타냅니다 또는 `None` SOAP를 사용 하지 않도록 설정 합니다.  
  
-   <xref:System.ServiceModel.Channels.Message.IsFault%2A> 속성에서 반환 `true` 메시지를 SOAP 오류 메시지입니다.  
  
-   <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> 속성에서 반환 `true` 경우 메시지가 비어 있습니다.  
  
 사용할 수는 <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> 본문 래퍼 요소에 특정 특성에 액세스 하는 메서드 (예를 들어 `<soap:Body>`) 특정 이름과 네임 스페이스에 의해 식별 합니다. 이러한 특성이 없으면 `null`이 반환됩니다. 이 메서드는 `Message`가 만듦 상태인 경우(메시지 본문에 아직 액세스하지 않은 경우)에만 호출할 수 있습니다.  
  
## <a name="working-with-headers"></a>헤더 작업  
 A `Message` 라는 명명 된 XML 조각 개수에 제한 없이 포함 될 수 있습니다 *헤더*합니다. 각 조각은 일반적으로 SOAP 헤더에 매핑됩니다. 헤더를 통해 액세스 되는 `Headers` 형식의 속성 <xref:System.ServiceModel.Channels.MessageHeaders>합니다. <xref:System.ServiceModel.Channels.MessageHeaders> 의 컬렉션인 <xref:System.ServiceModel.Channels.MessageHeaderInfo> 개체 및 개별 헤더를 통해 액세스할 수는 <xref:System.Collections.IEnumerable> 인터페이스 인덱서. 예를 들어 다음 코드는 `Message`의 모든 헤더 이름을 나열합니다.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>헤더 추가, 제거, 찾기  
 사용 하 여 모든 기존 헤더의 끝에 새 헤더를 추가할 수는 <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A> 메서드. 사용할 수는 <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> 메서드를 특정 인덱스에 헤더를 삽입 합니다. 기존 헤더는 삽입된 항목에 대해 이동됩니다. 헤더는 인덱스에 따라 순서가 지정되며 사용 가능한 첫 번째 인덱스는 0입니다. 다양 한 사용할 수 있습니다 <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> 헤더를 추가 하는 서로 다른 메서드 오버 로드 `Message` 또는 `MessageHeaders` 인스턴스. 일부 오버로드는 개별 헤더를 복사하고 다른 오버로드는 모든 헤더를 복사합니다. <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> 메서드는 모든 헤더를 제거 합니다. <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> 메서드 (뒤에 모든 헤더를 이동) 하는 특정 인덱스에 있는 헤더를 제거 합니다. <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> 메서드는 특정 이름과 네임 스페이스를 가진 모든 헤더를 제거 합니다.  
  
 사용 하 여 특정 헤더를 검색 하는 <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A> 메서드. 이 메서드는 찾을 헤더의 이름과 네임스페이스를 사용하고 해당 인덱스를 반환합니다. 헤더가 여러 번 발생하는 경우 예외가 throw됩니다. 헤더가 없으면 -1을 반환합니다.  
  
 SOAP 헤더 모델에서는 헤더의 의도된 수신자를 지정하는 `Actor` 값이 헤더에 포함될 수 있습니다. 가장 기본적인 `FindHeader` 오버로드는 메시지의 최종 수신자에 대한 헤더만 검색합니다. 그러나 다른 오버로드를 사용하여 검색에 포함할 `Actor` 값을 지정할 수 있습니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] SOAP 사양  
  
 A [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> 헤더를 복사 하려면 메서드가 제공 됩니다는 <xref:System.ServiceModel.Channels.MessageHeaders> 배열에 컬렉션 <xref:System.ServiceModel.Channels.MessageHeaderInfo> 개체입니다.  
  
 호출할 수는 헤더에 XML 데이터에 액세스 하려면 <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> 하 고 특정 헤더 인덱스에 대 한 XML 판독기를 반환 합니다. 사용 하 여 헤더 내용을 개체로 deserialize 하려는 경우 <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> 또는 다른 오버 로드 중 하나입니다. 사용 하 여 헤더를 deserialize 하는 가장 기본적인 오버 로드는 <xref:System.Runtime.Serialization.DataContractSerializer> 기본값에 구성 된 방법입니다. 다른 serializer나 `DataContractSerializer`의 다른 구성을 사용하려면 `XmlObjectSerializer`를 받아들이는 오버로드 중 하나를 사용합니다. 인덱스 대신 헤더 이름, 네임스페이스 및 선택적으로 `Actor` 값의 목록을 사용하는 오버로드도 있습니다. 이 오버로드는 `FindHeader` 및 `GetHeader`의 조합입니다.  
  
## <a name="working-with-properties"></a>속성 작업  
 `Message` 인스턴스는 임의 형식과 개수의 명명된 개체를 포함할 수 있습니다. `Properties` 형식의 `MessageProperties` 속성을 통해 이 컬렉션에 액세스합니다. 컬렉션 구현 하는 <xref:System.Collections.Generic.IDictionary%602> 로 매핑으로 하며 인터페이스 <xref:System.String> 를 <xref:System.Object>.\</TKey, TValue> 속성 값은 통신 중인 메시지의 모든 부분에 직접 매핑되지 않고 다양 한 채널에 대 한 다양 한 메시지 처리 힌트를 제공 일반적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 스택 또는 [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> 서비스 프레임 워크입니다. 예를 들어 참조 [데이터 전송 아키텍처 개요](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)합니다.  
  
## <a name="inheriting-from-the-message-class"></a>Message 클래스에서 상속  
 `CreateMessage`를 사용하여 만든 기본 제공 메시지 형식이 요구 사항에 맞지 않을 경우 `Message` 클래스에서 파생된 클래스를 만듭니다.  
  
### <a name="defining-the-message-body-contents"></a>메시지 본문 내용 정의  
 메시지 본문 내의 데이터에 액세스하는 세 가지 기본 방법은 쓰기, 읽기 및 버퍼에 복사입니다. 따라서 궁극적으로 이러한 작업은 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A>, 및 <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> 메서드가 호출 됩니다 각각의 파생된 클래스에서 `Message`합니다. 기본 `Message` 클래스는 각 `Message` 인스턴스에 대해 이 메서드 중 하나만 호출되며 여러 번 호출되지 않도록 합니다. 또한 기본 클래스는 닫힌 메시지에 대해 메서드가 호출되지 않도록 합니다. 구현에서 메시지 상태를 추적할 필요는 없습니다.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> 는 추상 메서드를 구현 해야 합니다. 메시지의 본문 내용을 정의하는 가장 기본적인 방법은 이 메서드를 사용하여 쓰는 것입니다. 예를 들어 다음 메시지에는 1에서 20까지 100,000개의 난수가 포함됩니다.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 
          `OnGetReaderAtBodyContents` 및 `OnCreateBufferedCopy` 메서드에는 대부분의 경우에서 작동하는 기본 구현이 있습니다. 기본 구현에서는 `OnWriteBodyContents`를 호출하고 그 결과를 버퍼링한 다음 결과 버퍼로 작업합니다. 그러나 일부 경우에서는 이 기능만으로 충분하지 않을 수 있습니다. 앞의 예제에서 메시지를 읽으면 100,000개의 XML 요소가 버퍼링되며 이는 바람직하지 않을 수 있습니다. `OnGetReaderAtBodyContents`를 재정의하여 난수를 제공하는 사용자 지정 `XmlDictionaryReader` 파생 클래스를 반환할 수 있습니다. 그런 후에 다음 예제와 같이 `OnWriteBodyContents`를 재정의하여 `OnGetReaderAtBodyContents` 속성이 반환하는 판독기를 사용할 수 있습니다.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 마찬가지로 `OnCreateBufferedCopy`를 재정의하여 고유한 `MessageBuffer` 파생 클래스를 반환할 수 있습니다.  
  
 메시지 본문 내용 제공 외에도 메시지 파생 클래스는 `Version`, `Headers` 및 `Properties` 속성을 재정의해야 합니다.  
  
 메시지 복사본을 만드는 경우 복사본은 원본의 메시지 헤더를 사용합니다.  
  
### <a name="other-members-that-can-be-overridden"></a>재정의할 수 있는 기타 멤버  
 재정의할 수는 <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, 및 <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> 은 어떻게 SOAP 봉투, SOAP 헤더 및 SOAP 본문 요소 시작 태그를 지정 하는 메서드는 작성. 일반적으로 이 메서드는 `<soap:Envelope>`, `<soap:Header>` 및 `<soap:Body>`에 해당하며 `Version` 속성에서 `MessageVersion.None`을 반환할 경우 아무 내용도 쓰면 안 됩니다.  
  
> [!NOTE]
>  `OnGetReaderAtBodyContents`의 기본 구현에서는 `OnWriteStartEnvelope`를 호출하고 결과를 버퍼링하기 전에 `OnWriteStartBody` 및 `OnWriteBodyContents`를 호출합니다. 헤더는 쓰지 않습니다.  
  
 재정의 <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> 메서드 하 여 다양 한 부분에서 전체 메시지가 생성 되는 방법을 변경 합니다. `OnWriteMessage` 에서 메서드는 <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> 및 기본 <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> 구현 합니다. 재정의 <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> 좋은 방법은 아닙니다. 적절 한 재정의 하는 것이 좋습니다 `On` 메서드 (예를 들어 <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, 및 <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>합니다.  
  
 재정의 <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> 디버깅 중에 메시지 본문을 나타내는 방법을 재정의 합니다. 기본값은 메시지 본문을 세 개의 점("…")으로 나타냅니다. 메시지 상태가 Closed가 아니면 이 메서드는 여러 번 호출할 수 있습니다. 이 메서드의 구현에서는 한 번만 수행해야 하는 작업(예: 정방향 전용 스트림에서 읽기)을 발생시키면 안 됩니다.  
  
 재정의 <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> SOAP 본문 요소의 특성에 대 한 액세스를 허용 하려면 메서드. 이 메서드는 횟수에 관계없이 호출할 수 있지만 `Message` 기본 형식에서 메시지가 만듦 상태인 경우에만 메서드가 호출되도록 합니다. 구현에서 상태를 확인할 필요는 없습니다. 기본 구현에서는 항상 본문 요소의 특성이 없음을 나타내는 `null`을 반환합니다.  
  
 경우에 `Message` 재정의할 수 없습니다, 개체는 메시지 본문은 더 이상 때 특별 한 정리를 수행 해야 <xref:System.ServiceModel.Channels.Message.OnClose%2A>합니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
 `IsEmpty` 및 `IsFault` 속성을 재정의할 수 있습니다. 기본적으로 두 메서드는 모두 `false`를 반환합니다.