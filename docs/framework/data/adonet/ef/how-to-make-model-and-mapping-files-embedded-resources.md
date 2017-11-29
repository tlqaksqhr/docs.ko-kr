---
title: "방법: 모델 및 매핑 파일을 포함 리소스로 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98fb3ada369279a34ed08110644aabcbbe72a501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>방법: 모델 및 매핑 파일을 포함 리소스로 만들기
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 모델 및 매핑 파일을 응용 프로그램의 포함 리소스로 배포할 수 있습니다. 포함된 모델 및 매핑 파일이 있는 어셈블리는 엔터티 연결과 동일한 응용 프로그램 도메인에 로드해야 합니다. 자세한 내용은 참조 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)합니다. 기본적으로 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 도구는 모델과 매핑 파일을 포함합니다. 모델 및 매핑 파일을 수동으로 정의하는 경우 이 절차를 사용하여 파일을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 응용 프로그램과 함께 포함 리소스로 배포해야 합니다.  
  
> [!NOTE]
>  포함 리소스를 유지하려면 모델 및 매핑 파일이 수정될 때마다 이 절차를 반복해야 합니다.  
  
### <a name="to-embed-model-and-mapping-files"></a>모델 및 매핑 파일을 포함하려면  
  
1.  **솔루션 탐색기**, 개념적 (.csdl) 파일을 선택 합니다.  
  
2.  에 **속성** 창 설정 **빌드 작업** 를 **포함 리소스**합니다.  
  
3.  저장소 파일(.ssdl) 및 매핑 파일(.msl)에 대해 1단계와 2단계를 반복합니다.  
  
4.  **솔루션 탐색기**, App.config 파일을 두 번 클릭 한 다음 수정 된 `Metadata` 에서 매개 변수는 `connectionString` 다음 형식 중 하나를 기반으로 특성:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     자세한 내용은 참조 [연결 문자열](../../../../../docs/framework/data/adonet/ef/connection-strings.md)합니다.  
  
## <a name="example"></a>예제  
 다음 연결 문자열에 포함 된 모델 및 매핑 파일에 대 한 참조는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832)합니다. 이 연결 문자열은 프로젝트의 App.config 파일에 저장됩니다.  
  
  
  
## <a name="see-also"></a>참고 항목  
 [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [방법: 연결 문자열 정의](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [방법: EntityConnection 연결 문자열 작성](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [ADO.NET 엔터티 데이터 모델 도구](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
