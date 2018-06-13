---
title: 서비스 작업 기간 확인
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 8c86ccc09979071e0678be792f4937d526e23fa7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804965"
---
# <a name="determining-service-operation-duration"></a>서비스 작업 기간 확인
Windows Communication Foundation (WCF) 응용 프로그램에서 분석 추적을 사용 하는 경우 서비스 작업에 대 한 실행 기간 동안 이벤트 로그를 검사 하 여 쉽게 확인할 수 있습니다.  이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.  
  
### <a name="determining-service-operation-execution-duration"></a>서비스 작업 실행 기간 확인  
  
1.  클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.  
  
2.  분석 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** . 선택 **보기**, **분석 및 디버그 로그 표시**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다. 서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
3.  다음으로 서비스 프로젝트 및 해당 서비스와 상호 작용 하는 클라이언트 프로젝트가 포함 된 WCF 응용 프로그램을 엽니다.  수행 하 여 이러한 응용 프로그램을 만들 수 있습니다는 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.  WCF 샘플 설치 되어 있는 경우 열 수 있습니다는 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하 합니다.  
  
4.  키를 눌러 서버 응용 프로그램을 실행 **F5**합니다. 클라이언트 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 여 실행는 **클라이언트** 프로젝트를 선택 하 고 **디버그**, **새 인스턴스 시작**합니다.  
  
5.  이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.  이벤트 이벤트 ID를 확인 [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)합니다.  이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.  다음 이벤트는 Add 작업의 기간을 보여 줍니다.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
