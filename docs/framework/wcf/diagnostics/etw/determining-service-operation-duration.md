---
title: "서비스 작업 기간 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 서비스 작업 기간 확인
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램에 분석 추적이 사용하도록 설정되어 있으면 이벤트 로그를 검사하여 서비스 작업의 실행 기간을 손쉽게 확인할 수 있습니다.  이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.  
  
### 서비스 작업 실행 기간 확인  
  
1.  **시작**, **실행**을 차례로 클릭하고 `eventvwr.exe`를 입력하여 이벤트 뷰어를 엽니다.  
  
2.  분석 추적을 사용하도록 설정하지 않은 경우 **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**을 차례로 확장합니다.  **보기**, **분석 및 디버그 로그 표시**를 선택합니다.  **분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용**을 선택합니다.  서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
3.  그런 다음 서비스 프로젝트 및 해당 서비스와 상호 작용하는 클라이언트 프로젝트가 포함된 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램을 엽니다.  이러한 응용 프로그램은 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)를 따라 만들 수 있습니다.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 샘플을 설치한 경우 자습서에서 만든 것과 같은 완료된 프로젝트가 포함된 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md)을 열 수 있습니다.  
  
4.  **F5** 키를 눌러 서버 응용 프로그램을 실행합니다.  **Client** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **디버그**, **새 인스턴스 시작**을 차례로 선택하여 클라이언트 응용 프로그램을 실행합니다.  
  
5.  이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.  이벤트 ID가 [214 \- OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)인 이벤트를 찾습니다.  이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.  다음 이벤트는 Add 작업의 기간을 보여 줍니다.  
  
    ```Output  
  
    OperationInvoker가 'Add' 메서드에 대한 호출을 완료했습니다.  메서드 호출 기간은 '3'밀리초입니다.    
    ```