---
title: WCF 테스트 클라이언트(WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 78be40268b46c4c85ee034db67d67ee0fbf2158f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809747"
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF 테스트 클라이언트(WcfTestClient.exe)
Windows Communication Foundation (WCF) 테스트 클라이언트 (WcfTestClient.exe)는 사용 하면 테스트 매개 변수 입력, 해당 서비스를 입력 하 고 서비스가 다시 보내는 응답을 볼 수 있는 GUI 도구입니다. 서비스를 매끄럽게 테스트할 WCF 서비스 호스트를 함께 사용 하면 환경을 제공 합니다.  
  
 일반적으로 다음 위치에서 WCF 테스트 클라이언트 (WcfTestClient.exe)를 찾을 수 있습니다: C:\Program Files (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE-커뮤니티 중 하나일 수 있습니다 "Enterprise", "전문" 또는 "커뮤니티"에 따라 Visual Studio 수준의 설치 되어 있습니다.
  
## <a name="scenarios-for-using-test-client"></a>테스트 클라이언트 사용 시나리오  
 다음 섹션에서는 WCF 테스트 클라이언트 개발 프로세스를 효율적으로 사용할 수 있는 가장 일반적인 시나리오에 설명 합니다.  
  
### <a name="inside-visual-studio"></a>Visual Studio의 경우  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>WCF 서비스 호스트가 단일 서비스에서 WCF 테스트 클라이언트 시작  
 새 WCF 서비스 프로젝트를 만들고 f5 키를 눌러 디버거를 시작 프로젝트에 서비스를 호스팅하는 WCF 서비스 호스트가 시작 합니다. 그런 다음 WCF 테스트 클라이언트가 열리고 구성 파일에 정의 된 서비스 끝점의 목록이 표시 됩니다. 그러면 매개 변수를 테스트하고, 서비스를 호출하며, 이 프로세스를 반복하여 테스트를 계속하고 서비스의 유효성을 검사할 수 있습니다.  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>WCF 서비스 호스트가 여러 서비스에서 WCF 테스트 클라이언트 시작  
 또한 여러 서비스를 포함 하는 서비스 프로젝트 디버깅을 돕기 위해 WCF 테스트 클라이언트를 사용할 수 있습니다. WCF 테스트 클라이언트를 열 때 자동으로 프로젝트에 있는 서비스 목록을 반복 하 고 테스트를 위해이 엽니다.  
  
### <a name="outside-visual-studio"></a>Visual Studio 외부  
 인터넷에서 임의의 서비스를 테스트 하려면 Visual Studio 외부 WCF 테스트 클라이언트 (WcfTestClient.exe)를 호출할 수도 있습니다. 도구를 찾으려면 다음 위치로 이동합니다.  
  
 C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\  
  
 도구를 사용하려면 파일 이름을 두 번 클릭하여 이 위치에서 열거나 명령줄에서 시작합니다.  
  
 WCF 테스트 클라이언트 명령줄 인수로 임의 개수의 Uri 사용합니다.  이들은 테스트할 수 있는 서비스의 URI입니다.  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 WCF 테스트 클라이언트 창이 열린 후 클릭 **파일**->**서비스 추가**, 고 열려는 서비스의 끝점 주소를 입력 합니다.  
  
## <a name="wcf-test-client-user-interface"></a>WCF 테스트 클라이언트 사용자 인터페이스  
 단일 서비스 또는 여러 서비스와 함께 WCF 테스트 클라이언트를 사용할 수 있습니다.  
  
### <a name="service-operations"></a>서비스 작업  
 WCF 테스트 클라이언트 주 창의 왼쪽된 창에는 각 끝점 및 작업을 함께 사용할 수 있는 모든 서비스를 나열합니다.  
  
 작업을 두 번 클릭하면 작업 이름이 표시된 새 탭 내의 오른쪽 창에서 해당 내용을 볼 수 있습니다.  
  
 또한 왼쪽 창에는 클라이언트 구성 파일이 나열됩니다. 이 항목 중 하나를 두 번 클릭하면 오른쪽 창의 새 탭 창에 파일 내용이 표시됩니다.  
  
### <a name="entering-test-parameters"></a>테스트 매개 변수 입력  
 테스트 매개 변수를 보려면 작업을 두 번 클릭하여 오른쪽 창에서 엽니다. 매개 변수도 표시 되며 **형식** 기본적으로 뷰는 서비스를 테스트 하려면 매개 변수에 대 한 임의 값을 입력할 수 있습니다.  
  
 메시지의 XML을 보려면 클릭 **XML**합니다. 서비스에 보내도록 하려면 **Invoke**합니다.  
  
 데이터 집합 매개 변수를 클릭 하 고 **...** 단추 옆에 **편집...** DataGrid를 보여 주는 새 창에서 편집할 합니다. 확인 된 **데이터 집합 복사** 및 **데이터 집합 붙여넣기** 단추입니다. 처음 편집할 때 DataSet 개체의 스키마를 알 수 없는 경우 DataGrid는 비어 있습니다. DataSet 개체는 같은 스키마를 사용하여 DataGrid의 현재 개체에 붙여 넣어야 합니다. 붙여넣기 작업 전에 다른 위치에서 스키마를 복사해야 합니다. 클릭 하 여 차후 사용률에 대 한 데이터 집합 개체를 복사할 수도 있습니다는 **데이터 집합 복사** 단추입니다.  
  
 서비스의 응답은 테스트 매개 변수 아래에 표시됩니다.  
  
> [!NOTE]
>  예상 반환 값이 문자열이면 제공된 입력 값이 따옴표 안에 들어 있지 않은 경우에도 결과는 따옴표로 묶인 문자열로 표시됩니다.  
  
 서비스의 계약을 만들 때 특정 작업을 단방향으로 지정한 경우 서비스 응답이 표시되지 않습니다. 메시지가 배달을 위해 대기 중이면 대화 상자가 표시되어 메시지를 보냈음을 알립니다.  
  
### <a name="session-support"></a>세션 지원  
 **새 프록시 시작** 서비스 작업의 탭에 확인란을 사용 하면 세션 지원을 설정/해제 합니다. 이 상자는 기본적으로 선택되어 있지 않습니다.  
  
 특정 작업 (또는 동일한 서비스 끝점에 있는 다른 작업)에 대 한 테스트 매개 변수를 입력 하 고 클릭 **Invoke** 여러 번 확인란을 선택 취소 되어, 이러한 작업을 하나의 프록시 공유 및 서비스 상태는 여러 작업 간에 유지 됩니다.  
  
 경우는 **새 프록시 시작** 확인란, 각각에 대해 새 프록시 시작 **Invoke**이전 세션 시나리오는 종료 하 고 서비스 상태가 다시 설정 됩니다.  
  
### <a name="editing-client-configuration"></a>클라이언트 구성 편집  
 WCF 테스트 클라이언트 주 창의 왼쪽된 창 클라이언트 구성 파일을 나열합니다. 이 항목 중 하나를 두 번 클릭하면 오른쪽 창에 파일 내용이 표시됩니다.  
  
#### <a name="edit-with-service-configuration-editor"></a>서비스 구성 편집기로 편집  
 마우스 오른쪽 단추로 클릭 **Config 파일** 왼쪽된 창 고에서 상황에 맞는 메뉴 **서비스 구성 편집기로 편집**합니다. 서비스 구성 편집기가 시작되어 클라이언트 구성 내용이 표시됩니다. 이 도구 내에서 구성을 편집하고 저장할 수 있습니다.  
  
 서비스 구성 편집기에서 파일을 저장 한 후 WCF 테스트 클라이언트를 해당 파일이 외부에서 수정 되었으며 하며 요청에 다시 로드할 것인지 여부를 알려주는 경고 메시지를 표시 합니다.  
  
 선택 하는 경우 **예**, "Client.dll.config" 탭에서 구성 콘텐츠 편집기에서 변경한 변경 내용을 반영 합니다.  
  
 선택 하는 경우 **아니요**"Client.dll.config" 탭의 구성 내용이 그대로 유지 하 고 수정 된 내용이 자동으로 소스 파일에 저장 됩니다.  
  
#### <a name="restore-to-default-configuration"></a>기본 구성으로 복원  
 모든 변경 내용을 취소 하 고 기본 클라이언트 구성으로 복원 마우스 오른쪽 단추로 클릭 하려는 경우 **Config 파일** 왼쪽된 창 고에서 상황에 맞는 메뉴 **기본 구성으로 복원**합니다. 기본 구성 값이 로드 하 고 "Client.dll.config" 탭의 내용을 복원 됩니다.  
  
#### <a name="validate-changes"></a>변경 내용 확인  
 WCF 테스트 클라이언트에서 로드 되 고 변경 내용이 저장된, WCF 스키마에 대해 유효성에 대 한 구성을 확인 합니다. 오류가 발견되면 오류 정보를 보여 주는 대화 상자가 표시됩니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 하는 동안 (즉, "편집 …", "복원 …" 및 등)를 편집을 지 원하는 메뉴 항목을 사용 하는 사용할 수 없습니다. WCF 테스트 클라이언트를 업데이트 된 구성을 로드 하는 경우 서비스 호출도 비활성화 됩니다.  
  
#### <a name="persist-client-configuration"></a>클라이언트 구성 유지  
 **도구**->**옵션**->**클라이언트 구성** 탭에는 **항상 다시 생성 구성 때 시작 서비스** 기본적으로 사용 되는 옵션입니다. 이 옵션을 WCF 테스트 클라이언트는 서비스를 로드할 때마다 자동으로 다시 생성 된 최신 서비스 계약 및 서비스 App.config 파일에 따라 구성 파일을 지정 합니다.  
  
 WCF 서비스에 대 한 클라이언트 구성을 편집한 경우와 항상을 사용 하려면이 업데이트 된 파일 항목을 선택 취소 사용자가 서비스를 디버깅 하는 **다시 생성** 옵션입니다. 이렇게 하면 WCF 테스트 클라이언트를 닫고 서비스를 업데이트 하는 경우에 Client.dll.config 파일은 업데이트 된 서비스에 따라 하나를 다시 생성 되지 않고 이전에 업데이트 된 합니다.  
  
 그러나 다시 생성된 프록시와 일치하도록 구성 파일을 편집해야 할 수 있습니다. 다시 생성된 프록시와 구성 파일이 업데이트된 서비스로 인해 일치하지 않으면 서비스를 호출할 때 오류가 발생합니다.  
  
> [!CAUTION]
>  클라이언트 구성 파일을 수정한 후 나중에 다시 사용하기 위해 선택하는 경우 파일이 다음 위치에 있습니다.  
>   
>  \Documents and 설정을\\[사용자 계정] \My Documents\Test 클라이언트 프로젝트입니다.  
>   
>  클라이언트 구성 파일에 저장된 업데이트된 자격 증명 정보는 ACL(Access Control 목록)을 통해 보호됩니다.  
  
### <a name="adding-removing-and-refreshing-services"></a>서비스 추가, 제거 및 새로 고침  
  
#### <a name="add-service"></a>서비스 추가  
 클릭 **파일**->**서비스 추가** WCF 테스트 클라이언트에는 서비스를 추가 합니다. 그런 다음 추가할 서비스의 URI(끝점 주소)를 입력해야 합니다. 서비스 주소는 mex 주소나 WSDL 주소일 수 있습니다.  
  
 10 최근에 추가 된 서비스의 끝점 목록의 찾을 수도 있습니다는 **최근 서비스** 하위 메뉴입니다. 그 중 하나를 선택 하는 경우 지정된 된 서비스에서 WCF 테스트 클라이언트에 추가 됩니다.  
  
 서비스 트리의 루트를 마우스 오른쪽 단추로 클릭 **내 서비스 프로젝트**를 선택 하 고 **서비스 추가** 동일한 결과 얻을 수 있습니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 편집을 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
#### <a name="remove-service"></a>서비스 제거  
 제거 되 고 선택 서비스의 서비스 루트를 마우스 오른쪽 단추로 클릭 **서비스 제거** WCF 테스트 클라이언트에서 서비스를 제거 하 합니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 제거를 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
#### <a name="refresh-service"></a>서비스 새로 고침  
 WCF 테스트 클라이언트가 실행 되 고 해당 서비스에 대 한 WCF 테스트 클라이언트 구현이 최신 인지 확인 하려면 서비스에는 변경 내용이 경우 선택한 서비스의 서비스 루트를 마우스 오른쪽 단추로 **서비스 새로 고침**합니다. 서비스를 새로 고친 한 서비스 상태는 다시 설정됩니다.  
  
 프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 새로 고침을 지원하는 메뉴 항목을 사용할 수 없습니다. 서비스 호출도 비활성화됩니다.  
  
## <a name="location-of-files-generated-by-the-test-client"></a>테스트 클라이언트에서 생성한 파일의 위치  
 기본적으로 WCF 테스트 클라이언트에서는 "%appdata%\Local\temp\Test Client Projects" 폴더에서 클라이언트 코드 및 구성 파일을 생성 합니다. WCF 테스트 클라이언트 종료 된 후이 폴더는 삭제 됩니다. WCF 테스트 클라이언트에서 구성 파일을 수정할 경우와 **다시 생성 구성 서비스 시작 시 항상** 옵션을 사용할 수 없습니다, 수정된 된 파일은 "My Documents\Test Client Projects 아래의" Cached Config "폴더에 복사 Documents\Test Client Projects"매핑 (메타 데이터 주소-파일-이름 간) XML 파일이 인덱스로 사용 합니다.  
  
 명령줄을 사용 하 여 WCF 테스트 클라이언트를 시작할 수도 있습니다는 `/ProjectPath` 생성 된 파일을 저장할 새 경로 지정 하려면 전환 하거나 사용 하 여는 `/RestoreProjectPath` 스위치를 기본 위치에 복원 합니다. 구문은 다음과 같습니다.  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 이 명령을 실행 하면 WCF 테스트 클라이언트 열리지 않습니다. 폴더 위치만 변경됩니다. WCF 테스트 클라이언트 실행 되는지에 상관 없이이 명령을 실행할 수 있습니다. 새 위치는 WCF 테스트 클라이언트를 다시 시작할 때 적용 됩니다. 위치 정보는 레지스트리 나 "%appdata%\Local\temp\Test Client Projects" 폴더의 WcfTestClient.exe.option 파일에 저장할 수 있습니다.  
  
## <a name="features-supported-by-wcf-test-client"></a>WCF 테스트 클라이언트에서 지원되는 기능  
 다음은 WCF 테스트 클라이언트에서 지 원하는 기능의 목록입니다.  
  
-   서비스 호출: 요청/응답 및 단방향 메시지.  
  
-   바인딩: Svcutil.exe에서 지원되는 모든 바인딩.  
  
-   세션 제어  
  
-   메시지 계약  
  
-   XML 직렬화  
  
 다음은 WCF 테스트 클라이언트에서 지원 되지 않는 기능 목록입니다.  
  
-   형식: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 형식(관련 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 특성 포함), <xref:System.Xml.Linq.XDocument> 및 <xref:System.Xml.Linq.XElement> 형식, ADO.NET <xref:System.Data.DataTable> 형식  
  
-   이중 계약  
  
-   트랜잭션  
  
-   보안: [!INCLUDE[infocard](../../../includes/infocard-md.md)] , 인증서 및 이름/암호  
  
-   바인딩: WSFederationbinding, 컨텍스트 바인딩 및 Https 바인딩, WebHttpbinding(Json 응답 메시지 지원)  
  
## <a name="closing-wcf-test-client"></a>WCF 테스트 클라이언트 닫기  
 다음과 같은 방법으로 WCF 테스트 클라이언트를 닫을 수 있습니다.  
  
-   에 **파일** 메뉴를 클릭 하 여 **종료**합니다. 또는 WCF 테스트 클라이언트 주 창에서 클릭 하 여 **닫기**합니다. 이러한 작업 중 또한 WCF 서비스 자동 호스트를 종료와 Visual Studio에서 WCF 테스트 클라이언트를 시작한 경우 Visual Studio 디버깅 프로세스를 중지 합니다.  
  
-   마우스 오른쪽 단추로 클릭는 **WCF 서비스 호스트** 클릭 한 다음 확인 하 고 알림 영역에서 아이콘 **종료 합니다.** 이 WCF 서비스 자동 호스트와 WCF 테스트 클라이언트를 종료 하 고 Visual Studio 프로세스 디버깅을 중지 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
