---
title: 추적을 사용하여 워크플로 실행 기간 확인
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: 9f9c65f2c873d54da443db14e7f5797ef1e14174
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>추적을 사용하여 워크플로 실행 기간 확인
이 항목에서는 성공적으로 완료된 자체 호스트되는 워크플로가 실행하는 데 걸리는 시간을 워크플로 추적을 사용하여 확인하는 방법을 보여 줍니다.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>워크플로 추적을 사용하여 워크플로 응용 프로그램 실행 기간을 확인하려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.  선택 **파일**, **새**, **프로젝트**합니다.  아래 **C#**, 선택는 **워크플로** 노드.  선택 **워크플로 콘솔 응용 프로그램** 템플릿 목록에서.  새 프로젝트의 이름을 `WorkflowDurationTracing` 클릭 **확인**합니다.  
  
2.  Workflow1.xaml을 엽니다.  <xref:System.Activities.Statements.Delay> 활동을 디자이너 화면으로 끌어서 놓습니다. 활동의 Duration 속성에 00:00:10 값(10초)을 할당합니다.  
  
3.  클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.  
  
4.  워크플로 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** . 선택 **보기**, **분석 및 디버그 로그 표시**합니다. 마우스 오른쪽 단추로 클릭 **디버그** 선택 **로그 사용**합니다. 워크플로가 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
5.  Ctrl+Shift+B를 눌러 워크플로 응용 프로그램을 실행합니다.  
  
6.  이벤트 뷰어에서 ID가 1009인 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다. 메시지가 기록된 시간을 기록해 둡니다.  
  
 **부모 작업 ', DisplayName: ', InstanceId: ' 예약 된 자식 작업 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  ID가 1001인 다른 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다.  이 메시지의 기록된 값에서 이전 메시지 시간을 빼서 워크플로 실행 기간을 확인합니다. 이 시간은 10초 정도여야 합니다.  
  
 **WorkflowInstance Id: ' 1bbac57b-3322-498e-9e27-8833fda3a5bf' Closed 상태로 완료 되었습니다.**  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 추적](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Windows Server App Fabric 모니터링](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [App Fabric로 응용 프로그램 모니터링](http://go.microsoft.com/fwlink/?LinkId=201275)
