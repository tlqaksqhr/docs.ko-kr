---
title: "서비스 작업 오류 모니터링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6030b1ad1dc3953137d3b068be1bceb99975a5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="monitoring-service-operation-failures"></a>서비스 작업 오류 모니터링
응용 프로그램에 분석 추적을 사용하도록 설정된 경우 이벤트 뷰어에서 서비스 오류를 쉽게 모니터링할 수 있습니다.  이 항목에서는 서비스 작업이 실패한 경우를 확인하는 방법과 오류가 발생한 원인을 확인하는 방법을 보여 줍니다.  
  
### <a name="determining-service-operation-failure-information"></a>서비스 작업 실패 정보 확인  
  
1.  클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.  
  
2.  분석 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** . 선택 **보기**, **분석 및 디버그 로그 표시**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다. 서비스 작업이 실패한 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
3.  만든 샘플을 열고는 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md) 에 [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] 실행 해야 하는 참고 [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] 관리자 권한으로 서비스를 만들 수 있도록 합니다. 있는 경우는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 열 수 있습니다 설치 되어 있는 샘플의 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하 합니다.  
  
4.  Server 프로젝트의 Program.cs 파일에서 `Divide` 클래스의 `CalculatorService` 메서드 시작 부분에 다음 코드 줄을 추가합니다.  
  
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
  
6.  서버 응용 프로그램 키를 눌러 디버깅 하지 않고 실행 **Ctrl + f 5**합니다.  
  
7.  Visual Studio 명령 프롬프트를 엽니다.  클라이언트 디렉터리로 이동하고 명령줄에서 클라이언트를 실행합니다.  
  
8.  이벤트 뷰어에서 분석 로그를 사용하지 않도록 설정하고 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.  이벤트 ID를 사용 하 여 이벤트를 찾아보십시오 [219-ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), 서비스 오류를 설명 하는 합니다.  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  이벤트는 이벤트 뷰어로 전송될 때 버퍼링되므로 실패 이벤트가 바로 나타나지 않을 수 있습니다.
