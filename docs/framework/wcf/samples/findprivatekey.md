---
title: "FindPrivateKey | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "FindPrivateKey"
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# FindPrivateKey
인증서 저장소에서 특정 X.509 인증서와 연결된 개인 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다.FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.  
  
> [!IMPORTANT]
>  FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다.FindPrivateKey 도구를 빌드하는 방법에 대한 지침은 아래의 "FindPrivateKey 프로젝트를 빌드하려면" 단원을 참조하십시오.  
  
 X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다.하지만 다른 계정\(예: [!INCLUDE[wxp](../../../../includes/wxp-md.md)]의 ASPNET 또는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]의 NETWORK SERVICE 계정\)에서 실행되는 서비스에서 인증서에 액세스할 수도 있습니다.  
  
 처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 개인 키 파일에 대한 액세스 권한이 없을 수도 있습니다.FindPrivateKey 도구는 지정된 X.509 인증서의 개인 키 파일 위치를 알려줍니다.특정 X.509 인증서의 개인 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.  
  
 보안에 인증서를 사용하는 샘플의 경우 Setup.bat 파일에서 FindPrivateKey 도구를 사용합니다.개인 키 파일을 찾고 나면 Cacls.exe 등의 다른 도구를 사용하여 파일에 적절한 액세스 권한을 설정할 수 있습니다.  
  
 자체 호스팅 실행 파일 등의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 사용자 계정에서 실행하는 경우에는 사용자 계정에 파일에 대한 읽기 전용 권한이 있는지 확인해야 합니다.IIS\(인터넷 정보 서비스\)에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 실행하는 경우 서비스가 실행되는 기본 계정은 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]의 ASPNET 또는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]의 NETWORK SERVICE이며, 기본적으로 개인 키 파일에 대한 액세스 권한이 없습니다.  
  
## 예제  
 프로세스에 읽기 권한이 없는 인증서에 액세스하면 다음 예와 비슷한 예외 메시지가 표시됩니다.  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 이 경우 FindPrivateKey 도구를 사용하여 개인 키 파일을 찾은 다음 서비스가 실행 중인 프로세스의 액세스 권한을 설정합니다.예를 들어, 다음 예와 같이 Cacls.exe 도구를 사용하면 됩니다.  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### FindPrivateKey 프로젝트를 빌드하려면  
  
1.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동합니다.  
  
2.  .sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.  
  
3.  **빌드** 메뉴에서 **솔루션 다시 빌드**를 선택합니다.클라이언트 프로그램 파일은 client\\bin에 빌드되고 서비스 프로그램 파일이 service\\bin에 빌드됩니다.  
  
4.  솔루션을 빌드하면 FindPrivateKey.exe 파일이 생성됩니다.  
  
## 규칙 \- 명령줄 항목  
 "\[*option*\]"은 선택적인 매개 변수 집합을 나타냅니다.  
  
 "{*option*}"은 명령 매개 변수의 필수 집합을 나타냅니다.  
  
 "*option1* &#124; *option2*"는 옵션 집합 사이의 선택을 나타냅니다.  
  
 "\<*value*\>"는 입력할 매개 변수 값을 나타냅니다.  
  
## 용도  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 명령 프롬프트에 매개 변수가 지정되지 않은 경우에는 이 도움말 텍스트가 표시됩니다.  
  
## 예제  
 이 예제에서는 현재 User.FindPrivateKey My CurrentUser \-n "CN\=localhost"의 개인 저장소에서 제목 이름이 "CN\=localhost"인 인증서의 파일 이름을 찾습니다.  
  
 이 예제에서는 현재 사용자의 개인 저장소에서 제목 이름이 "CN\=localhost"인 인증서의 파일 이름을 찾아 전체 디렉터리 경로를 출력합니다.  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
  
```  
  
 이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## 참고 항목