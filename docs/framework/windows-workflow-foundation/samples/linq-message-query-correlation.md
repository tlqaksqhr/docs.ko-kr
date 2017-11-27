---
title: "LINQ 메시지 쿼리 상관 관계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3239d14ce8213b719305b5e32204569a8105997a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="linq-message-query-correlation"></a>LINQ 메시지 쿼리 상관 관계
이 샘플에서는 시스템에서 제공하는 <xref:System.ServiceModel.Dispatcher.MessageQuery> 대신 사용자 지정 <xref:System.ServiceModel.XPathMessageQuery> 구현을 사용하여 내용 기반 상관 관계를 만드는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageQuery>, 내용 기반 상관 관계  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 상관 관계를 만들기 위해 <xref:System.ServiceModel.Dispatcher.MessageQuery> 기본 클래스를 확장하는 방법을 보여 줍니다. 사용자 지정 `LinqMessageQuery`를 구현하면 XLinq를 사용하여 메시지 내에서 XName을 찾을 수 있습니다. 쿼리를 통해 검색한 데이터는 메시지를 적절한 워크플로 인스턴스로 디스패치하기 위한 상관 관계 키를 만드는 데 사용됩니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  이 샘플에서는 HTTP 끝점을 사용하여 워크플로 서비스를 노출합니다. 이 샘플을 적절 한 URL Acl을 실행 하려면 추가 해야 합니다 (참조 [HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353) 세부 정보에 대 한), 관리자 권한으로 Visual Studio를 실행 하거나 적절 한 Acl을 추가 하려면 프롬프트에서 다음 명령을 실행 하 여 합니다. 도메인과 사용자 이름이 대체되었는지 확인합니다.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  URL ACL이 추가되었으면 다음 단계를 사용합니다.  
  
    1.  솔루션을 빌드합니다.  
  
    2.  솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 여러 시작 프로젝트 설정 **시작 프로젝트 설정**합니다. 추가 **서비스** 및 **클라이언트** 순서 대로) (에 여러 시작 프로젝트로 합니다.  
  
    3.  응용 프로그램을 실행합니다. 주문서를 보내고 구매 주문서 ID를 받은 다음 주문을 확인하는 워크플로가 클라이언트 콘솔에 표시됩니다. 처리 중인 요청이 서비스 창에 표시됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
