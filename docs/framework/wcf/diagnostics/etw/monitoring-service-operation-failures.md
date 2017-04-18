---
title: "서비스 작업 오류 모니터링 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 서비스 작업 오류 모니터링
응용 프로그램에 분석 추적을 사용하도록 설정된 경우 이벤트 뷰어에서 서비스 오류를 쉽게 모니터링할 수 있습니다.이 항목에서는 서비스 작업이 실패한 경우를 확인하는 방법과 오류가 발생한 원인을 확인하는 방법을 보여 줍니다.  
  
### 서비스 작업 실패 정보 확인  
  
1.  **시작**, **실행**을 차례로 클릭하고 `eventvwr.exe`를 입력하여 이벤트 뷰어를 엽니다.  
  
2.  분석 추적을 사용하도록 설정하지 않은 경우 **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**을 차례로 확장합니다.**보기**, **분석 및 디버그 로그 표시**를 선택합니다.**분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용**을 선택합니다.서비스 작업이 실패한 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
3.  그런 다음 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)에서 만든 샘플을 [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]에서 엽니다. [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]을 관리자 권한으로 실행해야 서비스를 만들 수 있습니다.[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 샘플을 설치한 경우 자습서에서 만드는 것과 같은 완료된 프로젝트가 포함된 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md)을 열 수 있습니다.  
  
4.  Server 프로젝트의 Program.cs 파일에서 `CalculatorService` 클래스의 `Divide` 메서드 시작 부분에 다음 코드 줄을 추가합니다.  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
  
    ```  
  
5.  Client 프로젝트의 Program.cs 파일에서 value2에 할당된 값을 0으로 변경합니다.  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
  
    ```  
  
6.  **Ctrl\+F5**를 눌러 서버 응용 프로그램을 디버깅하지 않고 실행합니다.  
  
7.  Visual Studio 명령 프롬프트를 엽니다.클라이언트 디렉터리로 이동하고 명령줄에서 클라이언트를 실행합니다.  
  
8.  이벤트 뷰어에서 분석 로그를 사용하지 않도록 설정하고 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.서비스 실패를 설명하는 이벤트 ID가 [219 \- ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md)인 이벤트를 찾습니다.  
  
    ```Output  
    메시지를 처리하는 동안 'System.DivideByZeroException' 형식의 처리되지 않은 예외가 발생했습니다.전체 예외 ToString: System.DivideByZeroException: 0으로 나누려 했습니다.  
    ```  
  
    > [!NOTE]
    >  이벤트는 이벤트 뷰어로 전송될 때 버퍼링되므로 실패 이벤트가 바로 나타나지 않을 수 있습니다.