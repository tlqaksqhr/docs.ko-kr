---
title: "방법: 연결 문자열 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 연결 문자열 정의
이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다.  이 항목은 [AdventureWorks Sales](http://msdn.microsoft.com/ko-kr/f16cd988-673f-4376-b034-129ca93c7832) 개념적 모델을 기반으로 합니다.  AdventureWorks Sales 모델은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 문서의 작업 관련 항목 전체에서 사용됩니다.  이 항목에서는 이미 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 구성하고 AdventureWorks Sales 모델을 정의한 것으로 가정합니다.  자세한 내용은 [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/ko-kr/d4fd6864-f2a1-48f0-aa32-1e318775a99a)을 참조하세요.  이 항목의 절차는 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/ko-kr/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)에도 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 프로젝트에서 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 마법사를 사용하면 이 마법사에서 자동으로 .edmx 파일을 생성하고 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/ko-kr/dadb058a-c5d9-4c5c-8b01-28044112231d)을 참조하세요.  
  
### Entity Framework 연결 문자열을 정의하려면  
  
-   프로젝트의 응용 프로그램 구성 파일\(app.config\)을 열고 다음 연결 문자열을 추가합니다.  
  
  
  
     프로젝트에 응용 프로그램 구성 파일이 없는 경우에는 **프로젝트** 메뉴에서 **새 항목 추가**를 선택하고 **일반** 범주, **응용 프로그램 구성 파일**을 차례로 선택한 다음 **추가**를 클릭하여 응용 프로그램 구성 파일을 추가할 수 있습니다.  
  
## 참고 항목  
 [Quickstart](http://msdn.microsoft.com/ko-kr/0bc534be-789f-4819-b9f6-76e51d961675)   
 [How to: Create a New .edmx File](http://msdn.microsoft.com/ko-kr/beb8189e-e51c-4051-839c-9902c224abf2)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ko-kr/91076853-0881-421b-837a-f582f36be527)