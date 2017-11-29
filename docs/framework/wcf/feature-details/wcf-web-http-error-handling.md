---
title: "WCF 웹 HTTP 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3366ab851c6e6b66a5df94bdb24baad4ae0c8d14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-web-http-error-handling"></a>WCF 웹 HTTP 오류 처리
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 웹 HTTP 오류 처리를 사용하면 HTTP 상태 코드를 지정하고 작업과 동일한 형식(예: XML 또는 JSON)을 사용하여 오류 정보를 반환하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 HTTP 서비스에서 오류를 반환할 수 있습니다.  
  
## <a name="wcf-web-http-error-handling"></a>WCF 웹 HTTP 오류 처리  
 <xref:System.ServiceModel.Web.WebFaultException> 클래스는 HTTP 상태 코드를 지정할 수 있도록 하는 생성자를 정의합니다. 이 상태 코드는 나중에 클라이언트에 반환됩니다. <xref:System.ServiceModel.Web.WebFaultException> 클래스의 제네릭 버전인 <xref:System.ServiceModel.Web.WebFaultException%601>을 사용하면 발생한 오류에 대한 정보가 들어 있는 사용자 정의 형식을 반환할 수 있습니다. 이 사용자 지정 개체는 작업에 지정된 형식을 사용하여 serialize되고 클라이언트에 반환됩니다. 다음 예제에서는 HTTP 상태 코드를 반환하는 방법을 보여 줍니다.  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 다음 예제에서는 HTTP 상태 코드와 추가 정보를 사용자 정의 형식에 반환하는 방법에 대해 설명합니다. `MyErrorDetail`은 발생한 오류에 대한 추가 정보를 포함하는 사용자 정의 형식입니다.  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 위의 코드에서는 사용할 수 없음 상태 코드 및 `MyErrorDetails` 개체의 인스턴스가 포함된 본문과 함께 HTTP 응답을 반환합니다. `MyErrorDetails` 개체의 형식은 다음에 의해 결정됩니다.  
  
-   서비스 작업에 지정된 `ResponseFormat` 또는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성의 <xref:System.ServiceModel.Web.WebInvokeAttribute> 매개 변수 값  
  
-   <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>의 값  
  
-   <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>에 액세스하는 <xref:System.ServiceModel.Web.OutgoingWebResponseContext> 속성의 값  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]이러한 값을에 따른 작업의 형식 참조 [WCF 웹 HTTP 형식 지정](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.  
  
 <xref:System.ServiceModel.Web.WebFaultException>은 <xref:System.ServiceModel.FaultException>이므로 SOAP 끝점과 웹 HTTP 끝점을 둘 다 노출하는 서비스의 오류 예외 프로그래밍 모델로 사용될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [WCF 웹 HTTP 형식 지정](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 [오류 정의 및 지정](../../../../docs/framework/wcf/defining-and-specifying-faults.md)  
 [예외 및 오류 처리](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [오류 보내기 및 받기](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
