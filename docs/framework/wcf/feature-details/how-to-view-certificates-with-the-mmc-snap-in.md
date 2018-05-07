---
title: '방법: MMC 스냅인을 사용하여 인증서 보기'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: d924121b9d9fa267fa7d1ada13c9dc5f5bf1523d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>방법: MMC 스냅인을 사용하여 인증서 보기
일반적인 자격 증명 형식은 X.509 인증서입니다. 보안된 서비스 또는 클라이언트를 만들 때 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>과 같은 메서드를 사용하여 클라이언트 또는 서비스 자격 증명으로 사용할 인증서를 지정할 수 있습니다. 메서드에는 인증서를 저장할 저장소 및 인증서를 검색할 때 사용할 값과 같은 여러 매개 변수가 필요합니다. 다음 절차에서는 적절한 인증서를 찾기 위해 컴퓨터에서 저장소를 검사하는 방법을 보여 줍니다. 인증서 지문의 찾을 예제를 보려면 [하는 방법: 인증서의 지문을 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)합니다.  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a>MMC 스냅인에서 인증서를 보려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  형식 `mmc` ENTER 키를 누릅니다. 로컬 컴퓨터 저장소에서 인증서를 보려면 관리자 역할이어야 합니다.  
  
3.  에 **파일** 메뉴를 클릭 하 여 **스냅인 추가/제거**합니다.  
  
4.  **추가**를 클릭합니다.  
  
5.  에 **독립 실행형 스냅인 추가** 대화 상자에서 **인증서**합니다.  
  
6.  **추가**를 클릭합니다.  
  
7.  에 **인증서 스냅인** 대화 상자에서 **컴퓨터 계정** 클릭 **다음**합니다. 선택할 수 있습니다 **내 사용자 계정** 또는 **서비스 계정**합니다. 컴퓨터의 관리자가 아닐 경우에는 본인의 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.  
  
8.  에 **컴퓨터 선택** 대화 상자를 클릭 **마침**합니다.  
  
9. 에 **독립 실행형 스냅인 추가** 대화 상자를 클릭 **닫기**합니다.  
  
10. 에 **스냅인 추가/제거** 대화 상자를 클릭 **확인**합니다.  
  
11. 에 **콘솔 루트** 창 클릭 **인증서 (로컬 컴퓨터)** 인증서를 보려면 컴퓨터에 대 한 저장 합니다.  
  
12. 선택 사항입니다. 사용자 계정에 대한 인증서를 보려면 3 ~ 6단계를 반복하십시오. 선택 하는 대신 7 단계에서 **컴퓨터 계정**, 클릭 **내 사용자 계정** 8 ~ 10 단계를 반복 합니다.  
  
13. 선택 사항입니다. 에 **파일** 메뉴를 클릭 하 여 **저장** 또는 **다른 이름으로 저장**합니다. 나중에 다시 사용하기 위해 콘솔 파일을 저장합니다.  
  
## <a name="viewing-certificates-with-internet-explorer"></a>Internet Explorer로 인증서 보기  
 Internet Explorer를 사용하여 인증서를 보고, 내보내고, 가져오고, 삭제할 수도 있습니다.  
  
#### <a name="to-view-certificates-with-internet-explorer"></a>Internet Explorer로 인증서를 보려면  
  
1.  Internet Explorer에서 클릭 **도구**, 클릭 **인터넷 옵션** 표시 하는 **인터넷 옵션** 대화 상자.  
  
2.  클릭는 **콘텐츠** 탭 합니다.  
  
3.  아래 **인증서**, 클릭 **인증서**합니다.  
  
4.  모든 인증서의 세부 정보를 보려면 인증서 선택 하 고 클릭을 **보기**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [방법: 개발 중 사용할 임시 인증서 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [방법: 인증서의 지문 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
