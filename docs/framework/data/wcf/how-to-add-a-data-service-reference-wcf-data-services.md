---
title: "방법: 데이터 서비스 참조 추가(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fa20e9ed0cefbe587bba90ad25d5460592e3ecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>방법: 데이터 서비스 참조 추가(WCF Data Services)
사용할 수는 **서비스 참조 추가** 대화에 대 한 참조를 추가 하려면 Visual Studio에서 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]합니다. 이렇게 하면 Visual Studio에서 개발하는 클라이언트 응용 프로그램에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다. 이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다. 자세한 내용은 참조 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)합니다.  
  
### <a name="to-add-a-data-service-reference"></a>데이터 서비스 참조를 추가하려면  
  
1.  (선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.  
  
2.  클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **서비스 참조 추가**합니다.  
  
3.  클릭 하 여 데이터 서비스는 현재 솔루션의 일부 이면 **Discover**합니다.  
  
     또는  
  
     에 **주소** 텍스트 상자에 입력 데이터 서비스의 기준 URL과 같은 `http://localhost:1234/Northwind.svc`, 클릭 하 고 **이동**합니다.  
  
4.  **확인**을 클릭합니다.  
  
     데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 추가됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
