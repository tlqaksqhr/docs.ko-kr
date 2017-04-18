---
title: "방법: C#에서 응용 프로그램에 다중 설정 집합 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "응용 프로그램 설정[Windows Forms], C#"
  - "응용 프로그램 설정[Windows Forms], 여러 집합"
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: C#에서 응용 프로그램에 다중 설정 집합 추가
응용 프로그램에 여러 개의 설정 집합을 사용하려는 경우가 있습니다.  예를 들어 특정 설정 그룹을 자주 변경해야 하는 응용 프로그램을 개발하려는 경우 다른 설정에는 영향을 주지 않으면서 파일이 전체적으로 바뀔 수 있도록 해당 설정 그룹을 단일 파일로 구분할 수 있습니다.  Visual Studio에서는 프로젝트에 여러 개의 설정 집합을 추가할 수 있습니다.  추가 설정 집합은 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
### 응용 프로그램에 설정 집합을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  **새 항목 추가** 대화 상자가 열립니다.  
  
2.  **새 항목 추가** 대화 상자에서 **설정 파일**을 선택하고 파일 이름을 입력한 다음 **추가**를 클릭하여 솔루션에 새 설정 파일을 추가합니다.  
  
3.  **솔루션 탐색기**에서 새 설정 파일을 **속성** 폴더로 끌어 옵니다.  이렇게 하면 코드에서 새 설정을 사용할 수 있습니다.  
  
4.  이 파일의 설정을 다른 설정 파일과 같은 방식으로 추가 및 사용합니다.  이 설정 그룹은 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
## 참고 항목  
 [응용 프로그램 설정 및 사용자 설정 사용](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)