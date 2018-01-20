---
title: "방법: 연결 문자열 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 355d313fd607ccf85ba55b09b9ece4d9c88e298f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-define-the-connection-string"></a>방법: 연결 문자열 정의
이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다. 이 항목에 따라는 [AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 개념적 모델입니다. AdventureWorks Sales 모델은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 문서의 작업 관련 항목 전체에서 사용됩니다. 이 항목에서는 이미 구성 된 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] AdventureWorks Sales 모델을 정의 합니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일을 수동으로 정의](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a)합니다. 이 항목의 절차에도 나와 [하는 방법: 수동으로 Entity Framework 프로젝트 구성](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)합니다.  
  
> [!NOTE]
>  [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 프로젝트에서 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 마법사를 사용하면 이 마법사에서 자동으로 .edmx 파일을 생성하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 프로젝트를 구성합니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사 사용](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Entity Framework 연결 문자열을 정의하려면  
  
-   프로젝트의 응용 프로그램 구성 파일(app.config)을 열고 다음 연결 문자열을 추가합니다.  
  
  
  
     프로젝트에 없으면 응용 프로그램 구성 파일을 선택 하 여 범주를 추가할 수 있습니다 **새 항목 추가** 에서 **프로젝트** 메뉴에서 선택 하는 **일반** 범주 선택 하면 **응용 프로그램 구성 파일**을 클릭 한 다음 **추가**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빠른 시작](http://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [방법: 새.edmx 파일 만들기](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [ADO.NET 엔터티 데이터 모델 도구](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
