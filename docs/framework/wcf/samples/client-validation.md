---
title: Client Validation
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 6e34ca8e1bb14f610e363c02eaeb94b7fa5e27c7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808288"
---
# <a name="client-validation"></a>Client Validation
서비스는 메타데이터를 자주 게시하여 클라이언트 프록시 형식의 자동 생성 및 구성을 활성화합니다. 서비스를 신뢰할 수 없으면 클라이언트 응용 프로그램에서 메타데이터가 보안, 트랜잭션, 서비스 계약 형식 등에 대한 클라이언트 응용 프로그램의 정책을 준수하는지 확인해야 합니다. 다음 샘플에서는 서비스 끝점을 안전하게 사용할 수 있도록 서비스 끝점의 유효성을 검사하는 클라이언트 끝점 동작 기록 방법을 보여 줍니다.  
  
 서비스는 네 개의 서비스 끝점을 노출합니다. 첫 번째 끝점은 WSDualHttpBinding을, 두 번째 끝점은 NTLM 인증을, 세 번째 끝점은 트랜잭션 흐름을, 네 번째 끝점은 인증서 기반 인증을 사용합니다.  
  
 클라이언트는 <xref:System.ServiceModel.Description.MetadataResolver> 클래스를 사용하여 서비스에 대한 메타데이터를 검색합니다. 클라이언트에서는 이중 바인딩 방지, NTLM 인증 및 유효성 검사 동작을 사용하는 트랜잭션 흐름에 대한 정책을 적용합니다. 각 <xref:System.ServiceModel.Description.ServiceEndpoint> 의 인스턴스를 추가 하는 서비스의 메타 데이터를 클라이언트 응용 프로그램에서 가져온 인스턴스는 `InternetClientValidatorBehavior` 끝점 동작을는 <xref:System.ServiceModel.Description.ServiceEndpoint> 에 연결할 Windows Communication Foundation (WCF) 클라이언트를 사용 하기 전에 끝점입니다. 동작의 `Validate` 메서드는 서비스의 작업이 호출되기 전에 실행되고 `InvalidOperationExceptions`를 throw하여 클라이언트의 정책을 적용합니다.  
  
### <a name="to-build-the-sample"></a>이 샘플을 빌드하려면  
  
1.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  관리자 권한으로 Visual Studio 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
2.  \service\bin\Debug에서 서비스 응용 프로그램을 실행합니다.  
  
3.  \client\bin\Debug에서 클라이언트 응용 프로그램을 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
4.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
5.  샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다. 다른 보안 샘플에도 동일한 인증서가 사용됩니다.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서버에서 관리자 권한으로 실행 되는 Visual Studio 명령 프롬프트에 입력 `setup.bat service`합니다. 실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.  
  
2.  서버에서 새 인증서 이름을 반영하도록 App.config를 편집합니다. 즉, 변경 된 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 요소는 컴퓨터의 정규화 된 도메인 이름입니다.  
  
3.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
4.  클라이언트에서 관리자 권한 및 형식으로 Visual Studio 명령 프롬프트를 열고 `setup.bat client`합니다. 실행 `setup.bat` 와 `client` 인수 Client.com 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.  
  
5.  client.cs 파일에서 MEX 끝점의 주소 값과 `findValue`를 변경하여 서비스의 새 주소와 일치하도록 기본 서버 인증서를 설정합니다. 이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다. 다시 빌드합니다.  
  
6.  클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.  
  
7.  클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
8.  서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다. 이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.  
  
9. 서비스 컴퓨터에서 Visual Studio로 서비스 프로젝트를 빌드하고 service.exe를 실행합니다.  
  
10. 클라이언트 컴퓨터에서 client.exe를 실행합니다.  
  
    1.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
    > [!NOTE]
    >  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. CurrentUser-에 설치 된 서비스 인증서를 지워야를 컴퓨터 인증서를 사용 하는 WCF 샘플을 실행 한 경우 TrustedPeople 저장 합니다. 이렇게 하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com` 명령을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 사용](../../../../docs/framework/wcf/feature-details/using-metadata.md)
