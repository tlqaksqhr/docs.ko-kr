---
title: "FindPrivateKey 샘플-WCF"
ms.date: 12/04/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29489cd1b82cf1c31f178d8a305a21371b542f15
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="findprivatekey-sample"></a>FindPrivateKey 샘플

인증서 저장소에서 특정 X.509 인증서와 연결된 개인 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다. FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.

> [!IMPORTANT]
> FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다. 참조는 [FindPrivateKey 프로젝트를 빌드하려면](#to-build-the-findprivatekey-project) FindPrivateKey 도구를 작성 하는 방법에 대 한 지침은 섹션.

X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다. 그러나 인증서를 다른 계정으로 실행 되는 서비스에서 액세스할 수 있습니다. 예를 들어 네트워크 서비스 계정입니다.

처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 개인 키 파일에 대한 액세스 권한이 없을 수도 있습니다. FindPrivateKey 도구는 지정된 X.509 인증서의 개인 키 파일 위치를 알려줍니다. 특정 X.509 인증서의 개인 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.

FindPrivateKey 도구를 사용 하 여 보안에 대 한 인증서를 사용 하는 예제는 *Setup.bat* 파일입니다. 와 같은 다른 도구를 개인 키 파일을 찾은 사용할 수 있습니다 *Cacls.exe* 파일에 적절 한 액세스 권한을 설정할 수 있습니다.

자체 호스팅된 실행 파일 등의 사용자 계정으로 Windows Communication Foundation (WCF) 서비스를 실행할 때 파일에 사용자 계정에 읽기 전용 권한이 있는지 확인 합니다. 인터넷 정보 서비스 (IIS)에서 WCF 서비스를 실행 하는 경우에 서비스가 실행 되는 기본 계정은 IIS 7 및 이전 버전에서 네트워크 서비스 또는 IIS 7.5 이상 버전에서 응용 프로그램 풀 Id입니다. 자세한 내용은 참조 [응용 프로그램 풀 Id](/iis/manage/configuring-security/application-pool-identities)합니다.

## <a name="examples"></a>예제

프로세스 읽기 권한이 없는 인증서에 액세스할 때는 다음 예와 비슷한 예외 메시지가 표시:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

이 경우 FindPrivateKey 도구를 사용 하 여 개인 키 파일을 찾으려고 하 고 서비스에서 실행 중인 프로세스의 액세스 권한을 설정 합니다. 예를 들어 이렇게 Cacls.exe 도구와 함께 다음 예제와 같이:

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>FindPrivateKey 프로젝트를 빌드하려면

프로젝트를 다운로드 하려면 방문 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](https://www.microsoft.com/download/details.aspx?id=21459)합니다.

1. 열기 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] 로 이동 하 고는 *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* 샘플을 설치한 디렉터리 위치 아래의 폴더입니다.

2. .sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.

3. 에 **빌드** 메뉴 선택 **솔루션 다시 빌드**합니다.

4. 솔루션을 빌드하면 FindPrivateKey.exe 파일이 생성됩니다.

## <a name="conventionscommand-line-entries"></a>규칙 — 명령줄 항목

 "[*옵션*]"는 선택적 매개 변수 집합을 나타냅니다.

 "{*옵션*}"는 필수 매개 변수 집합을 나타냅니다.

 "*option1* &#124; *옵션 2*"옵션 집합이 사이 선택을 나타냅니다.

 "\<*값*>"를 입력 매개 변수 값을 나타냅니다.

## <a name="usage"></a>용도

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

여기서

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

명령 프롬프트에서 지정 된 매개 변수가 없는 경우이 도움말 텍스트가 표시 됩니다.

## <a name="examples"></a>예제

이 예의 주체 이름 가진 인증서의 파일 이름을 찾아 "CN = localhost", 현재 사용자의 개인 저장소에 있습니다.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

이 예의 주체 이름 가진 인증서의 파일 이름을 찾아 "CN = localhost", 개인 현재 사용자의 저장 및 전체 디렉터리 경로 출력 합니다.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
