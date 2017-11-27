---
title: "ByteStream 인코더를 사용하여 이진 개체 인코딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acf9d2ace66702c5f0bc522d97ae92869891a38b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>ByteStream 인코더를 사용하여 이진 개체 인코딩
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]을 사용한 원시 이진 데이터의 보내기 및 받기는 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>를 사용하여 구성됩니다.  
  
## <a name="byte-stream-message-encoder-architecture"></a>바이트 스트림 메시지 인코더 아키텍처  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 사용하는 이진 메시지 인코더에는 메시지의 내부 이진 데이터를 처리하거나, 유효성을 검사하거나, 식별하는 기능이 없습니다. 데이터 패키지는 XML로 인코딩된 후 보내기, 받기 및 디코딩됩니다. 인코더는 데이터가 전송에 전달된 후와 메시지가 메시지 큐에 보내지기 전에 데이터를 처리합니다. 이진 인코더는 메시지 데이터를 `<binary>` 요소에 래핑하고 메시지를 받은 후 이 요소를 제거하는 기능을 제공합니다.  
  
## <a name="using-the-byte-stream-message-encoder"></a>바이트 스트림 메시지 인코더 사용  
 다음 예제에서는 바이트 스트림 메시지 인코더를 구현하는 서비스 계약을 보여 줍니다.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 다음 예제에서는 호출되는 서비스를 보여 줍니다.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 라우터와 같은 메시지 인프라를 구현하는 서비스를 사용하는 경우 다음 예제와 같이 메시지가 검사, 유효성 검사 또는 상호 작용 없이 처리됩니다.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>시나리오  
 바이트 스트림 인코더는 다음과 같은 시나리오에서 유용합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 컴퓨터 간에 JPEG 이미지를 전송하는 경우. 이 시나리오에서는 이미지가 외부 소스에서의 전송을 통해 도착하며 전송된 데이터는 이미지를 구성하는 원시 바이트입니다. 서비스는 이진 데이터를 받고 이미지를 표시합니다.  
  
-   메시지 큐에서 정보를 읽고 처리하는 경우. 메시지 큐 관리자에서 메시지를 읽으며 이 메시지는 처리되기 위해 메시지 큐 채널 위로 전달됩니다. 메시지 큐 채널은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 스택에서 큐 관리자 역할을 합니다.  
  
 메시지 큐 채널을 통해 메시지를 보내는 경우 보낸 사람은 큐 관리자에서 받은 바이트를 제어할 수 없습니다. 받는 프로세스에 원시 바이트를 읽는 기능이 없는 경우 메시지가 잘못된 형식으로 수신되고 처리되지 않습니다. 받는 프로세스에는 받은 바이트를 사용 가능한 형식으로 다시 변환하는 기능이 있다고 간주됩니다.
