---
title: '방법: 채널 팩터리를 사용하여 비동기로 작업 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: 95279f90fbf87d64d96a1ed036449b72416e4f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490391"
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>방법: 채널 팩터리를 사용하여 비동기로 작업 호출
이 항목에서는 <xref:System.ServiceModel.ChannelFactory%601> 기반 클라이언트 응용 프로그램을 사용하여 클라이언트에서 서비스 작업에 비동기적으로 액세스하는 방법에 대해 설명합니다. 서비스를 호출하기 위해 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> 개체를 사용하는 경우 이벤트 구동 비동기 호출 모델을 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 비동기적 서비스 작업 호출](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)합니다. 이벤트 기반 비동기 호출 모델에 대 한 자세한 내용은 참조 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).)  
  
 이 항목에서 설명하는 서비스에서는 `ICalculator` 인터페이스를 구현합니다. 클라이언트는 이 인터페이스의 작업을 비동기적으로 호출할 수 있는데, 이는 `Add` 등의 작업이 호출을 시작하는 `BeginAdd`와 작업 완료 시 결과를 검색하는 `EndAdd`라는 두 개의 메서드로 나뉨을 의미합니다. 서비스에서 작업을 비동기적으로 구현 하는 방법을 보여 주는 예제를 참조 하십시오. [하는 방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)합니다. 동기 및 비동기 작업에 대 한 세부 정보를 참조 하십시오. [동기 및 비동기 작업](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)합니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>WCF 서비스 작업을 비동기적으로 호출하려면  
  
1.  실행의 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구에 `/async` 다음 명령에 표시 된 것 처럼 옵션입니다.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     그러면 작업에 서비스 계약의 비동기 클라이언트 버전이 생성됩니다.  
  
2.  다음 샘플 코드와 같이 비동기 작업이 완료될 때 호출할 콜백 함수를 만듭니다.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  서비스 작업에 비동기적으로 액세스하려면 다음 샘플 코드에서와 같이, 클라이언트를 만들고 `Begin[Operation]`(예: `BeginAdd`)을 호출하며 콜백 함수를 지정합니다.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     콜백 함수가 실행될 때 클라이언트는 결과를 검색하기 위해 `End<operation>`(예: `EndAdd`)을 호출합니다.  
  
## <a name="example"></a>예제  
 이전 절차에 사용된 클라이언트 코드와 함께 사용되는 서비스는 다음 코드에서와 같이 `ICalculator` 인터페이스를 구현합니다. 서비스 쪽에서의 `Add` 및 `Subtract` 계약의 작업은 동기적으로 호출 하 여는 Foundation WCF (Windows Communication) 실행 시간을 이전 클라이언트 단계는 클라이언트에 비동기적으로 호출 하더라도 합니다. 클라이언트가 `Multiply` 및 `Divide` 작업을 비동기적으로 호출하더라도 서비스 쪽에서는 이 작업을 사용하여 비동기적으로 서비스를 호출합니다. 다음 예제에서는 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> 속성을 `true`로 설정합니다. 이 속성 설정을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 비동기 패턴 구현과 함께 사용하면 런타임에서 작업이 비동기적으로 호출됩니다.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [서비스 계약: 비동기 샘플](http://msdn.microsoft.com/library/833db946-f511-4f64-a26f-2759a11217c7)
