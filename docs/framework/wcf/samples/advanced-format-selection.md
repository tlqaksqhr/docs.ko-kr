---
title: 고급 포맷 선택
ms.date: 03/30/2017
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
ms.openlocfilehash: 4913d8dbf69f574aa4f329279bed0d92710512f9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="advanced-format-selection"></a>고급 포맷 선택
이 샘플에는 나가는 응답의 새로운 형식을 지원 하기 위해 Windows Communication Foundation (WCF) REST 프로그래밍 모델을 확장 하는 방법을 보여 줍니다. 또한 이 샘플에서는 T4 템플릿을 사용하여 응답을 XHTML 페이지로 반환하고, 뷰 스타일 프로그래밍 모델을 구현하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플은 간단한 서비스와 서비스로 요청을 보내는 클라이언트 코드로 구성되어 있습니다.  이 서비스에서는 메서드 서명 `Message EchoListWithGet(string list);`이 있는 단일 [WebGet] 작업을 지원합니다.  
  
 클라이언트에서는 서비스로 요청을 보낼 때 `list` 쿼리 문자열 매개 변수에서 쉼표로 구분된 항목 목록을 제공하며, 서비스에서는 동일한 목록을 XML, JSON, Atom, XHTML 또는 jpeg 형식 중 하나로 반환합니다.  
  
 서비스에서 반환되는 응답 형식은 먼저 `format` 쿼리 문자열 매개 변수에 의해 결정되고 두 번째로는 요청과 함께 제공된 HTTP Accept 헤더에 의해 결정됩니다. `format` 쿼리 문자열 매개 변수의 값이 앞의 형식 중 하나인 경우 응답은 해당 형식으로 반환됩니다. `format` 쿼리 문자열이 없는 경우 서비스에서는 요청의 Accept 헤더 요소를 반복하고 서비스에서 지원하는 첫 번째 콘텐츠 형식의 형식을 반환합니다.  
  
 작업의 반환 형식에 주목해야 합니다. WCF REST 프로그래밍 모델에서는 기본적으로 작업 이외의 다른 형식을 반환 하는 경우 XML 및 JSON 응답 형식만 지원 <xref:System.ServiceModel.Channels.Message>합니다. 그러나 <xref:System.ServiceModel.Channels.Message>를 반환 형식으로 사용하는 경우 개발자가 메시지 내용의 서식이 지정되는 방식을 완전히 제어할 수 있습니다.  
  
 이 샘플에서는 <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> 및 <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> 메서드를 사용하여 문자열 목록을 각각 XML, JSON 및 ATOM 메시지로 serialize합니다. jpeg 응답 형식의 경우 <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> 메서드가 사용되고 이미지가 스트림에 저장됩니다. XHTML 응답의 경우 <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A>이 전처리된 T4 템플릿과 함께 사용됩니다. 전처리된 T4 템플릿은 .tt 파일과 자동 생성된 .cs 파일로 구성되어 있습니다. 개발자는 .tt 파일을 사용하여 변수 및 제어 구조가 포함된 템플릿 폼에 응답을 쓸 수 있습니다. T4에 대 한 자세한 내용은 참조 [생성 아티팩트 템플릿을 사용 하 여 텍스트](http://go.microsoft.com/fwlink/?LinkId=166023)합니다.  
  
 이 샘플은 자체 호스팅 서비스와 콘솔 응용 프로그램 내에서 실행되는 클라이언트로 구성되어 있습니다. 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-run-this-sample"></a>이 샘플을 실행하려면  
  
1.  Advanced Format Selection 샘플의 솔루션을 엽니다. 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다. 마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘과 선택 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 디버깅하지 않고 콘솔 응용 프로그램 AdvancedFormatSelection 프로젝트를 실행합니다. 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.  
  
3.  샘플이 실행되면 클라이언트에서는 서비스로 요청을 보내고 콘솔 창에 응답을 씁니다. 응답 형식은 XML, JSON, Atom 및 XHTML의 네 가지로 나타납니다.  
  
4.  그런 다음 응답을 .jpeg 형식으로 요청할 수 있는 URI로 이동할지 묻는 메시지가 표시됩니다. 브라우저를 열고 지정된 URI로 이동합니다.  
  
5.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## <a name="see-also"></a>참고 항목
