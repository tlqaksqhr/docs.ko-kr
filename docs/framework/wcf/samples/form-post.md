---
title: 폼 게시
ms.date: 03/30/2017
ms.assetid: fa6f84f9-2e07-4e3c-92d0-a245308b7dff
ms.openlocfilehash: 005aba6ab8a8fcbe4f4e4f79055e04cff059f47d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="form-post"></a>폼 게시
이 샘플에서는 WCF REST 프로그래밍 모델을 확장하여 들어오는 요청의 새로운 형식을 지원하는 방법을 보여 줍니다. 이 샘플에는 HTML 폼 게시의 요청을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 deserialize할 수 있는 포맷터의 구현도 포함되어 있습니다. 또한 이 샘플에서는 T4 템플릿을 사용하여 사용자가 다시 WCF REST 서비스에 게시할 수 있는 HTML 폼을 제공하는 HTML 페이지를 반환합니다.  
  
## <a name="demonstrates"></a>세부 항목  
  
-   들어오는 요청 형식에 대한 지원 확장  
  
-   T4 템플릿 통합  
  
## <a name="discussion"></a>토론  
 이 샘플은 두 프로젝트로 구성되어 있습니다. 한 프로젝트는 HTML 폼 게시를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 deserialize할 수 있는 사용자 지정 요청 포맷터가 포함된 HtmlFormProcessing 라이브러리입니다. 다른 프로젝트는 Basic Resource Service 샘플을 확장하여 HtmlFormProcessing 라이브러리의 사용자 지정 요청 포맷터를 사용하는 콘솔 응용 프로그램입니다.  
  
 HTML 폼 게시(HtmlFormRequestDispatchFormatter)를 deserialize할 수 있는 사용자 지정 포맷터는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]를 사용하여 문자열에서 변환할 수 있는 <xref:System.ServiceModel.Dispatcher.QueryStringConverter> 형식과 QueryStringConverter를 사용하여 문자열에서 변환할 수 있는 멤버만 있으며 <xref:System.Runtime.Serialization.DataContractAttribute>로 표시된 형식을 모두 받아들입니다.  
  
 HtmlFormProcessing 라이브러리 프로젝트에는 다른 사용자 지정 요청 포맷터를 만드는 데 사용할 수 있는 추상 기본 클래스인 `RequestBodyDispatchFormatter`도 포함되어 있습니다. `RequestBodyDispatchFormatter`에서 파생 클래스를 만들면 개발자는 기본 클래스에서 URI 템플릿 매개 변수를 작업의 메서드 매개 변수에 매핑할 수 있게 해 주는 요청 본문 deserialization 논리에 집중할 수 있습니다. 또한 HtmlFormProcessing 라이브러리 프로젝트에는 `HtmlFormProcessingBehavior`에서 파생 클래스를 만들어 기본 요청 포맷터를 사용자 지정 요청 포맷터로 대체하는 방법을 보여 주는 <xref:System.ServiceModel.Description.WebHttpBehavior> 클래스도 포함되어 있습니다.  
  
 이 콘솔 응용 프로그램 프로젝트에서 확장 된 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플. Basic Resource Service 샘플에서는 WCF REST 프로그래밍 모델을 사용하는 방식으로 리소스를 노출하는 방법을 보여 줍니다. Basic Resource Service 샘플에서는 고객 컬렉션 리소스가 노출되므로 컬렉션의 고객을 만들고, 검색하고, 업데이트하고, 삭제할 수 있습니다. Basic Resource Service 샘플에서는 기본적으로 지원되는 들어오는 요청 형식인 XML과 JSON만 사용합니다.  
  
 이 Form Post 샘플의 콘솔 응용 프로그램에서는 HtmlFormProcessing 라이브러리의 사용자 지정 포맷터를 사용합니다. 이 사용자 지정 포맷터를 사용하면 사용자가 브라우저를 사용하여 HTML 폼 게시에서 요청을 보내는 방법으로 고객을 만들 수 있습니다. 이 콘솔 응용 프로그램에서는 서비스에 다시 게시할 폼이 포함된 HTML 페이지를 반환하는 작업도 추가합니다. 이 HTML 페이지는 .tt 파일과 자동 생성된 .cs 파일로 구성된 전처리된 T4 템플릿을 사용하여 생성됩니다. 개발자는 .tt 파일을 사용하여 변수 및 제어 구조가 포함된 템플릿 폼에 응답을 쓸 수 있습니다. T4에 대 한 자세한 내용은 참조 [생성 아티팩트 템플릿을 사용 하 여 텍스트](http://go.microsoft.com/fwlink/?LinkId=178139)합니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  Form Post 샘플의 솔루션을 엽니다. 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다. 마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘 및 상황에 맞는 메뉴에서 "관리자 권한으로 실행"을 선택 합니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 콘솔 응용 프로그램 FormPost 프로젝트를 실행합니다.  
  
3.  콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.  
  
4.  샘플이 실행되면 클라이언트에서는 고객을 추가, 업데이트, 삭제 중인지 서비스에서 현재 고객 목록을 가져오는 중인지 등의 현재 활동 상태를 콘솔 창에 씁니다.  
  
5.  그런 다음 고객 폼의 URI로 이동할지 묻는 메시지가 표시됩니다. 브라우저를 열고 지정된 URI로 이동합니다. 이름 및 고객과 클릭에 대 한 주소에 입력 된 **전송** 단추 합니다.  
  
6.  콘솔 창에서 아무 키나 눌러 샘플을 계속 실행합니다.  
  
7.  샘플이 완료되면 브라우저를 사용하여 만든 고객이 최종 고객 목록에 포함됩니다.  
  
8.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Web\FormPost`
