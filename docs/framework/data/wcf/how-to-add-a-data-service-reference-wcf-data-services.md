---
title: "방법: 데이터 서비스 참조 추가(WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, 구성"
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 방법: 데이터 서비스 참조 추가(WCF Data Services)
Visual Studio의 **서비스 참조 추가** 대화 상자를 사용하여 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 대한 참조를 추가할 수 있습니다.  이렇게 하면 Visual Studio에서 개발하는 클라이언트 응용 프로그램에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다.  이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다.  자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)을 참조하세요.  
  
### 데이터 서비스 참조를 추가하려면  
  
1.  \(선택 사항\) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.  
  
2.  클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 선택합니다.  
  
3.  데이터 서비스가 현재 솔루션에 포함되어 있는 경우 **검색**을 클릭합니다.  
  
     또는  
  
     **주소** 입력란에 데이터 서비스의 기본 URL\(예: `http://localhost:1234/Northwind.svc`\)을 입력하고 **이동**을 클릭합니다.  
  
4.  **확인**을 클릭합니다.  
  
     데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 추가됩니다.  
  
## 참고 항목  
 [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)