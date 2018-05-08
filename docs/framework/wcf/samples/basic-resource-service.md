---
title: 기본 리소스 서비스
ms.date: 03/30/2017
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
ms.openlocfilehash: 3ec743bbbb6d18d972701c3149179d6f615d1884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="basic-resource-service"></a>기본 리소스 서비스
이 샘플에는 검색을 지 원하는 고객 컬렉션을 노출 하는 Windows Communication Foundation (WCF) REST 프로그래밍 모델을 사용 하 여 HTTP 기반 서비스 구현, 추가, 삭제 및 바꾸기 작업 하는 방법을 보여 줍니다. 이 샘플은 자체 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP 서비스(Service.cs)와 서비스를 만들고 호출하는 콘솔 응용 프로그램(program.cs)의 두 구성 요소로 구성되어 있습니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 리소스 지향/REST 방식으로 고객 컬렉션을 노출합니다. 즉, 고객 컬렉션과 이 컬렉션 내의 모든 고객마다 고유한 URI가 있어야 합니다. 이 서비스는 컬렉션 URI에서 HTTP `GET`을 보내 전체 컬렉션을 검색하고 컬렉션 URI에서 HTTP `POST`를 보내 컬렉션에 새 고객을 추가하는 작업을 지원합니다. 또한 개별 고객의 URI에서는 고객 세부 정보를 가져오기 위한 HTTP `GET`, 고객 세부 정보를 대체하기 위한 HTTP `PUT` 및 컬렉션에서 고객을 제거하기 위한 HTTP `DELETE`를 지원합니다. 컬렉션에 새 고객이 추가되면 서비스에서는 고객에게 고유한 URI를 할당하고 이 URI를 고객 세부 정보의 일부로 저장합니다. 또한 서비스에서는 응답의 HTTP Location 헤더를 사용하여 이 URI를 클라이언트에 전달합니다.  
  
 App.config 파일에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 속성이 <xref:System.ServiceModel.Description.WebHttpEndpoint>로 설정된 기본 <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>로 `true` 서비스를 구성합니다. 따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `http://localhost:8000/Customers/help`에 자동 HTML 기반 도움말 페이지를 만듭니다. 이 페이지에서는 서비스에 대한 HTTP 요청을 생성하고 서비스의 HTTP 응답에 액세스하는 방법에 대한 정보가 제공됩니다. 예를 들어 고객 세부 정보를 XML 또는 JSON으로 표현하는 방법에 대한 예제가 제공됩니다.  
  
 이러한 방식으로 고객 컬렉션(보다 일반적으로는 모든 리소스)을 노출하면 클라이언트가 URI와 HTTP `GET`, `PUT`, `DELETE` 및 `POST`를 사용하여 일관된 방식으로 고객 컬렉션과 상호 작용할 수 있습니다. Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다. 이 방법은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다. <xref:System.ServiceModel.ChannelFactory> 및 <xref:System.Net.WebClient> 같은 다른 .NET Framework 클래스를 사용하여 서비스에 액세스할 수도 있습니다. SDK의 다른 샘플 (같은 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [선택 영역 자동 서식](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플)와 통신 하려면 이러한 클래스를 사용 하는 방법을 보여는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  
  
 이 샘플은 콘솔 응용 프로그램 내에서 실행되는 자체 호스팅 서비스와 클라이언트로 구성되어 있습니다. 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  Basic Resource Service 샘플의 솔루션을 엽니다. 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다. 마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 콘솔 응용 프로그램을 실행합니다. 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다. 언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다. 샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
3.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## <a name="see-also"></a>참고 항목  
 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md)  
 [자동 포맷 선택](../../../../docs/framework/wcf/samples/automatic-format-selection.md)
