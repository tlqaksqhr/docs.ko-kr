---
title: "클라이언트 런타임 동작 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시스템 제공 클라이언트 동작 [WCF]"
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 클라이언트 런타임 동작 지정
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 클라이언트는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스와 마찬가지로 클라이언트 응용 프로그램에 맞게 런타임 동작을 수정하도록 구성될 수 있습니다. 세 가지 특성을 사용하여 클라이언트 런타임 동작을 지정할 수 있습니다. 이중 클라이언트 콜백 개체를 사용할 수는 <xref:System.ServiceModel.CallbackBehaviorAttribute> 및 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 특성을 해당 런타임 동작을 수정 합니다. 다른 특성인 <xref:System.ServiceModel.Description.ClientViaBehavior>는 논리 대상과 직접 네트워크 대상 구분 하는 데 사용 될 수 있습니다. 또한 이중 클라이언트 콜백 형식은 서비스측 동작 중 일부를 사용할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][서비스 런타임 동작 지정](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)합니다.  
  
## <a name="using-the-callbackbehaviorattribute"></a>CallbackBehaviorAttribute 사용  
 구성 하거나 사용 하 여 클라이언트 응용 프로그램에서 콜백 계약 구현의 실행 동작을 확장할 수는 <xref:System.ServiceModel.CallbackBehaviorAttribute> 클래스입니다. 이 특성을 콜백 클래스에 대 한 비슷한 기능을 수행 된 <xref:System.ServiceModel.ServiceBehaviorAttribute> 인스턴스 동작과 트랜잭션 설정을 제외 하 고 클래스입니다.  
  
 <xref:System.ServiceModel.CallbackBehaviorAttribute> 클래스의 콜백 계약을 구현 하는 클래스에 적용 되어야 합니다. 비 이중 계약 구현에 적용 하는 경우는 <xref:System.InvalidOperationException> 런타임 시 예외가 throw 됩니다. 다음 코드 예제는 <xref:System.ServiceModel.CallbackBehaviorAttribute> 클래스를 사용 하는 콜백 개체는 <xref:System.Threading.SynchronizationContext> , 마샬링할 스레드를 결정 하는 개체는 <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> 메시지 유효성 검사를 적용 하는 속성 및 <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> 으로 예외를 반환 하는 속성 <xref:System.ServiceModel.FaultException> 디버깅 목적으로 서비스에는 개체입니다.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>CallbackDebugBehavior를 사용하여 관리되는 예외 정보의 흐름 활성화  
 다시 설정 하 여 디버깅 목적으로 서비스에 클라이언트 콜백 개체의 관리 되는 예외 정보의 흐름을 사용 하도록 설정할 수는 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 속성을 `true` 프로그래밍 방식으로 또는 응용 프로그램 구성 파일에서.  
  
 관리되는 예외 정보를 서비스로 이동하면 예외 정보가 내부 클라이언트 구현 정보를 노출하여 권한이 없는 서비스에서 사용할 수 있으므로 보안상 위험할 수 있습니다. 또한 있지만 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 속성은 프로그래밍 방식으로 설정할 수 있습니다, 비활성화를 잊기 쉬울 수 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 배포 하는 경우.  
  
 보안 문제와 관련이 있으므로 다음 작업을 수행하는 것이 좋습니다.  
  
-   응용 프로그램 구성 파일을 사용 하 여 값을 설정 하는 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 속성을 `true`합니다.  
  
-   제어된 디버깅 시나리오에서만 이 작업을 수행합니다.  
  
 다음 코드 예제에서는 클라이언트 콜백 개체의 관리되는 예외 정보를 SOAP 메시지에 반환하도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에 지시하는 클라이언트 구성 파일을 보여 줍니다.  
  
 [!code[SCA.CallbackContract#4](../../../samples/snippets/common/VS_Snippets_CFX/sca.callbackcontract/common/client.exe.config#4)]
 [!code-csharp[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]
 [!code-vb[SCA.CallbackContract#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.callbackcontract/vb/client.exe.config#4)]  
  
## <a name="using-the-clientviabehavior-behavior"></a>ClientViaBehavior 동작 사용  
 사용할 수는 <xref:System.ServiceModel.Description.ClientViaBehavior> 동작 전송 채널은 만들 수는 Uniform Resource Identifier를 지정할 수 있습니다. 직접 네트워크 대상이 메시지의 의도된 프로세서가 아닌 경우 이 동작을 사용합니다. 이 경우 호출 응용 프로그램에서 최종 대상을 알 필요가 없거나 대상 `Via` 헤더가 주소가 아닌 경우에 다중 홉 대화가 가능합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스 런타임 동작 지정](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)