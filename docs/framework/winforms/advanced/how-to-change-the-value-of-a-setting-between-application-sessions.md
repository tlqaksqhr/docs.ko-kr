---
title: "방법: 응용 프로그램 세션 간 설정 값 변경 | Microsoft Docs"
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
  - "응용 프로그램 설정[Windows Forms], 응용 프로그램 세션 간"
  - "응용 프로그램 설정[Windows Forms], 변경"
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 응용 프로그램 세션 간 설정 값 변경
응용 프로그램을 컴파일 및 배포한 후 응용 프로그램 세션 간에 설정 값을 변경하려는 경우가 있습니다.  예를 들어 올바른 데이터베이스 위치를 가리키도록 연결 문자열을 변경할 수 있습니다.  응용 프로그램이 컴파일 및 배포된 후에는 디자인 타임 도구를 사용할 수 없으므로 설정 값을 파일에서 수동으로 변경해야 합니다.  
  
### 응용 프로그램 세션 간에 설정 값을 변경하려면  
  
1.  Microsoft 메모장이나 다른 텍스트 또는 XML 편집기를 사용하여 응용 프로그램과 연결된 .config 파일을 엽니다.  
  
2.  변경할 설정의 항목을 찾습니다.  설정 항목은 아래에 표시된 예제와 같이 나타납니다.  
  
    ```  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  새 설정 값을 입력하고 파일을 저장합니다.  
  
## 참고 항목  
 [응용 프로그램 설정 및 사용자 설정 사용](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)