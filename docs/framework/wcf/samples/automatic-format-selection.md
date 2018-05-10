---
title: 자동 포맷 선택
ms.date: 03/30/2017
ms.assetid: dab51e56-8517-4a6a-bb54-b55b15ab37bb
ms.openlocfilehash: 8c26253bee069bf9bbc009ea219e6c12cab034ef
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="automatic-format-selection"></a>자동 포맷 선택
이 샘플의 작업 코드에서 형식을 명시적으로 설정 하는 방법 뿐만 아니라 모델을 프로그래밍 Windows Communication Foundation (WCF) 나머지 선택 영역 자동 서식 지정 (XML 또는 JSON)을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플은 서비스와 서비스로 요청을 보내는 클라이언트 코드로 구성되어 있습니다. 서비스에서는 단일 HTTP `GET` 작업(`EchoWithGet`) 및 단일 HTTP `POST` 작업(`EchoWithPost`)을 지원합니다. 두 작업은 모두 문자열을 필요로 하며 응답에서도 문자열을 반환합니다. `GET` 작업을 사용할 경우 문자열은 URI 쿼리 문자열 매개 변수에서 제공됩니다. `POST` 작업을 사용할 경우 문자열은 요청의 본문에서 XML로 serialize되어 제공됩니다. 서비스에서는 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]의 새로운 기능인 선택 영역 자동 서식 지정 및 선택 영역 명령적 서식 지정 기능을 사용하여 응답을 XML이나 JSON으로 반환할 수 있습니다.  
  
 이 샘플에서는 App.config 파일을 사용하여 선택 영역 자동 서식 지정 기능을 사용하도록 설정합니다. 기본 웹 HTTP 끝점에서 `automaticFormatSelectionEnabled` 특성에는 `true` 값이 지정됩니다. 활성화 선택 영역 자동 서식, WCF 인프라에서 가장 적합 한 응답 형식 (XML 또는 JSON) 요청의 HTTP Accept 또는 Content-type 헤더를 지정 된를 선택 합니다. 개발자는 `automaticFormatSelectionEnabled` 특성을 `true`로 설정하여 이 새 기능을 사용할 수 있으며 그 외에는 추가 코드나 구성을 제공할 필요가 없습니다. Program.cs에서 클라이언트 코드에서 요청을 보냅니다 모두에 `GET` 및 `POST` 있는 응답을 반환 하는 중 "응용 프로그램/xml" 또는 "application/json"로 지정 된 HTTP Accept 헤더가 포함 된 서비스 및 서비스의 작업 해당 형식입니다.  
  
 또한 `GET` 작업에서는 선택 영역 명령적 서식 지정 기능이 사용됩니다. `GET` 작업에서는 선택적 `format` 쿼리 문자열 매개 변수를 검사하고, 이 매개 변수가 있으면 <xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A> 속성에서 응답 형식을 설정합니다. 명령적으로 이러한 방식으로 응답 형식을 설정 WCF 인프라에서 수행한 자동 서식 선택 영역을 재정의 합니다.  
  
 이 샘플은 자체 호스팅 서비스와 콘솔 응용 프로그램 내에서 실행되는 클라이언트로 구성되어 있습니다. 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  Automatic Format Selection 샘플의 솔루션을 엽니다. 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다. 마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘과 선택 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 콘솔 응용 프로그램 AutomaticFormatSelection 프로젝트를 실행합니다. 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.  
  
3.  샘플이 실행되면 클라이언트에서는 서비스로 요청을 보내고 콘솔 창에 응답을 씁니다. 응답 형식은 XML과 JSON의 두 가지로 나타납니다.  
  
4.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AutomaticFormatSelection`  
  
## <a name="see-also"></a>참고 항목
