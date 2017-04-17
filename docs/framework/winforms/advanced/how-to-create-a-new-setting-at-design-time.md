---
title: "방법: 디자인 타임에 새 설정 만들기 | Microsoft Docs"
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
  - "응용 프로그램 설정[Windows Forms], 만들기"
  - "응용 프로그램 설정[Windows Forms], 디자인 타임"
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 디자인 타임에 새 설정 만들기
설정 디자이너를 사용하여 디자인 타임에 새 설정을 만들 수 있습니다.  설정 디자이너는 새 설정을 만들고 해당 설정의 속성을 지정하는 데 사용할 수 있는 표 스타일 인터페이스입니다.  새 설정의 이름, 값, 형식 및 범위를 지정해야 합니다.  설정을 만든 후에는 코드에서 해당 설정에 액세스할 수 있습니다.  
  
### C\#에서 디자인 타임에 새 설정을 만들려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 **속성** 노드를 확장합니다.  
  
2.  새 설정을 추가할 .settings 파일을 두 번 클릭합니다.  이 파일의 기본 이름은 Settings.settings입니다.  
  
3.  설정 디자이너에서 설정의 이름, 값, 형식 및 범위를 설정합니다.  각 행은 단일 설정을 나타냅니다.  
  
### Visual Basic에서 디자인 타임에 새 설정을 만들려면  
  
1.  **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **속성** 페이지에서 **설정** 탭을 선택합니다.  
  
3.  설정 디자이너에서 설정의 이름, 값, 형식 및 범위를 설정합니다.  각 행은 단일 설정을 나타냅니다.  
  
## 참고 항목  
 [응용 프로그램 설정 및 사용자 설정 사용](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [방법: 디자인 타임에 기존 설정 값 변경](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)