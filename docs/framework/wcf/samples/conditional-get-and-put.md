---
title: "조건부 Get과 Put | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 조건부 Get과 Put
이 샘플에서는 WCF REST 프로그래밍 모델을 위한 새 조건부 검색 및 업데이트 API를 사용하는 방법을 보여 줍니다.조건부 검색 및 업데이트는 리소스 지향 및 REST 서비스에 가장 적절하므로 이 샘플에서는 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플을 확장합니다.이 샘플에서는 조건부 검색에 대한 지원을 추가하고 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]에 도입된 새 API를 사용하여 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플로 업데이트하는 방법을 중점적으로 다룹니다.  
  
## 세부 항목  
 조건부 검색 및 업데이트  
  
## 추가 설명  
 이 샘플의 WCF 서비스는 리소스 지향 및 REST 방식으로 고객 컬렉션을 노출합니다.서비스 구현에 대한 자세한 내용은 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플을 참조하십시오.  
  
 이 샘플에서는 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플에 조건부 검색 및 업데이트 기능을 추가합니다.조건부 검색 및 업데이트 기능에서는 HTTP 엔터티 태그와 HTTP If\-None\-Match 및 If\-Match 헤더를 사용하여 클라이언트에 지정된 리소스에 대한 최신 엔터티가 있는지 또는 없는지를 확인합니다.그러나 HTTP If\-None\-Match 및 If\-Match 헤더를 올바르게 구문 분석하기 위한 코드를 구현하는 작업은 번거롭고 오류가 발생하기 쉽습니다.따라서 <xref:System.ServiceModel.Web.WebOperationContext>의 현재 인스턴스를 사용하여 액세스할 수 있는 <xref:System.ServiceModel.Web.IncomingWebRequestContext>에 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 및 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 메서드가 추가되었습니다.또한 올바른 엔터티 태그를 쉽게 반환할 수 있도록 <xref:System.ServiceModel.Web.OutgoingWebRequestContext>에 `SetETag` 메서드가 추가되었습니다.  
  
 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 메서드는 \[WebGet\] 작업과 함께 사용됩니다.이 메서드는 지정된 리소스에 대한 현재 엔터티 태그를 `entityTag` 매개 변수로 사용하며, 이 매개 변수는 `string`, `int`, `long` 또는 `Guid`일 수 있습니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 메서드는 요청의 HTTP If\-None\-Match 헤더와 비교하여 엔터티 태그를 확인합니다.엔터티 태그가 HTTP If\-None\-Match 헤더에 있는 경우 상태 코드 304\(수정 안 됨\)와 함께 <xref:System.ServiceModel.Web.WebFaultException>이 throw되며, 그렇지 않은 경우에는 메서드가 반환됩니다.클라이언트에서는 조건부 검색 메커니즘을 사용하여 이 엔터티가 있음을 서버에 알릴 수 있으며 클라이언트에 이 엔터티가 아직 없는 경우에만 현재 엔터티를 보낼 수 있습니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 메서드의 사용 예는 서비스의 `GetCustomer` 및 `GetCustomers` 작업에서 확인할 수 있습니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>에 대한 호출이 반환되지 않을 수 있다는 점에 주의하십시오.개발자는 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>에 대한 호출이 실행되기 전에 해당 요청이 이미 성공적인 것으로 알려지도록 작업을 구현해야 합니다. 이러한 경우 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>에 대한 호출이 없으면 서비스에서는 성공 상태 코드와 함께 응답을 보냅니다.  
  
 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 메서드는 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 메서드와 비슷합니다.또한 이 메서드는 지정된 리소스에 대한 현재 엔터티 태그를 사용합니다.그러나 이 메서드는 해당 메서드가 "PUT" 또는 "DELETE"로 설정된 \[WebInvoke\] 작업과 함께 사용하기 위한 것입니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 메서드는 요청의 HTTP If\-Match 헤더를 비교하여 엔터티 태그를 확인합니다.엔터티 태그가 HTTP If\-Match 헤더에 없는 경우 상태 코드 412\(사전 조건 실패\)와 함께 <xref:System.ServiceModel.Web.WebFaultException>이 throw됩니다.클라이언트에서는 조건부 업데이트 메커니즘을 사용하여 리소스에 대한 이 엔터티가 있음을 서버에 알릴 수 있으며 클라이언트에 있는 엔터티가 현재 엔터티인 경우에만 리소스를 변경할 수 있습니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 메서드의 사용 예는 서비스의 `UpdateCustomer` 및 `DeleteCustomer` 작업에서 확인할 수 있습니다.<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>와 마찬가지로 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>에 대한 호출이 반환되지 않을 수 있다는 점에 주의하십시오.개발자는 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>에 대한 호출이 실행되기 전에 해당 요청이 이미 성공적인 것으로 알려지도록 작업을 구현해야 합니다. 이러한 경우 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>에 대한 호출이 없으면 서비스에서는 성공 상태 코드와 함께 응답합니다.  
  
 이 샘플은 자체 호스팅 서비스와 콘솔 응용 프로그램 내에서 실행되는 클라이언트로 구성되어 있습니다.콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### 이 샘플을 실행하려면  
  
1.  Conditional Get and Put 샘플의 솔루션을 엽니다.관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다.이렇게 하려면 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **관리자 권한으로 실행**을 선택합니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드한 다음 Ctrl\+F5를 눌러 콘솔 응용 프로그램 프로젝트를 실행합니다.Ctrl\+F5 대신 F5 키를 눌러 디버깅을 사용하는 상태로 이 프로젝트를 실행할 경우, 조건부 GET 및 PUT 확인 시 예외가 throw되면 디버거가 중지됩니다.이 경우 F5 키를 눌러 샘플을 계속 실행합니다.  
  
3.  콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.  
  
4.  샘플이 실행되면 클라이언트에서는 서비스로 요청을 보내고 콘솔 창에 응답을 씁니다.  
  
5.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`