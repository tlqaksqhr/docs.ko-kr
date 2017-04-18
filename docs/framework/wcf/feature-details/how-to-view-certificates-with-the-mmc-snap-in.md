---
title: "방법: MMC 스냅인을 사용하여 인증서 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "인증서 [WCF], MMC 스냅인을 사용하여 보기"
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 방법: MMC 스냅인을 사용하여 인증서 보기
일반적인 자격 증명 형식은 X.509 인증서입니다.보안된 서비스 또는 클라이언트를 만들 때 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>과 같은 메서드를 사용하여 클라이언트 또는 서비스 자격 증명으로 사용할 인증서를 지정할 수 있습니다.메서드에는 인증서를 저장할 저장소 및 인증서를 검색할 때 사용할 값과 같은 여러 매개 변수가 필요합니다.다음 절차에서는 적절한 인증서를 찾기 위해 컴퓨터에서 저장소를 검사하는 방법을 보여 줍니다.인증서 지문을 찾는 예에 대해서는 [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)을 참조하십시오.  
  
### MMC 스냅인에서 인증서를 보려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  `mmc`를 입력하고 Enter 키를 누릅니다.로컬 컴퓨터 저장소에서 인증서를 보려면 관리자 역할이어야 합니다.  
  
3.  **파일** 메뉴에서 **스냅인 추가\/제거**를 클릭합니다.  
  
4.  **추가**를 클릭합니다.  
  
5.  **독립 실행형 스냅인 추가** 대화 상자에서 **인증서**를 선택합니다.  
  
6.  **추가**를 클릭합니다.  
  
7.  **인증서 스냅인** 대화 상자에서 **컴퓨터 계정**을 선택하고 **다음**을 클릭합니다.필요한 경우 **내 사용자 계정** 또는 **서비스 계정**을 선택할 수 있습니다.컴퓨터의 관리자가 아닐 경우에는 본인의 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.  
  
8.  **컴퓨터 선택** 대화 상자에서 **마침**을 클릭합니다.  
  
9. **독립 실행형 스냅인 추가** 대화 상자에서 **닫기**를 클릭합니다.  
  
10. **스냅인 추가\/제거** 대화 상자에서 **확인**을 클릭합니다.  
  
11. 해당 컴퓨터에 대한 인증서 저장소를 보려면 **콘솔 루트** 창에서 **인증서\(로컬 컴퓨터\)**를 클릭합니다.  
  
12. 선택적 요소입니다.사용자 계정에 대한 인증서를 보려면 3 ~ 6단계를 반복하십시오.7단계에서는 **컴퓨터 계정**을 선택하는 대신 **내 사용자 계정**을 클릭하고 8단계에서 10단계까지 반복합니다.  
  
13. 선택적 요소입니다.**파일** 메뉴에서 **저장** 또는 **다른 이름으로 저장**을 클릭합니다.나중에 다시 사용하기 위해 콘솔 파일을 저장합니다.  
  
## Internet Explorer로 인증서 보기  
 Internet Explorer를 사용하여 인증서를 보고, 내보내고, 가져오고, 삭제할 수도 있습니다.  
  
#### Internet Explorer로 인증서를 보려면  
  
1.  Internet Explorer에서 **도구**를 클릭한 다음 **인터넷 옵션**을 클릭하여 **인터넷 옵션** 대화 상자를 표시합니다.  
  
2.  **콘텐츠** 탭을 클릭합니다.  
  
3.  **인증서** 아래에서 **인증서**를 클릭합니다.  
  
4.  인증서 세부 정보를 보려면 인증서를 선택하고 **보기**를 클릭합니다.  
  
## 참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [방법: 개발 중 사용할 임시 인증서 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)   
 [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)