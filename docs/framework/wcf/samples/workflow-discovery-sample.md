---
title: "Workflow Discovery 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Workflow Discovery 샘플
이 샘플에서는 워크플로 서비스를 검색 가능하게 만드는 방법과 특정 서비스를 검색하는 사용자 지정 코드 활동을 작성하는 방법을 보여 줍니다.  
  
## 세부 항목  
 찾기 활동 및 워크플로 사용  
  
## 추가 설명  
 샘플의 첫 번째 부분에서는 구성을 사용하여 워크플로 서비스를 검색 가능하게 만듭니다.또한 구성을 사용하여 범위와 같은 사용자 지정 메타데이터로 서비스를 적절하게 적용할 수도 있습니다.클라이언트에서 이 샘플은 검색을 사용하여 특정 계약과 일치하는 서비스를 검색하는 사용자 지정 코드 활동을 사용합니다.코드 활동은 URI를 출력하며 이 URI는 나중에 보내기 활동에서 사용됩니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  이 샘플에서는 HTTP 끝점을 사용하며, 이 샘플을 실행하려면 적절한 URL ACL이 있어야 합니다. 자세한 내용은 [HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353)을 참조하십시오.권한이 높은 명령 프롬프트에서 다음 명령을 실행하면 적절한 ACL이 추가됩니다.셸에서 변수 형식을 인식하지 못하는 경우 다음 인수 대신 도메인과 사용자 이름을 사용합니다.  
  
     **netsh http add urlacl url\=http:\/\/\+:8000\/ user\=%DOMAIN%\\%UserName%**  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`