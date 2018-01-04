---
title: "방법: MetadataResolver를 사용하여 동적으로 바인딩 메타데이터 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 640d053e0186766e5acdbef692f4e7fae59337b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>방법: MetadataResolver를 사용하여 동적으로 바인딩 메타데이터 가져오기
이 항목에서는 <xref:System.ServiceModel.Description.MetadataResolver> 클래스를 사용하여 바인딩 메타데이터를 동적으로 가져오는 방법을 보여 줍니다.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>바인딩 메타데이터를 동적으로 가져오려면  
  
1.  메타데이터 끝점 주소를 사용하여 <xref:System.ServiceModel.EndpointAddress> 개체를 만듭니다.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  서비스 유형 및 메타데이터 끝점 주소를 전달하는 <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>를 호출합니다. 지정된 계약을 구현하는 끝점의 컬렉션이 반환됩니다. 바인딩 정보만 메타데이터에서 가져오고, 계약 정보는 가져오지 않습니다. 제공된 계약이 대신 사용됩니다.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  서비스 끝점의 컬렉션을 반복하여 필요한 바인딩 정보를 추출할 수 있습니다. 다음 코드에서는 끝점을 반복하고, 현재 끝점과 연결된 바인딩 및 주소로 전달되는 서비스 클라이언트 개체를 만든 다음 서비스에 대한 메서드를 호출합니다.  
  
    ```  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터](../../../../docs/framework/wcf/feature-details/metadata.md)
